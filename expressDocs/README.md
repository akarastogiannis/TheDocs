# Express Js Docs

## Starting a Project
1. Make a dir
2. Run ` npm init `
	> **Note**: Follow the steps of npm init, you can leave everything the same or blank.
4. Run `npm install express`
5. Run `npm install --save-dev nodemon`
	> **Note:** This is to auto restart server after every save.
	> This is **Optional** 
7. In Package.json under **scripts** under **test** type `"start":  "node <nameOfServer>.js"` or type `"start": "nodemon <nameOfServer>.js"` for nodemon.
	> **Note:** This is so that you can use `npm start` when you need to run the server instead of typing the server name each time.
	> This is **Optional**.
8. Then under **main** add `"type":  "module",` 
	> **Note:** This is so that you can use `import` in express
	> This is **Optional**.

## Uninstalling an npm Dependency
**There are many different scenarios**
1. If the package is installed *Locally*
	> Run `npm uninstall <package-name>`

2. If the package is installed as a *dev depency*
	> Run `npm uninstall -S <package-name>`
	> Then Run `npm uninstall -D <package-name>`

3. If the package is istalled *globally*
	> Run `npm uninstall -g <package-name>`

-*Using the -S flag or --save, will aslo remove the reference in the package.json File*

> Written by Athanasios Karastogiannis 

> Written with [StackEdit](https://stackedit.io/).
