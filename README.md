# Bruss

Bruss is a simple css style kit in [sass](https://sass-lang.com).

Save **80%** (in my practice) time of writing styles by just `@import 'bruss'`.

> Notice: '@use' was replaced with '@import' as it's not work in generally.

# How to use


```bash
npm i bruss
```

The define your app theme variables and import 'burss', see example below:

```scss
// 1. Define your theme variables
$theme: (
  // Containers' max with or padding-x on mobile
  container-max-width: 960px,
  container-padding-x: 4vw,
  // Base UI Factors
  radius : 16px,
  colors: ( "white": #fff, "silver": #f4f4f4, "gray": #aaa, "black": #1b1b1b, "primary": #38B833 ),
  texts: ( 1: 2.6rem, 2: 1.6rem, 3: 1.1rem, 4: 1rem, 5: .9rem, 6: .8rem, 7: .6rem ),
  sizes:  ( 24: 24px,36: 36px,44: 44px,54: 54px,64: 64px, 120: 120px ),
  spacings: ( 0: 0, 2: 2px, 5: 5px, 10: 10px, 15: 15px, 20: 20px, 30: 30px, 50: 50px ),
);

// 2. Use the bruss
// If sass compiler says 'stylesheet not found': try use path 'bruss/bruss' or '{path_to_node_modules}/bruss/bruss/index'
@import 'bruss';

// 3. Define your own styles
html,body{
  @extend .black, .t-4; // set default text style
  font-family: sans-serif;
}
.card{  // For example: a inline-block card
  @extend .bg-silver, .border-gray, .round, .inline, .p-20;
}
// other styles...

```


---


# Classe References

According to the variables you defined, most regular used classes will be generated. 

It's suggested to go through definations in /bruss folder, I promise it's simple.

> Notice: all block were set to 'box-sizing:border-box' and 'position:relative'


### Layout

`.container`

A Wrapper which width contracted by *$container-max-width* *$container-padding-x*.


`.inline`,`.block`

Note .inline means 'display:inline-block'.


`.flex-row` & `.center`,`.vcenter`

Define a flex-row wrapper and align child elements. modify + `.gap-${spacing}`


`.flex-row` > `.flex-1`,`.flex-2`,`.flex-3`,`.flex-5`,`.flex-none`

Only works when '@media screen and (orientation: landscape)'


`.flex-row` > `.flex-m-1`,`.flex-m-2`,`.flex-m-3`,`.flex-m-5`,`.flex-m-none`

Only works when '@media screen and (orientation: portrait)'


`.grid .grid-cols-* .grid-cols-m-*`, set element to grid with *(2-6) element each row. ( defint grid-gap by yourself )

Only works when '@media screen and (orientation: landscape)'


`.fix-t`,`.fix-b`: set 'fix'


`.ab-tl`,`.ab-tr`,`.ab-bl`,`.ab-br` : set 'position:absolute' and tl('top:0,left:0') or tr, bl, br.


`.fleft`,`.fright` : set 'float'


`.left`,`.right`,`.center` : set 'text-align'


---


### Color ( $colors )

Each key in $colors will be generated into classes, for example 'red':

`.red` : set 'color', modify + `.darken`,`.lighten`

`.bg-red`, `.bg-none` : set 'background-color', modify + `.darken`,`.lighten`, `.tap-darken`, `.tap-lighten`

`.bg-cover`: set 'background' center image and 'cover' mode

`.border-red` : set 'border', modify + `.border-t`,`.border-b`,`.border-dashed`,`.border-darken`,`.border-lighten`


---


### Size (use $sizes )

Each key in $sizes will be generated into classes, for example key:'44':

`.w-full`,`.h-full` : set 'width' or 'height' to 100%

`.w-100`,`.h-100`,`.w-min-100`,`.h-min-100` : set '(max-)width' or '(max-)height' to 100vw

`.w-44`,`.h-44`,`.wh-44` : set 'width', 'height', modify + `.round-full`


---


### Spacing (use $spacings )

Each key in $spacings will be generated into classes, for example key:'10':

`.m-10`,`.mt-10`,`.mb-10`,`.ml-10`,`.mr-10`,`.mx-10`,`.my-10` : set 'margin'

`.p-10`,`.pt-10`,`.pb-10`,`.pl-10`,`.pr-10`,`.px-10`,`.py-10` : set 'padding'


---


### Text (use $texts, $sizes )

Each key in $texts will be generated into classes, for example $texts key:'4', and $sizes key:'44':

`.t-4` : set 'font-size'

`.th-4`,`.th-44` : set 'line-height'

`.nowrap`,`.break-all`,`.trim`,`.bold`,`.italic`,`.underline`,`.line-through` : helpers


---


### Effect ( $radius )

`.hide`,`.hide-mobile`,`.hide-desk` : set 'display:none' in diffrent device

`.round`,`.round-t`,`.round-b` : set 'border-radius'

`.tap-opacity`,`.tap-expand`,`.tap-darken`,`.tap-lighten` : set active style

`.flip`,`.crop` :  helpers


---


# Credits

[Sass](https://sass-lang.com/)