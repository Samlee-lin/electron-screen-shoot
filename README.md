# electron-vite-react

[![awesome-vite](https://awesome.re/mentioned-badge.svg)](https://github.com/vitejs/awesome-vite)
![GitHub stars](https://img.shields.io/github/stars/caoxiemeihao/vite-react-electron?color=fa6470&style=flat)
![GitHub issues](https://img.shields.io/github/issues/caoxiemeihao/vite-react-electron?color=d8b22d&style=flat)
![GitHub license](https://img.shields.io/github/license/caoxiemeihao/vite-react-electron?style=flat)
[![Required Node.JS >= v14.17.0](https://img.shields.io/static/v1?label=node&message=%3E=14.17.0&logo=node.js&color=3f893e&style=flat)](https://nodejs.org/about/releases)

English | [įŽäŊä¸­æ](README.zh-CN.md)

## Overview

đĻ Out of the box  
đ¯ Based on the official [react-ts](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) template, less invasive  
đą Extensible, really simple directory structure  
đĒ Support using Node.js API in Electron-Renderer  
đŠ Support C/C++ native addons  
đĨ It's easy to implement multiple windows  

## Quick start

```sh
npm create electron-vite
```

![electron-vite-react.gif](https://github.com/electron-vite/electron-vite-react/blob/main/public/electron-vite-react.gif?raw=true)

## Debug

![electron-vite-react-debug.gif](https://github.com/electron-vite/electron-vite-react/blob/main/public/electron-vite-react-debug.gif?raw=true)

## Directory structure

*đ¨ By default, the files in `electron` folder will be built into the `dist/electron`*

```tree
âââ electron                  Electron-related code
â   âââ main                  Main-process source code
â   âââ preload               Preload-script source code
â   âââ resources             Resources for the production build
â       âââ icon.icns             Icon for the application on macOS
â       âââ icon.ico              Icon for the application
â       âââ installerIcon.ico     Icon for the application installer
â       âââ uninstallerIcon.ico   Icon for the application uninstaller
â
âââ release                   Generated after production build, contains executables
â   âââ {version}
â       âââ {os}-unpacked     Contains unpacked application executable
â       âââ Setup.{ext}       Installer for the application
â
âââ public                    Static assets
âââ src                       Renderer source code, your React application
```

## đ¨ `dependencies` vs `devDependencies`

**Put Node.js packages in `dependencies`**

**e.g.** `electron-store` `sqlite3` `serilaport` `mongodb` ...others

**Put Web packages in `devDependencies`**

**e.g.** `react` `react-dom` `react-router` `mobx` `zustand` `antd` `axios` ...others

See more đ [dependencies vs devDependencies](https://github.com/electron-vite/vite-plugin-electron-renderer#dependencies-vs-devdependencies)

## đ¨ Node.js ESM packages

**e.g.** `node-fetch` `execa` `got` ...

[đ Using Node.js ESM packages in Electron-Renderer](https://github.com/electron-vite/vite-plugin-electron-renderer#-nodejs-esm-packages)

<!--
- First, you need to know if your dependencies are needed after the application is packaged.

- Like [serialport](https://www.npmjs.com/package/serialport), [sqlite3](https://www.npmjs.com/package/sqlite3) they are node-native modules and should be placed in `dependencies`. In addition, Vite will not build them, but treat them as external modules.

- Dependencies like [Vue](https://www.npmjs.com/package/vue) and [React](https://www.npmjs.com/package/react), which are pure javascript modules that can be built with Vite, can be placed in `devDependencies`. This reduces the size of the application.
-->
