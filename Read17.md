# Web Scrapping 
Web scraping is a technique to automatically access and extract large amounts of information from a website, which can save a huge amount of time and effort. 

Web scraping a web page involves fetching it and extracting from it. Fetching is the downloading of a page (which a browser does when a user views a page). Therefore, web crawling is a main component of web scraping, to fetch pages for later processing. Once fetched, then extraction can take place. The content of a page may be parsed, searched, reformatted, its data copied into a spreadsheet or loaded into a database. Web scrapers typically take something out of a page, to make use of it for another purpose somewhere else

**Important notes about web scraping:**

- Read through the website’s Terms and Conditions to understand how you can legally use the data. Most sites prohibit you from using the data for commercial purposes.
- Make sure you are not downloading data at too rapid a rate because this may break the website. You may potentially be blocked from the site as well.

**Imports**

    import requests
    import urllib.request
    import time
    from bs4 import BeautifulSoup

**Access**
Set the url to the website and access the site with our requests library.
url = 'http://..........html'
response = requests.get(url)
If the access was successful, you should see the following output:

    Response [200]

**Parse the html with BeautifulSoup**

    soup = BeautifulSoup(response.text, “html.parser”)

## How to Scrape Websites Without Getting Blocked

**Respect Robots.txt**

If it contains lines like the ones shown below, it means the site doesn’t like and does not want to be scraped.

    User-agent: *

    Disallow:/ 

**Make the crawling slower, do not slam the server, treat websites nicely**

The faster you crawl, the worse it is for everyone. If a website gets too many requests than it can handle it might become unresponsive.

**Do not follow the same crawling pattern**

Incorporate some random clicks on the page, mouse movements and random actions that will make a spider look like a human.

**Make requests through Proxies and rotate them as needed**

Multiple requests coming from the same IP will lead you to get blocked, which is why we need to use multiple addresses. When we send requests from a proxy machine, the target website will not know where the original IP is from, making the detection harder.

Create a pool of IPs that you can use and use random ones for each request. Along with this, you have to spread a handful of requests across multiple IPs.


**Rotate User Agents and corresponding HTTP Request Headers between requests**

Now, just sending User-Agents alone would get you past most basic bot detection scripts and tools. If you find your bots getting blocked even after putting in a recent User-Agent string, you should add some more request headers.

**Use a headless browser like Puppeteer, Selenium or Playwright**

The simplest check is if the client (web browser) can render a block of JavaScript. If it doesn’t, then it pretty much flags the visitor to be a bot. While it is possible to block running JavaScript in the browser, most of the Internet sites will be unusable in such a scenario and as a result, most browsers will have JavaScript enabled.

**Beware of Honey Pot Traps**

Honeypots are systems set up to lure hackers and detect any hacking attempts that try to gain information. It is usually an application that imitates the behavior of a real system. Some websites install honeypots, which are links invisible to normal users but can be seen by web scrapers.

**Check if Website is Changing Layouts**

Some websites make it tricky for scrapers, serving slightly different layouts.

check how the layout is different and add a condition in your code to scrape those pages differently.

**Avoid scraping data behind a login**

If a page is protected by login, the scraper would have to send some information or cookies along with each request to view the page. This makes it easy for the target website to see requests coming from the same address. They could take away your credentials or block your account which can, in turn, lead to your web scraping efforts being blocked.

Its generally preferred to avoid scraping websites that have a login as you will get blocked easily, but one thing you can do is imitate human browsers whenever authentication is required you get the target data you need.

**Use Captcha Solving Services**

Many websites use anti web scraping measures. If you are scraping a website on a large scale, the website will eventually block you. You will start seeing captcha pages instead of web pages. There are services to get past these restrictions such as 2Captcha or Anticaptcha.


### How can websites detect and block web scraping?

- Unusual traffic/high download rate especially from a single client/or IP address within a short time span.
- Repetitive tasks performed on the website in the same browsing pattern – based on an assumption that a human user won’t perform the same repetitive tasks all the time.
- Checking if you are real browser – A simple check is to try and execute javascript. Smarter tools can go a lot more and check your Graphic cards and CPUs to make sure you are coming from real browser.
- Detection through honeypots – these honeypots are usually links which aren’t visible to a normal user but only to a spider. When a scraper/spider tries to access the link, the alarms are tripped.


**How to address this detection and avoid web scraping getting blocked?**

Spend some time upfront and investigate the anti-scraping mechanisms used by a site and build the spider accordingly. It will provide a better outcome in the long run and increase the longevity and robustness of your work.

**How do you find out if a website has blocked or banned you?**

If any of the following signs appear on the site that you are crawling, it is usually a sign of being blocked or banned.

    CAPTCHA pages
    Unusual content delivery delays
    Frequent response with HTTP 404, 301 or 50x errors
    
Frequent appearance of these HTTP status codes is also indication of blocking

    301 Moved Temporarily
    401 Unauthorized
    403 Forbidden
    404 Not Found
    408 Request Timeout
    429 Too Many Requests
    503 Service Unavailable