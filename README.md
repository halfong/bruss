# Bruss

Bruss is a simple stylesheets helper kit in sass language. You could save almost **80%** (in my practice) time of writing styles by just `@import` it to your project.

# How to use

In you app.sass (or anything like that), define variables that required, then import Bruss.

Here's an example contains all the variables:

```scss
// defined your theme variables
$theme: (
  radius : 16px,
  container-max-width: 960px,
  container-padding-x: 4vw,
  colors: ( white: #fff, silver: #f4f4f4, gray: #aaa, black: #1b1b1b, primary: #38B833 ),
  texts: ( 1: 2.6rem, 2: 1.6rem, 3: 1.1rem, 4: 1rem, 5: .9rem, 6: .8rem, 7: .6rem ),
  sizes:  ( 24: 24px,36: 36px,44: 44px,54: 54px,64: 64px, 120: 120px ),
  spacings: ( 0: 0, 2: 2px, 5: 5px, 10: 10px, 15: 15px, 20: 20px, 30: 30px, 50: 50px ),
);

// use the kit
@use 'bruss' with ( $theme : $theme );
```


# Classes

According to the variables you defined, most used classes will be generated (In brackets are the required variables ).

You could see the detail style definations in /src folder, i promise it's simple.

### Layout

`.container` ( $container-max-width, $container-padding-x )

`.inline`,`.block`

use flex to layout : `flex-row`
  & `center`,`vcenter`
  \> `flex-1`,`flex-2`,`flex-3`,`flex-5`,`flex-none`
  \> `flex-m-1`,`flex-m-2`,`flex-m-3`,`flex-m-5`,`flex-m-none`

position:fixed : `fix-t`,`fix-b`

position:absolute : `ab-tl`,`ab-tr`,`ab-bl`,`ab-br`,

float : `fleft`,`fright`

text-align : `left`,`right`,`center`

> Notice: all block were set to 'box-sizing:border-box' and 'position:relative'

### Color ( $colors )

$colors<Map> should be defined before import.

Each key in $colors should generate classes, for example key:'red':

color : `.red`,`.red .darken`,`.red .lighten`

background-color : `.bg-red`,`.bg-red .darken`,`.bg-red .lighten`,`bg-none`

daken background when tapped(:active) : `.tap-darken`, `tap-lighten`

center image background : `bg-cover`:

border : `.border-red`,`&.border-t`,`&.border-b`,`.border-dashed`,`.border-darken`,`.border-lighten`

### Size ( $sizes )

width:100% : `w-full`,`h-full`

100vw or 100vh : `w-100`,`h-100`,`w-min-100`,`h-min-100`

$sizes<Map> should be defined before import.

Each key in $sizes should generate classes, for example key:'44':

width & height: `w-44`,`h-44`,`wh-44`
  \> `round-full`

### Spacing ( $spacings )

$spacings<Map> should be defined before import.

Each key in $spacings should generate classes, for example key:'10':

margin : `.m-10`,`.mt-10`,`.mb-10`,`.ml-10`,`.mr-10`,`.mx-10`,`.my-10`

padding : `.p-10`,`.pt-10`,`.pb-10`,`.pl-10`,`.pr-10`,`.px-10`,`.py-10`

.flex-row
  > `gap-10`

### Text ( $texts, $sizes )

$texts<Map> should be defined before import.

Each key in $texts should generate classes, for example key:'4', and $sizes key:'44':

font-size : `.t-4`

line-height : `.th-4`,`.th-44`

helpers : `nowrap`,`break-all`,`trim`,`bold`,`italic`,`underline`,`line-through`

## Effect ( $radius )

display:none : `hide`,`hide-mobile`,`hide-desk`

border-radius : `.round`,`.round-t`,`.round-b`,

active style : `tap-opacity`,`tap-expand`,`tap-darken`

helpers : `flip`,`crop`,`shadow`

# Credits

[Sass](https://sass-lang.com/)

