---
layout: post
title: Chrome Developer Tools
---

The Chrome Developer Tools (DevTools for short), are a set of web authoring and debugging tools built into Google Chrome. The DevTools provide web developers deep access into the internals of the browser and their web application.<br />
Use the DevTools to efficiently track down layout issues, set JavaScript breakpoints, and get insights for code optimization. <br />
**Accessing the DevTools**<br />
To access the DevTools, open a web page or web app in Google Chrome. Either:<br />
1. Select the Chrome menu  at the top-right of your browser window, then select Tools > Developer Tools. <br />
2. Right-click on any page element and select Inspect Element. <br />
The DevTools window will open at the bottom of your Chrome browser.<br />
There are several useful shortcuts for opening the DevTools:<br />
1. Use Ctrl+Shift+I (or Cmd+Opt+I on Mac) to open the DevTools. <br />
2. Use Ctrl+Shift+J (or Cmd+Opt+J on Mac) to open the DevTools and bring focus to the Console.<br />
3. Use Ctrl+Shift+C (or Cmd+Shift+C on Mac) to open the DevTools in Inspect Element mode, or toggle Inspect Element mode if the DevTools are already open. <br />
4. For your day-to-day workflow, learning the shortcuts will save you time.<br />
**The DevTools window**<br />
The DevTools are organised into task-oriented groups in the toolbar at the top of the window. Each toolbar item and corresponding panel let you work with a specific type of page or app information, including elements, resources, and sources. <br />
Overall, there are eight main groups of tools available view Developer Tools:<br />
1. Elements. <br />
2. Resources. <br />
3. Network. <br /> 
4. Sources. <br />
5. Timeline. <br /> 
6. Profiles. <br /> 
7. Audits. <br />  
8. Console. <br /> 
You can use the Ctrl+[ and Ctrl+] shortcuts to move between panels.<br />
**Inspecting the DOM and styles**<br />
The Elements panel lets you see everything in one DOM tree, and allows inspection and on-the-fly editing of DOM elements.<br /> You will often visit the Elements tabs when you need to identify the snippet for some aspect of the page. For example, you may be curious if an image has an HTML id attribute and what the value is. <br />
**Working with the Console**<br />
The JavaScript Console provides two primary functions for developers testing web pages and applications. It is a place to:<br />
1. Log diagnostic information in the development process. <br />
2. A shell prompt which can be used to interact with the document and DevTools. <br />
You may log diagnostic information using methods provided by the Console . Such as console.log() or console.profile(). <br />
You can evaluate expressions directly in the console and use the methods provided by the Command Line API. These include $() command for selecting elements or profile() to start the profiler. <br />
 Console. 
**Debugging JavaScript**<br />
As the complexity of JavaScript applications increase, developers need powerful debugging tools to help quickly discover the cause of an issue and fix it efficiently. The Chrome DevTools include a number of useful tools to help make debugging JavaScript less painful. <br />
**Improving network performance**<br />
The Network panel provides insights into resources that are requested and downloaded over the network in real time. Identifying and addressing those requests taking longer than expected is an essential step in optimizing your page. <br />
 

**Audits**<br />
The Audit panel can analyze a page as it loads. Then provides suggestions and optimizations for decreasing page load time and increase perceived (and real) responsiveness. For further insight, we recommend using PageSpeed Insights. <br />
 
**Improving rendering performance**<br />
The Timeline panel gives you a complete overview of where time is spent when loading and using your web app or page. All events, from loading resources to parsing JavaScript, calculating styles, and repainting are plotted on a timeline. <br />
 

**JavaScript & performance**<br />
The Profiles panel lets you profile the execution time and memory usage of a web app or page. These help you to understand where resources are being spent, and so help you to optimize your code. The provided profilers are: <br />
1. The CPU profiler shows where execution time is spent in your page's JavaScript functions.<br />
2. The Heap profiler shows memory distribution by your page's JavaScript objects and related DOM nodes.<br />
3. The JavaScript profile shows where execution time is spent in your scripts <br />
**Inspecting storage**<br />
The Resources panel lets you inspect resources that are loaded in the inspected page. It lets you interact with HTML5 Database, Local Storage, Cookies, AppCache, etc. <br />
 Web Starter Kit as displayed in the resources panel. <br />

**Further reading**<br />
There are several other areas of the DevTools documentation that you might find beneficial to review. These include:<br />
1. Heap Profiling. <br />
2. CPU Profiling. <br />
3. Device Mode & Mobile Emulation. <br />
4. Remote Debugging. <br />
5. DevTools Videos. <br />

