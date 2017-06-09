---
layout: post
title: Web Views in iOS
---

The two different class of web views that are supported in iOS are WKWebView and UIWebView. There are obvious fundamental differences between these two classes that eases the decision-making process. 

In WWDC 2014, Apple introduced WebKit with a brand new WKWebView as a better version of the existing web view (i.e. UIWebView) in the UIKit. It is well known that UIWebView suffers from some major issues like the memory leak, and can throttle the application that heavily dependent on web views. As a fix to many such issues, Apple released the new [WebKit](https://developer.apple.com/documentation/webkit) with many new features majority of them are improvements in performance and user experience. Apple recommends to use WKWebView in the applications that plan to heavily consume them, but it is good to know the what are the pros and cons of this new framework. 

## WKWebView: How different from UIWebView?

The list of differences is given below.

### The Pros
* Runs outside of the app's main process
* Uses Nitro, a faster JavaScript engine
* Supports server-side authentication challenges
* Supports authenticating self-signed security certificates & certificates with errors
* Handles JavaScript asynchronously
* Eliminates certain touch delays

### The Cons
* Requires iOS 8 or later
* Does not support AJAX requests to locally-stored files
* Does not support 'Accept Cookies' setting
* Does not support 'Advanced Cache Settings'
* HTML5 local storage clears when app is exited
* Does not support logging of WebKit requests
* May not capture screenshots as expected

A brief description of these differences:

**Runs outside of the app's main process**: This is probably the biggest performance boost to the apps that heavily depend on web views. Running a web view in the app consumes a significant amount of memory and processing power for rendering the web pages. In worst case, the app might even crash because it has reached maximum memory limit. In order to escalate this, you can switch from UIWebView to WKWebView. Apple solves this problem by launching a new process for web view and it consumes all the resources outside of your app, the downside of this alternative is you might not be able to intercept and modify the requests to a proxy server, whereas in UIWebView you can pretty much do anything related to the requests.   

**Uses Nitro, a faster JavaScript engine**: Since WKWebView is launched as a new process Apple replaced the default javascript engine with Nitro, an advanced javascript engine as it doesn't effect apps resources and the apps can also leverage this for better user experience.

**Supports server-side authentication challenges**: It supports server side authentication challenges and cookie storage.

**Supports authenticating self-signed security certificates & certificates with errors**: It supports self-signed security certificates and in the case of errors you can still be able to load the web page (this feature is added to Swift 3).

**Handles JavaScript asynchronously**: As most of the modern web pages make server requests to render the data, WKWebView handles them asynchronously.

**Eliminates certain touch delays**: UIWebView doesn't handle the touch gestures smoothly, WKWebView has better optimizations to handle them seamlessly.

Apple recommends WKWebView over UIWebView so that apps can leverage the memory and process optimizations, but it depends on what you want to solve, to handle the server requests better one might prefer to use UIWebView, but in general WKWebView is the best.

Here is a good article that describes the intricacies of the [WKWebView](https://github.com/ShingoFukuyama/WKWebViewTips).




