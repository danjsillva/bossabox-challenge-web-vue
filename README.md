# VUTTR (Very Useful Tools to Remember) VueJS App

Welcome to **VUTTR VueJS App**. This app was developed by **Daniel Silva** for the [bossabox](http://bossabox.com) challenge.

NOTE: This document is a **work in progress**.

## Overview

This project was developed in [JavaScript](https://www.ecma-international.org) with [VueJS](https://vuejs.org) framework. That’s uses the [VUTTR API](https://github.com/danjsillva/bossabox-challenge-api).

## Setup

You need [NodeJS](https://nodejs.org/en/) and [NPM](https://www.npmjs.com) or [Yarn](https://yarnpkg.com/en/) to run the commands. This guide uses Yarn but NPM do the same.

Recommended versions:
+ NodeJS: v10.16.0
+ Yarn: 1.16.0

## Running dev server

First, run the following command to install the dependencies.

```bash
yarn install
```

Now you can start dev server by this command.

```bash
yarn serve
```

### That’s all!

The terminal returns this message:

```bash
 DONE  Compiled successfully in 8579ms
 

  App running at:
  - Local:   http://localhost:8080/ 
  - Network: http://10.0.0.51:8080/

  Note that the development build is not optimized.
  To create a production build, run yarn build.

```

This command starts the dev server at port 8080 and open your browser on this page. If your browser not open automatically, you can paste the url and it will works.

### Behind the commands

This project uses some NodeJS packages beyond the VueJS. They are:

+ axios: ^0.19.0
+ bootstrap: ^4.3.1
+ core-js: ^2.6.5
+ node-sass: ^4.12.0
+ sass-loader: ^7.1.0
+ vue: ^2.6.10
+ vue-router: ^3.0.3
+ vuex: ^3.0.1

### Structure of project directories

```bash
.
├── README.md
├── babel.config.js
├── node_modules
│   └── *
├── package.json
├── public
│   ├── favicon.ico
│   └── index.html
├── src
│   ├── App.vue
│   ├── assets
│   │   └── logo.png
│   ├── components
│   │   └── HelloWorld.vue
│   ├── config
│   │   └── api.js
│   ├── main.js
│   ├── router.js
│   ├── services
│   │   └── ToolService.js
│   ├── store.js
│   └── views
│       └── Tools
│           ├── ModalAdd.vue
│           ├── ModalRemove.vue
│           ├── Tool.vue
│           └── Tools.vue
├── vue.config.js
└── yarn.lock
```