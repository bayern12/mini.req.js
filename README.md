# mini.req.js
tiny,mini,easy,light weight http client (request) framework for both browser and nodejs

## thanks
first thanks to CentraRequest and reeq


## how 2 dev

using microbundule
```bash
npm run build

cp -f dist/min.req.umd.js test/static/req.min.js

npm i -g aok.js

aok test -s test/static -p 10000

#http://localhost:10000/index.html

```
or 
using browserify

```bash
npm i -g browserify
browserify -r ./index.js:min.req.js -o test/static/min.req.js

npm i -g aok.js

aok test -s test/static -p 10000

#http://localhost:10000/index.html
```

## install
in your javascript project
```bash
npm i -S mini.req.js
```
in your HTML <body> 
```html
<script src="js/mini.req.js"></script>
```
ps: download : [mini.req.js](./mini.req.js)

## just do it
```js
    //when node or browserify :  require('min.req.js')
    //when in html :  just try miniReq
    var req = require ? require('min.req.js') : miniReq
    req('http://localhost:10000/abc', 'get', {
        hello: 'good good day'
    }).then(
        d => {
            console.log(d)
        }
    )

    req.get('http://localhost:10000/abc?a=1', {
        hello: 'get'
    }).then(
        d => {
            console.log(d.data)
        }
    )

    req.post('http://localhost:10000/ssabc', {
        hello: 'post'
    }).then(
        d => {
            console.log(d.data)
        }
    )

    req.put('http://localhost:10000/abc', {
        hello: 'put'
    }).then(
        d => {
            console.log(d.data)
        }
    )

    req.delete('http://localhost:10000/abc?a=2', {
        hello: 'del'
    }).then(
        d => {
            console.log(d.data)
        }
    )
```


## publish
```bash
npm run build
mv -f dist/mini.req.umd.js ./mini.req.js
rm -f dist/mini.req.esm.js
rm -f dist/mini.req.modern.js
npm publish 

```