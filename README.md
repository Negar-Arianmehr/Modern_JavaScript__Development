# Modern_JavaScript__Development
https://www.udemy.com/course/the-complete-javascript-course/#JavaScript_Asynnchronouswith  : training

JS developer used to write all their codes into one big script  or maybe multiple scripts. But today, we divide our projects into multiple modules and these modules can share data between them and make our code more organized and maintainable.
One great thing about modules is taht we can also include 3rd-party modules(any code that has been written by a third party.) into our own code, and there are thousands of open source modules, which we also call packages, that developers share on the NPM repository. We can use these pakages for free in our own code.
For example, the popular React framwork or jQuery, or even the Leaflet library. All of these pakages are available through NPM. Now NPM stands for Node Pakage Manager, because it was orginally developed together with Noode.js and 4Node.js. However, NPM has established itself as the go to repository for all kinds of pakages in Modern JavaScript Development.
In order to download and use and share packages, we use the NPM software installed on our computer. And this is used a simple command line interface that allowa us to do all that.
So basically NPM is both the repository in which packages live and a program that we use on our computers to install and manage these packages.
# Build Process:
**Bundling** and **Transpiling/Polyfilling** >>> JavaScript Bundle
 At the end, our project needs a build process, where one big final JS bundle is built(which we will deploy to our web server for production). Basiclly it is the JS file that will be sent to browsers in production. Production means that the application is being used by real users in the real world. Now a build process can be something really complex, but for making it easier, include it two steps.
1. The first one: **BUNDLING** we will bundle all our modules together into one big file.
This is a really complex process which can eliminate unused code and compress our code as well. This step is imprortant, first because older browsers dont support modules at all, so the codes that is in the module couldnt be executed by any older browser. And second, it is also better for performance to send less files to the browser, and it is also beneficial that the bundling step compresses our code. 
2. As the second step: **TRANSPILING/POLYFILING** we do something called **transpiling and polyfiling** which is basically to convert all modern JS syntax and features back to old ES5 syntax, so that even older browsers can understand our code without breaking >>> THIS IS USULLY DONE USING A TOOL CALLED **BABLE**.
These two steps of our build process and after this two steps, we end up with that final JS bundle, ready to be deployed on a server for production. Now of course we dont perform these two steps ourselves. Instead we use a special tool to implement this build process for us.
The most common buil tools available, are probably **Webpack** and **Parcel** and these are called JavaScript Bundlers. As the name says they take our raw code and transform it into a JavaScript bundle. 
**The Wepack**  is the more popular one, but it can be really hard and confusing to set it up. That is because there is a lot of stuff that we need to configure manually, in order to make it work properly.
**Parcel**, on the other hand is a ziro configuration bundler, which simply works out of the box. We dont have to write any set up code, which is really amazing.
These development tools are actually also available on NPM.
# Modules in Javascript
Modules are a super important part of sotware developer.
The module is a reusable pice of code that encapsulates implementation details of a certain part of our project. Now that sounds a bit like a function or even a class, but the difference is that a module is usually a standalone file. Normally when we think of a module we think of a separate file. The module comtains some code but it can also have imports and exports. So we can export the value out of a module that is called the **public API**. It is like classes where we can also expose a public API for other code to comsume. Now in the case of modules, this public API is actually consumed by importing values into a module.
When we import the values from other module called **dependency**(dependencies of the importing module).
**Advantages of using modules**
1. Compose software: Modules use in many of languages and make it really easy to copose software. We can think of modules as small building blocks that we can then put together in order to build really complex applications.
2. Isolate components: Modules can be developed in isolation without thinking about the entire codebase.
3. Abstract code: Implement low-level code in modules and import these abstractions into other modules.
4. Organized code: Modules naturally lead to a more organized codebase.
5. Reuse code: modules allow us to easily reuse the same code, even across multiple projects.
So as of ES6, JS has a native built-in module system. We did have modules before ES6, but we had to implement them ourselves or use external libraries.
ES6 modules are the modules that are actually stored in files and each file is one module. So there is exactly one modules per file.
**different between old school scripts and modern ES6 modules:
1.	The first difference is that in modules all top level variables are scooped to module. So variables are private to the module by default. And the only way that outside of module can access value that is inside of a module is by exporting that value. Now in scripts, on the other hand, all top level variables are always global, and this can lead to problems like global namespace pollution, where multiple scripts try to declare variables with the same name and then these variables collide. So private variables are the solution to this problem. That is why ES6 modules implemented it like this.
2.	ES6 modules are always executed in strict mode while scripts on the other hand, are executed in sloppy mode by default. So with modules, there is no more need to manually declare strict mode.
3.	This keyword is always undefined at the top level while in scripts it points at the window object.
4.	We can import and export values between modules using this ES6 import and export syntax. In the regular scripts, importing and exporting values is just completely impossible.
5.	In order to link a module to an Html file, we need to use the script tag with the type attribute set to module, instead of just a plain script tag.<script> for Script, <script type="module">.
6.	About downloading the module files themselves, it always automatically happens in an asynchronous way. But regular script are downloaded by default in a blocking synchronous way. Unless we use the async or differ attributes on the script tag.
# modules behind the scenes:
For instance, we import some values from modules to another. When a piece of the code is executed, the first step is to **parse** that code. The parsing means to just read the code but without executing it. And this is the moment in which imports are hoisted(Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution). The whole process of importing modules happens before the code in the main module is actually executed. Modules are importing synchronously. Possible thanks to top-level("static") imports, which make imports known before execution. And this makes bundling and dead code elimination possible.
 After the parsing process, hostel will be figured out which modules it needs to import, then these modules are actually downloaded from the server. Downloading happen in an asynchronous way. It is only the importing operation itself that happens synchronously. Then after a module arrives, it's also parsed and the modules exports are linked to the imports in index.js. So exported values are not copied to imports. Instead, the import is basically just a reference to the export at value like a pointer. So when the value changes in the exporting module, then the same value also changes in the importing module. And this is quite important to understand because it's unique to ES6 modules.
 # Exporting and impoeting in ES6 module:
 We know the variables are scoped to its module, If we want to use them in the script.js module then we would have to use exports.
 In ES modules, there are rwo types of exports named Exports and Default Exports. Named imports is actually the simplest way of exporting something from a module, because all we have to do is to put export in front of anything, that we might want to export.
For Named import in script.js, we have to give them the same name that is in module and we have to put them inside curly braces {}. We can also export multiple things, at the same time, using Named Exports. We can also change the name of variable in script with add prename as newName in curly baces.

