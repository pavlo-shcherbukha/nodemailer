# Node.js Generate express template

## generate node-extpress template

### install express generator

```bash
npm install express-generator -g
```

### generate application template in application directory

```bash
express --view=pug
```

pug - html generator.
supported type are: *(ejs|hbs|hjs|jade|pug|twig|vash)*.

### install dependies in application directory

```bash
npm install
```

### start application

```bash
 npm start
```

actually look at the package.json
in real you can start aplication directly using [node ./bin/www]

```js
{
  "name": "git-nodeapp1",
  "version": "0.0.0",
  "private": true,
  "scripts": {
    "start": "node ./bin/www"
  },
  "dependencies": {
    "cookie-parser": "~1.4.4",
    "debug": "~2.6.9",
    "express": "~4.16.1",
    "http-errors": "~1.6.3",
    "morgan": "~1.9.1",
    "pug": "2.0.0-beta11"
  }
}

```

## Helpful links

[Atom editor и Nodejs — быстрый старт](http://aftamat4ik.ru/atom-i-nodejs-quick-start/)

[various Node.js related source code samples, articles, tutorials, and tips.](https://www.c-sharpcorner.com/technologies/nodejs)

[node.js express link](http://expressjs.com/en/4x/api.html#app.use)

## Node Patterns

### app.use()

Application-level middleware

Bind application-level middleware to an instance of the app object by using the app.use() and app.METHOD() functions, where METHOD is the HTTP method of the request that the middleware function handles (such as GET, PUT, or POST) in lowercase.
This example shows a middleware function with no mount path. The function is executed every time the app receives a request.
Detainls about app router see [Router-level middleware](http://expressjs.com/en/guide/using-middleware.html#middleware.router)

### Morgan logger

```js
var logger = require('morgan');
```

Morgan используется для регистрации деталей запроса.

## logger log4js

We use log4js for different perposes

### Add it

```js
// psh log4js
const log4js = require('log4js');
```

### Config it

```js
// ====================================
// psh: log4js
//ERROR — приложение в критическом положении, требуется внимание человека для продолжения. Появляется довольно редко, но метко. Я использую его для очень низкоуровневых вещей или для необработанных исключений
//WARN — произошло что-то необычное, выбивающееся из обычного сценария, но приложение умное и восстановило свою работу само. Я использую этот уровень в обрабочиках ошибок.
//INFO — что сейчас происходит
//DEBUG — что сейчас происходит, более подробно
//TRACE — пишем как в твиттер, все что не попадя.
//~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~`
log4js.configure({
  appenders: {
    console: { type: 'console' },
    file: { type: 'file', filename: 'logs/cheese.log' }
  },
  categories: {
    applog: { appenders: ['file'], level: 'trace' },
    default: { appenders: ['console'], level: 'trace' }
  }
 });
```

### Activate loggers

```js
//logger for console
const log4c = log4js.getLogger('default');
// logger for file
const log4f = log4js.getLogger('applog');


//logger.level = 'DEBUG' || 'info'
app.use(log4js.connectLogger(log4c, { level: 'trace' }));
app.use(log4js.connectLogger(log4f, { level: 'trace' }));
```

### write to logger

```js
log4c.info('CONSOLE:  LOGGER ACTIVATED');
log4f.info('FILE:  LOGGER ACTIVATED');
```

### Use it in other modules

```js
var log4js = require('log4js');

// in router function
   const log4c = log4js.getLogger('default');
   const log4f = log4js.getLogger('applog');

  log4c.info( 'log4c.console' + hirouter);
  log4f.info( 'lof4f.file' + hirouter);
```

 My Question: How cen we get it from app.use
