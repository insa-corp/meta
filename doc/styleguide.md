# Style Guide

The aim of this guide is to provide a set of rules to provide high-quality code:

 * __Consistency__ accross the different files accross our projects as well as to third-party libraries
 * __Readability__ to understand others code quicker, locate files, etc.
 * __Maintainability__ by preventing mistakes
 
## Project

### Structure

### VCS

### Versioning

See [SemVer](http://semver.org/).

### Changelog

## Naming

### File names

__Rule__: File names should only use lowercase. This does include directory names.

__DO__: `main.ts`, `_partial.scss`, `hello-world`, `contacts-list.jade`, `some-class.ts`

__DO NOT__: `Main.ts`, `_PARTIAL.SCSS`, `hello_world`, `contactslist.jade`, `SomeClass.ts`

__Explanation__: Sharing code between case-sensitive and case-insensitive file systems might lead to issues like
 duplicated files, non-detected renames, file path errors, inconsistencies induced by the VCS, etc. As Windows - one
 of our targeted platforms - has a case-insensitive file system, we prefer to refrain from using various case in file names. The use
 of dashes as logical separators (instead of simple concatenation or underscores) is a convention for most web projects.

__Exception__: Due to historical reasons, the readme file should be called exactly `README.md` and the license file `LICENCE.md`.

## Formatting

### Indentation

__Rule__: Indent with 2 spaces

__Explanation__: Indentation might lead to numerous debates but we have to settle on one single choice. Not only it is a
 prominent element of the formatting, some file formats (mainly Jade files) are sensitive the indentation so it becomes
 critical to only use one style of indents. Spaces were chosen in favor of tabs because they guarantee consistency
 between any software (terminal, editor, browser, etc.): even if tabs are cool, spaces are the solution mostly used by
 collaborative projects.

### Braces

__Rule__: Use K&R style

__DO__:

````typescript
if (condition) {  // no spaces inside parentheses
  ...  // 2 space indent.
} else if (...) {  // Braces are one the same line as the statement
  ...
} else { // The else goes on the same line as the closing brace.
  ...
}
````

````scss
body {
  color: red;
}
````

__Explanation__: Style of 99.9% projects.

## Documentation

## References

### Projects

 * [Express](https://github.com/expressjs/express/tree/master)
 * [Lodash](https://github.com/lodash/lodash)
 * [Bluebird](https://github.com/petkaantonov/bluebird)

### Documents
