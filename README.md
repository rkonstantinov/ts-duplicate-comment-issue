This is a test project which to illustrate the duplicate comments issue with TypeScript 2.1.4.

### The Issue
It seems that if the file starts with a comment (either block or line), 
running tsc will result in duplication of this comment in the generated JavaScript file.

### Steps to reproduce:
1. execute `npm install` in order to install typescript
1. generate the js files by running `node_modules/.bin/tsc`
1. view the generated file `cat src/utils.js`
1. you should notice that file content looks similar to the following:
```javascript
/**
 * @hidden
 */
/**
 * @hidden
 */ export var foo = "bar";
```
Note the duplication of the comments
