## Installation and Setup
1. Node.js (active LTS or maintenance LTS)
2. npm (include with Node.js)
3. Angular CLI

## Installation of Angular CLI
Install the cli:
``` Shell
npm install -g @angular/cli
```

View the ng version:
``` Shell
ng version
```

![[Pasted image 20231208191451.png]]

## Setting up your project
1. Rename the extracted folder to "homes-app"
2. cd homes-app
3. nmp install -- this command will install all the dependencies needed to run the application.

## Testing
``` Shell
ng serve
```

This command starts a local development server. Server is accessible with `localhost:4200`.

## Code editor
To edit the code we will use VSCode. Install Angular Language Service extension.

## Contents of the starting project folder
* angular.json -- there are setting for build configuration internationalization, and more.
* package.json -- project dependencies.
* tsconfig.json -- Typescript settings.
* src/ -- our application lives in this directory.
* app.component.ts -- contains the HTML template code.
## Lets change a page
Open src/app/app.components.ts and change `Hello World!` to `Hello Universe!`. Because our app running in ng serve the page will update it self.

## Resources:
1. https://youtu.be/UnOwDuliqZA?si=gAqAi3_HsyEBX-no