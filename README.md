# How to Setup tailwind in turborepos.

### Setting in Packages
Create a confige folder in your package/ui

something like this
```js
//create package.json
{
    "name": "@gaurav/configs",
    "version": "0.0.0",
    "private": true
}
```

>it is good to use organisation so that it is not conflict with the other packages.

create another tailwind folder under `package/ui/config`

```js
//tailwind.config.js
module.exports = {
    content: [
      "../../packages/ui/**/*.{js,ts,jsx,tsx}",
      "./**/*.{js,ts,jsx,tsx}",
      "./pages/**/*.{js,ts,jsx,tsx}",
    ],
    theme: {
      extend: {},
    },
  };
```
  

```js
//postcss.config.js
module.exports = {
    plugins: {
      tailwindcss: {},
      autoprefixer: {},
    },
  };
```  
  
### Using it in workspace

If you want to use it in any workspace  `apps/any-apps` you can simply create the two files in that workspace `tailwind.config.js` and `tailwind.config.js` .

```js
//tailwind.config.js
module.exports = require("@gaurav/configs/tailwind/tailwind.config");
```

```js
//postcss.config.js
module.exports = require("@gaurav/configs/tailwind/postcss.config");
```
  
 import the `ui/style.css` file in the main `.jsx` file and you are good to go.

---
⭐Please star this repo if it help you in any way.

---