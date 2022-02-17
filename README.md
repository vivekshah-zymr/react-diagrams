# Introduction

[![Join the chat at https://gitter.im/projectstorm/react-diagrams](https://badges.gitter.im/projectstorm/react-diagrams.svg)](https://gitter.im/projectstorm/react-diagrams?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) [![NPM](https://img.shields.io/npm/v/@projectstorm/react-diagrams.svg)](https://npmjs.org/package/@projectstorm/react-diagrams) [![Package Quality](https://npm.packagequality.com/shield/storm-react-diagrams.svg)](https://packagequality.com/#?package=storm-react-diagrams) [![CircleCI](https://circleci.com/gh/projectstorm/react-diagrams/tree/master.svg?style=svg)](https://circleci.com/gh/projectstorm/react-diagrams/tree/master) [![lerna](https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg)](https://lerna.js.org/)

![](.gitbook/assets/logo.jpg)

**DEMO**: [http://projectstorm.cloud/react-diagrams](http://projectstorm.cloud/react-diagrams)

**DOCS \(wip\)** [https://projectstorm.gitbook.io/react-diagrams](https://projectstorm.gitbook.io/react-diagrams)

Docs are currently being worked on, along with a migration path.

## What

A flow & process orientated diagramming library inspired by **Blender**, **Labview** and **Unreal engine**.

* **Modern Codebase** written entirely in Typescript and React, the library makes use of powerful generics, advanced software engineering principles and is broken up into multiple modules.
* **Hackable and extensible** the entire library including its core can be extended, rewired and re-assembled into fundamentally different software to suit your own software needs.
* **HTML nodes as a first class citizen** the library was originally written to represent advanced dynamic nodes, that are difficult to represent as SVG's due to complex input requirements ux requirements.
* **Designed for process** the library is aimed for software engineers that want to rewire their programs at runtime, and that want to make their software more dynamic.
* **Fast diagram editing** the defaults provided give the highest priority to editing diagrams as fast as possible.

## Gallery

Example implementation using custom models: \(Dylan's personal code\)

![Personal Project](.gitbook/assets/example1.jpg)
![](.gitbook/assets/example2.jpg)

Get started with the default models right out of the box:

![](.gitbook/assets/example3.jpg)

## Installing

For all the bells and whistles:

```text
yarn add @projectstorm/react-diagrams
```

This includes all the packages listed below \(and works \(mostly and conceptually\) like it used to in version 5.0\)

### A more modular approach

This library now has a more modular design and you can import just the core \(contains no default factories or routing\)

```text
yarn add @projectstorm/react-diagrams-core
```

this is built ontop of the evolving **react-canvas-core** library

```text
yarn add @projectstorm/react-canvas-core
```

which makes use of

```text
yarn add @projectstorm/geometry
```

and of course, you can add some extras:

```text
yarn add @projectstorm/react-diagrams-defaults
yarn add @projectstorm/react-diagrams-routing
```

## How to use

Before running any of the examples, please run `yarn build` in the root. This project is a monorepo, and the packages (including the demos) require the packages to first be built.


Take a look at the [diagram demos](https://github.com/projectstorm/react-diagrams/tree/master/diagrams-demo-gallery/demos)

**or**

Take a look at the [demo project](https://github.com/projectstorm/react-diagrams/tree/master/diagrams-demo-project) which contains an example for ES6 as well as Typescript

**or**

[Checkout the docs](https://projectstorm.gitbook.io/react-diagrams/)

## Run the demos

After running `yarn install` and `yarn build`, you must then run: `cd diagrams-demo-gallery && yarn run start`

## Building from source

Simply run `yarn` then `yarn build` or `yarn build:prod` in the root directory and it will spit out the transpiled code and typescript definitions into the dist directory as a single file.

## Built with react-diagrams

> Do you have an interesting project built with *react-diagrams*? PR it into this section for others to see.

## Generate tarball file after code change

Do appropriate code changes in file.
Remove the react-diagram related files from all node_modules folders. (Main node_module and node_module under the packages)
1) Then install all dependencies with original version eg. 6.7.0, by doing `yarn install` from main folder. 
2) Go to package.json of `react-diagram-core`, change package version to `-alpha.X`. After that do `yarn clean` and then `yarn build:prod` from main folder. After that goto `react-diagram-core` and do `yarn pack`, this will generate tarball file (.tgz).
3) Now give that tarball file reference in relevent place like package.json of react-diagram, react-diagram-default, react-diagram-routing. Delete react-diagram related files from all node_moudles folder.
4)Do `yarn install` again, Go to package.json of `react-diagram-default` change package version to `-alpha.X` And then do `yarn clean` and do `yarn build:prod`. that goto `react-diagram-default` and do `yarn pack`, this will generate tarball file (.tgz). 
Now repeate the same step for `react-diagram-routing` and then `react-diagram`
Now copy this all 4 tarball file to your project for use.
