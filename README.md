# Stylelint demo
This small demo illustrates that stylelint produces an error under the `declaration-block-no-redundant-longhand-properties` rule when using the `--fix` option, **specifically** when `repeat()` is used. 

## Steps to reproduce
1. download the repo
2. run `npm install`
3. observe the layout in the browser
4. run `npm run lint:fix`
5. observe the layout in the browser

## Expected behavior
`1fr` should be applied across each column:

```css
grid-template-areas: "left center right" auto / 1fr 1fr 1fr;
```

## Actual behavior

`repeat()` is copied, which is invalid syntax, breaking the layout:

```css
    grid-template: "left center center right" auto / repeat(3, 1fr);
```
