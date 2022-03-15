# LearningApp

A simple project demostrating CRUD operations made with Vue.js 3 and Vue Router 4. No additional database or CSS framework used.

The main idea is to manipulate the data in a given table, which contains information about educational courses.

The web app itself consists of two pages with navigation inbetween. First one is the main page (includes heading + some random text). Second one consists of a form with actions (ADD, UPDATE, DELETE) and a dynamically changing table that represents the result of performed actions. A simple error handling is implemented too.

The whole data from the table is stored in an array with strings. Each string in the array represents a row from the table. The data in each cell of a single row is concatenated with the symbol ' | '.

The web app has a simple error handling for the form. 

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
