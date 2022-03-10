# PiGrid

![GitHub release (latest by date)](https://img.shields.io/github/v/release/powellian/pigrid) ![GitHub](https://img.shields.io/github/license/powellian/pigrid)

**Demo:** [pigrid-demo.netlify.app](https://pigrid-demo.netlify.app/)

**What**

A SCSS setup utilising a few loops and a bunch of settings to generate up to 12 grid-row elements, all nestable, using inline classes. Utilises [BEM](https://css-tricks.com/bem-101/) throughout.
A newly added `<header>` uses named `grid-template-areas`, seperate from the rest of the grid.

**Demo:** [powellian.com/pigrid/]()

Inspired by [Foundation](https://foundation.zurb.com/sites/docs/)/[Bootstrap](https://getbootstrap.com/docs/4.3/getting-started/introduction/) , PiGrid layout consists of an outer `container`, then `row`, then inner `pod/s`. Add the relevant classes and the layout will flow accordingly.

**How**
Outer `container` elements are wrapped around the complete markup or individual blocks; width is modified via class modifiers: `--mini`, `--midi`, `--maxi`. There's an optional outer wrapper class for full width/height usilising `vw/vh` attributes.

Inner `row` blocks indicate the divisible aspect of the content pods e.g.:
`pigr__row pigr__row--N`- where N is the grid _fraction_ (`fr`), for the child `pod`s.

Content `pod`s use the following: `pigr__pod pigr__pod--N` - where N is the grid _fraction_ (`fr`) denoted on the parent `row`.

For example, when using `pigr__row pigr__row--6`, the inner pods could be:

- `pigr__row pigr__pod--1` _and_ `pigr__row pigr__pod--5`
- _3x_ `pigr__row pigr__pod--2`
- _3x_ `pigr__row pigr__pod--1` _and_ `pigr__row pigr__pod--3`
- `pigr__row pigr__pod--2` _and 1x_ `pigr__row` _and 1x_ `pigr__row pigr__pod--3`

etc...

Omitting the pod size leads to the elements _auto-sizing_ in the available space, based on the sizing dictated by the parent row element. For example within `pigr__row--6`:

- 4x `pigr__pod` and 1x `pigr__row pigr__pod--2`

**_QA:_**
Tested iteratively from ground-up in all decent modern browsers, with Firefox and Chrome device emulators used extensively throughout.
Mobile testing done in Android: Firefox & Chrome and iOS: Safari.
Tablet devices mostly tested in emulators.

The new Edge Chromium renders perfectly.
Edge 16+ tested intermittently in Browserstack, needs more (in progress).
**Currently breaks a bit in IE11 - am working on this.**
Nothing pre-IE11.

## This project runs with...

This project has been ported into [https://parceljs.org/](Parcel 2). It's being tweaked a little right now (Jan '22).
