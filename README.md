# astro-importmaps-runtime

# astro-importmaps

This example shows you how to use importmaps to map dependencies from bare imports to url-imports. The dependencies in this case are react and react-dom and they are imported from [esm.sh](https://esm.sh/).

Using a import map in Layour.astro you can see that react and react-dom are mapped to url imports from en external CDN ([esm.sh](https://esm.sh/)).

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

Note that the packages are imported over Http3 and gets cached in the browser. This means that you don't have to donwload react and react-dom on the second page reload.
