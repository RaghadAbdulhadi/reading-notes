### Django Forms Advantages:
- Quickly generate HTML form widgets
- Validate data and process it into a Python data structure
- Create form versions of our Models, quickly update models from Forms

To Create a form
- Create a forms.py file inside the application
-> from django import forms

Example:

    class FormName(forms.Form):
        name = forms.CharField()
        email = forms.EmailField()
        text = forms.CharField(widget=forms.Textarea)

*To view the form*
- Inside our views.py file
-> from . import forms or,

-> from forms import FormName

*Create a new view for the form*
Example:

    def form_name_view(request):
        form = forms.FormName()
        return render(request, 'form_name.html',{'form':form})

*Add the view to the app's url*
- urlpatterns = [
    path('formpage/', views.form_name_view, name='form_name')
]

*To inject the form using template tagging*
- Pass in the key from the context dictionary {{ form }}


**HTTP, GET and POST**

- HTTP stands for Hypertext Transfer Protocol and is designed to enable communication between a client and a server
- The client submits a request, the server then responds
- The most commonly used methods for this request/response protocol are GET and POST
    - GET - requests data from a resource
    - POST - submits data to be process to a resource

*On form_page.html*
<div class="container">
    <form method="POST">
        {{ form.as_p}}
        <!-- to have a nicer layout, layed from top to bottom -->
        {% csrf_token %}
        <!-- CSRF cross-site request forgery token, which secures the HTTP POST action that is initiated on the subsequent submission of a form -->
        <input type="submit" class="btn btn-primary" value="Submit">
    </form>
</div>

*To inform the view that if we get a POST back, we should check if the data is valid and if so, grab the data*

```python
    def form_name_view(request):
        form = forms.FormName()

        # Check to see if we get a post back
        if request.method == "POST":
            form = FormName(request.POST)

            # Check to see form is valid
            if form.is_valid():
            # Do smth
            print("Form Validation Success")
            print("Name: " + form.cleaned_data['name'])
            print("Email: " + form.cleaned_data['email'])
            print("Text: " + form.cleaned_data['text'])
        return render(request, 'basicapp/form_page.html', {'form': form})
```
