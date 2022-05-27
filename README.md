# Tailwind CSS Hello World

Just running through the basics, May 2022

https://tailwindcss.com/docs/installation

## Steps

### Installation

```
npm install -D tailwindcss

npx tailwindcss init
```

File structure after running through:

```
ali@stinky:~/git/tailwind-css-hello-world$ ls *
index.html  package-lock.json  README.md  tailwind.config.js

dist:
output.css

node_modules:
acorn              glob-parent     postcss-js
acorn-node         has             postcss-load-config
acorn-walk         is-binary-path  postcss-nested
anymatch           is-core-module  postcss-selector-parser
arg                is-extglob      postcss-value-parser
binary-extensions  is-glob         queue-microtask
braces             is-number       quick-lru
camelcase-css      lilconfig       readdirp
chokidar           merge2          resolve
color-name         micromatch      reusify
cssesc             minimist        run-parallel
defined            nanoid          source-map-js
detective          @nodelib        supports-preserve-symlinks-flag
didyoumean         normalize-path  tailwindcss
dlv                object-hash     to-regex-range
fast-glob          path-parse      util-deprecate
fastq              picocolors      xtend
fill-range         picomatch       yaml
function-bind      postcss

src:
input.css
```

Doesn't cover getting page served with the output css; adding a nginx docker to serve this up;

```
$ cat Dockerfile
FROM nginx:latest

COPY ./dist /usr/share/nginx/html/dist
COPY ./index.html /usr/share/nginx/html/index.html

$ docker build -t webserver .
$ docker run -d -p 8080:80 webserver
```

then visit: http://localhost:8080/
