# Descriptions

## QUnit CLI issues
When running qUnit tests through the console, the tests are dynamically loaded using CommonJS.
If tests are written in the style of ES6 modules, then the test validation will
 fail because CommonJS does not support exporting ES6 modules.

## Fix
To fix the situation of dynamic loading of ES6 modules in the CommonJS context, 
dynamic loading by this component is performed using the import () function.
Thus, through `import ()` you can load both CommonJS style tests and ES6 module style tests.

# Install 


    
# Run

Command `quinit-m` takes the same options and performs the same actions as the command `qunit`   

`npx quinit-m -h`  - Qunit for Module ES6

# Other

If your component uses CommonJS loading tests and ES6 module loading tests,
it is recommended to separate such tests by extensions. `test.cjs` - CommonJS,` test.mjs` -module ES6.
Otherwise, conflicts may arise, since files with the `js` extension will use
module loader according to the `type` parameter in` package.json`.

