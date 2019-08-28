# 🚨Breaking the Build! 🚨

## Episode 02: Surviving the Crash

> https://www.youtube.com/watch?v=rUeztOMhlU4

![https://www.youtube.com/watch?v=rUeztOMhlU4](./breaking-the-build-episode-02.png)

* [Episode 02: Surviving the Crash](#episode-02-surviving-the-crash)
* [📝 Description](#-description)
* [💻 Code](#-code)
	* [Initializing the module](#initializing-the-module)
	* [Leaving Breadcrumb Trail](#leaving-breadcrumb-trail)
	* [Adding User Metadata](#adding-user-metadata)
	* [Logging an Error (Handled Exception)](#logging-an-error-handled-exception)
	* [Allow User to Opt-Out](#allow-user-to-opt-out)
* [🔗 Links](#-links)
* [👏 Credits](#-credits)
* [📚Learn More](#learn-more)
* [📣 Feedback](#-feedback)


## 📝 Description

> 😱 Your mobile app has crashed!! Don't panic! All is not lost!  In this episode we walk you through surviving the crash and quickly getting your app up and running again by using Mobile Crash Analytics!  


Subscribe to our channel and hit the 🔔 to get notified when we've posted a new episode!

Enjoy this episode? 👍 Like our video and share it!

This show was created by the Axway Developer Relations Team and many others at Axway!

## 💻 Code


### Initializing the module

> This will initialize the crash analytics module after `com.appcelerator.aca` has been added to `tiapp.xml`

```JavaScript
const aca = require('com.appcelerator.aca');
```


### Leaving Breadcrumb Trail

> This code will help you track down any problems by allowing you to log where/what you have done in the app.  These are only reported in the case of a handled exception or crash.

```JavaScript
aca.leaveBreadcrumb('Opening screen:' + myscreen.id);
```

### Adding User Metadata

> This code will help you track down any problems by allowing you to log where/what your users have done in the app

```JavaScript
aca.setUsername(username);
aca.setMetadata('lastLogin', datetime);
aca.setMetadata('gameLevel', 0);
```


### Logging an Error (Handled Exception)

> This code will allow you to track down exceptions/errors that may not cause a crash but are needed to help identify potential issues.

```JavaScript
try {
    var err = new Error('FATAL ERROR: Value cannot be null or undefined!');
    if (value === null || value === undefined) throw err;
} catch (err) {
    aca.logHandledException(err);
}
```

### Allow User to Opt-Out

> This code allows you to have to user opt-out of sending any crash analytics.  Nothing will appear in report for this user if they do this.

```JavaScript
// Disable sending data to Crash Analytics
aca.setOptOutStatus(true);

```



## 🔗 Links

* AMPLIFY Crash Analytics - https://breakingthebuild.dev/crash
  

## 👏 Credits

* Executive Producer:  Todd Holbrook 
* Marketing and Communications: Erin Bailey
* Host / DevRel:  [Brenton House](https://brenton.house)


## 📚Learn More

Check out the developer resources available below!

* Axway Developer Blog - https://devblog.axway.com
* Axway Titanium Overview - https://breakingthebuild.dev/titanium
* Axway Developer Slack Channel - https://breakingthebuild.dev/slack
* Axway Developer Portal - https://developer.axway.com/


## 📣 Feedback

Have an idea or a comment?  [Join in the conversation here](https://github.com/axway-developer-relations/breaking-the-build/issues)! 


