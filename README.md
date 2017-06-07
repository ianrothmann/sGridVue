# sGridVue
A set of Vue 2 components that wrap Stylus Grid (stylusgrid.com).

## Installation
Be sure to install the s-grid dependency too.

```javascript
npm install s-grid  --save-dev
npm install s-grid-vue  --save-dev
```
In your app.styl be sure to include:

```
@import '../../../node_modules/s-grid-vue/s-grid-settings.styl'

@import '../../../node_modules/s-grid/s-grid-functions.styl'
@import '../../../node_modules/s-grid/s-grid-classes.styl'
```

## Usage

```html
  <s-grid center reverse>
       <s-cell md="4">Content here</s-cell>
       <s-cell md="4">Content here</s-cell>
       <s-cell md="4">Content here</s-cell>
  </s-grid>
```    

```html
  <s-grid h-center>
            <s-cell md="6" >Centered Content</s-cell>
   </s-grid>
```        

### s-grid

The following properties are available for s-grid:

Vertical Positions
*  top (default)
*  bottom
*  center
*  stretch

Horizontal positions
*  h-center
*  h-start
*  h-end

Handle cells in rows / columns:
*   rows (default)
*   columns
*   reverse (use with rows or columns)

### s-grid-cell
The breakpoints have a 12 point system (similar to bootstrap).

The breakpoints are set with:
*  xs (xs is always set with a default value of 12)
*  sm
*  md
*  lg
*  xl

Offsets are also supported:
* offset-xs
* offset-sm
* etc.

The breakpoints are:
```
    xs: 0,
    sm: 640px,
    md: 1024px,
    lg: 1440px,
    xl: 1920px
```






