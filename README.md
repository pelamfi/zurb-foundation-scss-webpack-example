# Zurb Foundation with SCSS and Webpack Example Project
This is an example project demonstrating one way to set up Zurb Foundation as basis development with Npm and Webpack.

I put this example together after I failed to find an example project my self. Hope this helps somebody!

Here is a quick rundown of features in this example project:

 * [Zurb Foundation](https://foundation.zurb.com/) installed with Npm to  to `node_modules
 * Zurb Foundation [SCSS](https://sass-lang.com/guide) processed with [Webpack Sass Loader plugin](https://github.com/webpack-contrib/sass-loader#sass-loader)`
 * SCSS based layout development on top of the Foundation
 * [Webpack with auto reloading](https://webpack.js.org/configuration/dev-server/) for development

## Prebuilt demo
[Here is a prebuilt demo index.html](https://pelam.fi/zurb-foundation-scss-webpack-example/)

## Quick start webpack server
This way the page reloads when you edit the sources!

```sh
npm install

# start the  webpack server
npm run server 
```

Then open http://localhost:8000.

## Quick start with files built by webpack
In this mode webpack will rebuild files automatically when sources
are changed. You just have to reload the page.

```sh
npm install

# start the webpack process to build and rebuild files
npm run webpack
```

Then open `build/index.html` in a browser

## Build for Production

```sh
npm run webpack:production
```

## Interesting files
Start experimenting by changing these files
  * [zurb-foundation-sample-index.html](src/zurb-foundation-sample-index.html) An official example page that I borrowed to this project from the Zurb Foundation standalone distribution
  * [index.html](src/index.html) A small html file using the Foundation that I whipped together my self
  * [app.scss](scss/app.scss) The "root" SCSS that then imports and includes stuff from the Zurb Foundation. This file can be used for fine grained control on what parts of the Foundation to use (or just take everything). This file is then processed by the Webpack and embeded in the generated `Index.js`.
  This file is also a good place to start putting your own SCSS code.
  * [index.js](src/index.js) The "root" Javascript that imports the `app.css` above. This file also imports the Foundation Javascript components. This file is then processed by the Webpack and embeded in the generated `Index.js`. This file is also a good place to start putting your own Javascript code.

## LICENSE

Everything in this repo (this README, bunch of configuration and index.html, but see exception below) is licensed with the very liberal
[UNLICENSE](LICENSE.txt). Feel free to use.

As an exception, the file  [zurb-foundation-sample-index.html](src/zurb-foundation-sample-index.html) belongs to the
creators of Zurb Foundation, so consider deleting it after you clone this repository.
  
## TODO

  * Support for separate CSS resource in production mode to avoid [FOUC](https://en.wikipedia.org/wiki/Flash_of_unstyled_content)