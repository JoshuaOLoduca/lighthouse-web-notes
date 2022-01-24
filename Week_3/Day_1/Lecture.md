# Web servers 101
## Notes
Basic web server overview
1. Listens for incoming requests
2. http is a client-server text based protocol
3. returns text based data

<hr>

```response.write()``` must have ```response.end() ```used with it to tell client to stop waiting for new info
<hr>
HTTP uses TCP along with other stuff under the hood
<hr>

```js
app.set('view engine','ejs')

res.render('pageName')
```

EJS for templating .html with expressServer

rename .html to .ejs
(alternatives are Pug, handlebar and others)

<hr>

```js
const path = require('path');
// indicated location of static assets
express.static(path.join(__dirname), 'public');
```

public folder for statis resources for EJS (IE: css, imgs, javascript, etc)