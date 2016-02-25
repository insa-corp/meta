# Dependencies

Most web applications strongly rely on third party libraries, modules, frameworks, etc. A good understanding the main
package managers might be helpful.

## Package Managers ##

Package Managers are services that maintain public registries of available modules. *insa-frif* uses mostly 3 package
managers:

 * [npm](http://npmjs.com/): This is one of the very first package managers for the web. It was first created for Node.js
  but can now also serve files for browsers. Is the most important package managers due to it's tight integration with Node.js
  and huge number of libraries. Every library must be installed at least with npm.
  
 * [jspm](http://jspm.io/): This package manager is more focused on dependencies used in the browser. It acts as successor
  to [bower](http://bower.io/). Like bower, it has always used a browser-friendly flat structure; but unlike bower, JSPM
  handles the configuration steps automatically. The modules installed with JSPM cannot be loaded directly, they must be
  loaded with the [SystemJS](https://github.com/systemjs/systemjs) loader. It's a powerful loader for the browser
  (with the possibility to transpile files in the browser or bundle various scripts together), but it comes with limitations
  when used in Node.js (ie. the current directory `__directory` becomes unavailable)
  
 * [Typings](https://github.com/typings/typings): This recent package manager handles Typescript defintion files (`*.d.ts`).
  It is a replacement for [DefinitelyTyped](http://definitelytyped.org/), a popular definitions repository. Typings attends
  to solve the main issues of DefinitelyTyped: everyone can publish its typings directly from it's own repository (all the typings
  no longer live in a single colossal repository) and it promots external over ambient modules (local over global) and allows
  to solve the various conflicts arising from using DefinitelyTyped
  
## Adding a dependency ##

To add a dependency, you must know what you plan to do with this dependency. Answer the following questions to know which
package manager to use.

````text
Do you want to use this dependency ?
 => You NEED npm

Are-you going to use it in the browser ?
 => You NEED jspm

The dependency is written in plain old JS AND you want to import it in at least one Typescript file ?
 => You NEED typings
````

### npm ###

Are you going to use this library during your application's runtime ?
````bash
npm install --save <lib>
````
Otherwise, if you plan to use it only during the build or test process:
````bash
npm install --save-dev <lib>
````

### jspm ###

````bash
jspm install <lib>
````

### typings ###

Since *typings* is relatively recent and acts as a successor to *DefinitelyTyped*, some modules might not be available yet as
external modules but only as ambient modules from *DefinitelyTyped*.

First, we try to install it as a standard external module:
````bash
typings install -S <lib>
````
If the library is not found, we try to fall back on *DefinitelyTyped* ambient modules:
````bash
typings install -SA <lib>
````

If the definitions are neither on *typings* or *DefinitelyTyped*, [we will need to write our own...](http://www.typescriptlang.org/Handbook#writing-dts-files)
