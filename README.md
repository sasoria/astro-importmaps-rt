# astro-importmaps

This example shows you how to use importmaps to map dependencies from bare imports to url-imports. The dependencies in this case are react and react-dom and they are imported from [esm.sh](https://esm.sh/).

Using an import map in Layout.astro you can see that react and react-dom are mapped to url imports from en external CDN ([esm.sh](https://esm.sh/)).

```html
<script type="importmap">
  {
    "imports": {
      "react": "https://esm.sh/react",
      "react-dom": "https://esm.sh/react-dom"
    }
  }
</script>
```

React and react-dom are set as externals in astro.config.mjs so that they don't get bundled at build.

```javascript
if (target === "client") {
  vite.build.rollupOptions["external"] = ["react", "react-dom"];
}
```

Note that the packages are imported over Http3 and gets cached in the browser. This means that you don't have to donwload react and react-dom on the second page reload.
