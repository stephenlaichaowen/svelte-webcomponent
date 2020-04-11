## Build Web Component with Svelte

### How to create a web component with svelte

First we create svelte project that specifically made for web component
```
npx degit sveltejs/component-template my-component
```

After project has been created, you can find `index.js` and `Component.svelte` inside `src` directory `Component.svelte` is where our component lives. We add this code into the file. 
```
<script>
  export let name = ""
</script>

<!-- this is how we set the name of our web component -->
<svelte:options tag="my-component" />

<h1>
  Hi, my name is {name}
</h1>
```

In order to tell svelte this is a web component, we add this code to `rollup.config.js`
```
plugins: [
  svelte({ customElement: true }),
]
```

Then install all the dependencies
```
npm i
```

Generate production-ready web component, this will generate `dist` directory with`index.js` and `index.mjs` 
```
npm run build
```

### How to use web component

Create an `index.html` under root directory

Import `index.mjs` , this is our web component
```
<head>
  ...
  <script src="dist/index.mjs" type="module"></script>
</head>
```

Involke component
```
<body>
  <my-component name="Stephen Lai"></my-component>
</body>
```











