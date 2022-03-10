# PiGrid

**Demo:** [pigrid-demo.netlify.app](https://pigrid-demo.netlify.app/)

**What:** \
A responsive grid system using CSS-Grid and Flexbox, written in SCSS and utilising BEM throughout.

It uses a few SASS loops and a bunch of settings to generate up to 12 grid-row elements, all nestable, using inline classes.

A `<header>` block uses named `grid-template-areas`, seperate from the rest of the grid. This is just for experimentation/why-not.

Inspired by [Foundation](https://foundation.zurb.com/sites/docs/) & [Bootstrap](https://getbootstrap.com/docs/4.3/getting-started/introduction/) , PiGrid layout consists of an outer `container`, then `row`, then inner `pod/s`. Add the relevant classes and the layout will flow accordingly.

**How:** \
Outer `container` elements are wrapped around the complete markup or individual blocks; width is modified via class modifiers: `--mini`, `--midi`, `--maxi`.

There's an optional outer wrapper class for full width/height usilising `vw/vh` attributes via BEM modifiers, e.g.: \
`layout-wrapper--full-vh`

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

**Gradient pods:** \
The pods in the demo with gradient from green to red use the SASS `mix` function: \
[sass-lang.com/documentation/modules/color#mix](https://sass-lang.com/documentation/modules/color#mix)

Refer to the following `.scss` file: `scss/components/atomic/_gradient-block.scss`

A JS `for` loop in `main.js` numerically increments these pods which dovetail with the SASS to affect the gradient.

**Demo:** [pigrid-demo.netlify.app](https://pigrid-demo.netlify.app/)

---

## To run and view the project:

The project is built and compiled with [Parcel bundler](https://parceljs.org/) because it just works; anything else would be overkill.

- `npm i` - install dependencies
- `npm run start`

This runs the animation at `localhost:1234` with hot module reloading on save.

To compile for production:

- `npm run build`

**NOTE:**
Parcel deploys files to a flat structure. If a custom dir structure is required, the following works well: [github.com/VladimirMikulic/parcel-plugin-custom-dist-structure](https://github.com/VladimirMikulic/parcel-plugin-custom-dist-structure)

**Also included:**

- [Prettier](https://prettier.io/) code formatter with some common defaults
- `autoprefixer` plugin for Parcel to add vendor prefixes via PostCSS

For further information refer to:

- Parcel documentation: [parceljs.org/docs/](https://parceljs.org/docs/)
- Prettier documentation: [prettier.io/docs/](https://prettier.io/docs/en/index.html)

---

### TODO

Implement SASS `@use`: [sass-lang.com/documentation/at-rules/use](https://sass-lang.com/documentation/at-rules/use)

---

**_QA:_** \
Mobile testing done in Android: Firefox & Chrome and iOS: Safari.
Tested iteratively from ground-up in all decent modern browsers, with Firefox and Chrome device emulators used extensively throughout.
Tablet devices mostly tested in emulators.

Edge Chromium renders perfectly. \
Edge 16+ tested intermittently in Browserstack, needs more (in progress). \
Currently breaks a bit in IE11. \
Nothing pre-IE11.
