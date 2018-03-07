# Themes - Modifying trough variables

A <b>start</b> mappába dolgozunk az <b>end</b> mappában találjuk a megoldást

## 1. Themes mappa

- a default mappa mellé hozzunk létre egy <b>themes</b> mappát

## 2. Témák létrehozása

- a <b>themes</b> mappán belül hozzunk létre 3 almappát ezek legyenek <b>forest</b>, <b>spring</b>, <b>water-garden</b>

- a forest mappában hozzuk létre a <b>forest.scss</b>-t és a <b>_variables.scss</b>-t

- a <b>forest</b> mappában lévő <b>_variables.scss</b> tartalma a következő legyen:

```
/* forest theme */
$white: #fff;
$global-color: #486b00;
$global-hover-color: #2e4600;
$categories-background: #a2c523;
$footer-background: #7d4427;
$footer-link-color: $white;
$footer-color: $white;

$theme-fonts: "https://fonts.googleapis.com/css?family=Raleway:400,400i,700,700i,900,900i|Rammetto+One&subset=latin-ext"!default;

$body-font-family: "Raleway",sans-serif!default;
$module-head-font-family: "Rammetto One"!default;
$gutter: 20px;
$container-width: 1560px;
``` 

- a <b>spring</b> mappában hozzuk létre a <b>spring.scss</b>-t és a <b>_variables.scss</b>-t

- a <b>spring</b> mappában lévő <b>_variables.scss</b> tartalma a következő legyen: 

```
/* spring theme */
$white: #fff;
$global-color: #f98866;
$global-hover-color: #ff420e;
$categories-background: #89da59;
$footer-background: #80bd9e;
$footer-link-color: $white;
$footer-color: $white;
```

- a <b>water-garden</b> mappában hozzuk létre a <b>water-garden.scss</b>-t és a <b>_variables.scss</b>-t

- a <b>water-garden</b> mappában lévő <b>_variables.scss</b> tartalma a következő legyen: 

```
/* water-garden theme */
$white: #fff;
$global-color: #004445;
$global-hover-color: #021c1e;
$categories-background: #2c7873;
$footer-background: #6fb98f;
$footer-link-color: $white;
$footer-color: $white;
```

## 3. Témák behúzása

- a gyökérben lévő <b>index.scss</b> fájlban húzzuk be a három téma <b>variables.scss</b>-ét,

```
@import 'themes/forest/variables';
//@import 'themes/spring/variables';
//@import 'themes/water-garden/variables';
```

## 4. Forest sablon további stílusozása 

- a forest mappában hozzunk létre a components, és a modules mappát, illetve a _components.scss-t és a _modules.scss-t

- a _components.scss fájl tartalma a következő legyen:

```
@import 'components/button';
```

- a _modules.scss fájl tartalma a következő legyen:

```
@import 'modules/product-item';
```

-  a components mappában hozzuk létre a button.scss-t, tartalma a következő legyen:

```
.btn-lg {
    width: 100%;
    display: inline-block;
}
```

- a modules mappában hozzuk létre a product-item.scss-t, tartalma a következő legyen:

```
.content-position {
    .product-item {
        @include dinamic-width(5);
    }

    .product-item-row-actions {
        text-align: center;

        .product-item-row {
            width: 100%;
        }
    }
}
```

- a forest.scss tartalma a következő legyen:

```
@import "components";
@import "modules";
```

- az index.scss-ben a default theme alatt húzzuk be a forest theme-t
```
// forest theme
@import 'themes/forest/forest';
```

## 5. futassuk a gulp taskot a start mappán

- vizsgáljuk meg miért nem kaptuk meg a kivánt eredmény?!

## 6. !default flag

- a <b>default</b> mappában nyissuk meg a <b>variables.scss</b>-t és minden változó végére tegyük oda a !default flaget

## 7. futassuk a gulp taskot a start mappán ismét