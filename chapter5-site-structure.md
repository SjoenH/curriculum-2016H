## Site structure

### URL
Uniform Resource Locators (URL) are used to link to another document or resource. This can be a link to another web site, or to an external style sheet, script, image, submit a form, or any other resource. URLs can also be used to link to sections within the same document.  

The URL specifies the precise location of a resource on the Internet. They follow a protocol, a set of rules defining how information is exchanged between two resources, and web browsers communicate using Hypertext Transfer Protocol(HTTP). URLs for all web pages must start with the scheme "http" or "https" (secure HTTP). Other internet resources use different protocols, and have different scheme names, such as ftp.

An URL may look like `http://developer.mozilla.org` and `http://developer.mozilla.org/en-US/docs/Learn/`. Any of those URLs can be typed into our browser's address bar to tell it to load the associated page.

An URL is composed of different parts, some mandatory and others optional. Let's dissect the url `http://www.example.com:80/path/to/myfile.html?key1=valu e1&key2=value2#SomewhereInTheDocument`.

`http://` is the protocol part of the URL. It indicates which protocol the browser must use. Usually it is the `http ` protocol, or its secured version `https`. Browsers use `http` by default. The web requires one of those two, but browsers also know how to handle other protocols like:
* mailto (opens a mail client)
* ftp (handles file transfers)

`www.example.com` is the domain of the URL. It indicates which web server is being requested. Alternatively it is possible to directly use an IP address, but because it is less convenient, it is not often used on the web.

`:80` is the port, and indicates the technical "gate" used to access the resources on the web server. It is usually omitted if the web serves use the standard ports of the HTTP protocol (80 for HTTP and 443 for HTTPS) to grant access to its resources.

`/path/to/myfile.html` is the path to the resource on the web server. In the early days of the web, a path like this represented a physical file location on the web server. Now it is mostly an abstraction handled by the web server without any physical reality.

`?key1=value1&key2=value2` are extra parameters provided to the web server. Those parameters are a list of key/value pairs separated by the & symbol. The web server can use those parameters to do an operation before returning the resource. Each web server has its own rules regarding parameters, and the only reliable way to know if a specific web server is handling parameters is by asking the web server owner.

`#SomewhereInTheDocument` is an anchor to another part of the resource itself. An anchor represents a sort of "bookmark" inside the resource, giving the browser the directions to show the content located at that "bookmarked" spot. On an HTML document, for example, the browser will scroll to the point where the anchor is defined. On a video or audio file, the browser will try to go to the time the anchor represents.

#### GET and POST
Let's jump back to the parameters of the URL again, the `?key1=value1&key2=value2` section.

These parameters are used with a method called GET. There are two main methods when doing HTTP requests, GET and POST. There are others also, but they are not a part of this course. When you want to request data from a specific resource, as we do in the example above, use GET. If you want to submit data to be processed by a specific resource, use POST.

When you do a GET request, you will not manipulate any data on the server side, so a GET request should return the same result each time. POST will update data on the server side, and will thus will change the state of the software.

Using GET, the query string is sent as a part of the URL, where the first key is preceded by a ? symbol. An example of a request is for a user management software and you want to see information about user with id 5. You would then append `?userid=5` to your URL.

Some properties to be aware of with the GET method:
* GET requests can be cached
* GET requests can remain in the browser's history
* GET requests can be distributed and shared
* GET requests have length restrictions because the URL has a max length
* GET requests can be hacked, so don't send sensitive data, e.g. passwords, with GET.

On the other hand, we have the POST method. POST requests are send as a separate message, and not in the URL. POST requests are never cached, do not remain in the browser's history and can not be bookmarked. POSt should be used for sensitive data such as passwords, credit card numbers and bank account numbers. There is no max length for POST, so use that in stead of GET if you are sending lots of data.

You use GET or POST as part of a e.g. form (which you will learn about later). To use either GET or POST you specify the chosen method like this `<form method="POST" action="server_side_processing.php">` which will POST information to the program server_side_processing.php in the same directory as the current form on the server.

### Site map

When creating a web site, you should have an idea of how the site will look architecturally. That is, how the pages are linked together, and how the pages are ordered in a hierarchy. You have a landing page, which will be the first page the user sees, then you could have some pages in an about category, and different products under a shop category. In order to have an overview over the page, we should have a site map, or storyboard.

#### Storyboard
A storyboard is a diagram of a web site's structure, showing all the pages in the site and indicating how they are linked together. You should storyboard your web site before you start creating your pages in order to determine which structure works best for the type of information your site contains. A well designed structure can ensure that users are able to navigate the site without getting lost or missing important information.

![Storyboard](images/storyboard.png)

There are three ways of structuring your web pages, hierarchically, linear and a mix between those two.

In a linear structure, each page is linked with the pages that follow and precede in in an ordered chain. This works best for web pages with a clearly defined order, e.g. a galleries or long articles that are divided over several pages.

![Linear structure](images/linear.png)

In an augmented linear structure, each page contains an additional link back to an opening page.

![Augmented linear structure](images/augmented.png)

In the hierarchical structure, the pages are linked from the most general page down to more specific pages. Users easily move from general to specific and back again. If you have a navigation bar on your page, the links would be organized in a list of hyperlinks, grouped together in the same section of the page.

![Hierarchical structure](images/hierarchical.png)

As websites become larger and more complex, you often need to use a combination of the two structures. The overall form can be hierarchical, allowing the user to move from general to specific, however the links also allow users to move through the site in a linear fashion.

![Mixed structure](images/mixed.png)

Being proactive will allow you to make a website that is easy to use with less effort. Each page should contain, at a minimum, a link to the site's home page, or to the relevant main topic page.

You may want to supply your users with a site index (site map) which is a page containing an outline of the entire site and its contents with hyperlinks.
