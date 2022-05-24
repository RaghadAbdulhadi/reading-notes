# Permisions:
Django comes with a built-in permissions system. It provides a way to assign permissions to specific users and groups of users.

**The Django admin site uses permissions as follows:**

Access to view objects is limited to users with the “view” or “change” permission for that type of object.
Access to view the “add” form and add an object is limited to users with the “add” permission for that type of object.
Access to view the change list, view the “change” form and change an object is limited to users with the “change” permission for that type of object.
Access to delete an object is limited to users with the “delete” permission for that type of object.

Together with authentication and throttling, permissions determine whether a request should be granted or denied access.

Permission checks are always run at the very start of the view, before any other code is allowed to proceed. Permission checks will typically use the authentication information in the request.user and request.auth properties to determine if the incoming request should be permitted.

### How permissions are determined
The request was successfully authenticated, but permission was denied. — An HTTP 403 Forbidden response will be returned.
The request was not successfully authenticated, and the highest priority authentication class does not use WWW-Authenticate headers. — An HTTP 403 Forbidden response will be returned.
The request was not successfully authenticated, and the highest priority authentication class does use WWW-Authenticate headers. — An HTTP 401 Unauthorized response, with an appropriate WWW-Authenticate header will be returned.

### Object level permissions

EST framework permissions also support object-level permissioning. Object level permissions are used to determine if a user should be allowed to act on a particular object, which will typically be a model instance.

### Setting the permission policy
The default permission policy may be set globally, using the DEFAULT_PERMISSION_CLASSES setting.

## API Reference

### AllowAny
The AllowAny permission class will allow unrestricted access, regardless of if the request was authenticated or unauthenticated.

### IsAuthenticated
The IsAuthenticated permission class will deny permission to any unauthenticated user, and allow permission otherwise.

### IsAdminUser
The IsAdminUser permission class will deny permission to any user, unless user.is_staff is True in which case permission will be allowed.

### IsAuthenticatedOrReadOnly
The IsAuthenticatedOrReadOnly will allow authenticated users to perform any request. Requests for unauthorised users will only be permitted if the request method is one of the "safe" methods; GET, HEAD or OPTIONS.

### DjangoModelPermissions
This permission class ties into Django's standard django.contrib.auth model permissions. This permission must only be applied to views that have a .queryset property or get_queryset() method. Authorization will only be granted if the user is authenticated and has the relevant model permissions assigned.

### DjangoModelPermissionsOrAnonReadOnly
Similar to DjangoModelPermissions, but also allows unauthenticated users to have read-only access to the API.

### DjangoObjectPermissions

This permission class ties into Django's standard object permissions framework that allows per-object permissions on models. In order to use this permission class, you'll also need to add a permission backend that supports object-level permissions, such as django-guardian.

### Custom permissions
To implement a custom permission, override BasePermission and implement either, or both, of the following methods:

.has_permission(self, request, view)
.has_object_permission(self, request, view, obj)
The methods should return True if the request should be granted access, and False otherwise.