`npm install eslint@7.12.1 eslint-cli babel-eslint --save-dev`

The eslint command takes a JavaScript file as an argument. For example, if you have a JavaScript file called test.js, you can run ESLint against the file like this:
- $ npx eslint test.js

You should place the information in a file named .eslintrc.yml. 

When you run ESLint, it looks for this file (and others) in the current directory or the closest parent directory that contains a usable configuration file.

But it does not look in your home directory.

The easiest way to leverage this search is to put your default .eslintrc.yml file in a directory that contains all of your projects as subdirectories.

.eslintrc.yml will be a hidden file once created in the directory
