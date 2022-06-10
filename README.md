# Vue 3 + Vite + GSAP + SASS

This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)

&nbsp;
&nbsp;
# Demo POC (Proof of concept)
### Author: Fabio Politi (f.politi@icoa.it)
&nbsp;
## How to use (development)
- clone this repo
- run `npm install`
- run 'npm run dev'
- open the app at [localhost:3000](http://localhost:3000)

&nbsp;
## How to use (production) - (TBC)
- find out the "relative base public path", such as "/static/gsap-demo/"
- run `npx vite build --base=[BASE PATH HERE]`, such as `npx vite build --base=/static/gsap-demo/`
- all the assets and the articats will be generated into the "dist" folder
- transfer all the content of the "dist" folder to the production server (TBC)
- open the file at "dist/index.html", copy the CSS/JS declaration and inject them into another website
- place the markup `<div id="app"></div>` into a CMS page of the outher website
