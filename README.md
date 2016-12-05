# sailsjs-handlebars-app
Sails app using handlebars templating engine

Step-by-step

* create a new app
```sh
sails new sailsjs-handlebars-app
```

* install handlebars
```sh
npm install handlebars --save
```

* update configured templating engine
```javascript
// config/views.js

// ...
engine: 'handlebars',
// ...

```

* change extension of your view files
```sh
 cd views && for old in *.ejs; do mv $old `basename $old .ejs`.handlebars; done && cd ..
```

* update content of existing view files, so that they reflect handlebars syntax
```javascript
// views/layout.handlebars
// views/homepage.handlebars
// views/403.handlebars
// views/404.handlebars
// views/500.handlebars
```

* change extension used inside `sails-linker.js`
```javascript
// tasks/config/sails-linker.js
// example
// ...
'views/**/*.ejs': require('../pipeline').jsFilesToInject
// to
'views/**/*.handlebars': require('../pipeline').jsFilesToInject
// ...

```

Resource:
* [Sails](http://sailsjs.org)
