# ng-goes-native

## One Framework To Rule Them All

Complete setup for developing multi platform solutions with Angular, NativeScript and Electron.JS

![One Framework To Rule Them All](one_ring_to_rule_them_all.gif)

### Motivation

- Business logic is platform independant
- Using familiar technology
- Having the native experience 

## Setup

### Generating The Shared Angular & NativeScript project

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 6.1.0 with NativeScript schematics included. Shared flag transforms the project to shared Angular & NativeScript project. 

```bash
ng new --collection=@nativescript/schematics --style=scss --shared <appname>
```

More about Angular Schematics can be found on the [Angular Docs](https://angular.io/guide/schematics) page.

More on using the [NativeScript Angular Schematics](https://github.com/NativeScript/nativescript-schematics).

### Adding the Electron.JS Dev Dependency

[Electron.JS](https://electronjs.org/docs/all) is an Open Source Framework for creating native applications with web technologies like JavaScript, HTML, and CSS. It takes care of the hard parts so you can focus on the core of your application.

```bash
npm install electron --save-dev
```

Also, the electron-packager is added as a Dev Dependency as we are going to use it as a [Application Distribution](https://electronjs.org/docs/tutorial/application-distribution) tool.

```bash
npm install electron-packager --save-dev
```

And in order to deploy our Electron App, we are going to use this command:

```bash
electron-packager <sourcedir> <appname> --platform=<platform> --arch=<arch> [optional flags...]
```

### Adding a service worker to the project

To set up the Angular service worker in your project, use the CLI command ng add @angular/pwa. It takes care of configuring your app to use service workers by adding the service-worker package along with setting up the necessary support files.

```bash
ng add @angular/pwa
```

Also, for testing our PWA app, we'll need some HTTP Server.

```bash
npm install lite-server --save-dev
```

After that, we'll need to build our app.

```bash
ng build --prod
```

And then we can start our local HTTP server.

```bash
lite-server --baseDir=dist/<appname>
```
