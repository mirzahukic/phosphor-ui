# Phosphor UI

Phosphor UI is a CSS design system with the look of 1990s computer role-playing games. It has rusty metal plates, green CRT screens, red lamp buttons and paper notes. All colors come from a classic 256-color game palette.

It is one plain CSS file. It works with any framework or with plain HTML, and it needs no build step.

## Use it

1. Add the fonts and the stylesheet to the `<head>` of your page:

   ```html
   <link rel="preconnect" href="https://fonts.googleapis.com">
   <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
   <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Francois+One&family=VT323&display=swap">
   <link rel="stylesheet" href="phosphor.css">
   ```

2. Add the classes to your markup:

   ```html
   <body class="ph-chassis">
     <section class="ph-plate ph-stack">
       <h2 class="ph-label">Status</h2>
       <ul class="ph-screen ph-readout">
         <li>Hit Points <span>30/30</span></li>
         <li class="ph-dim">Poisoned</li>
       </ul>
       <div class="ph-row">
         <button class="ph-button ph-button--lamp">Done</button>
       </div>
     </section>
   </body>
   ```

   Components do not add space around themselves. Put `.ph-stack` (vertical) or `.ph-row` (horizontal, wraps) on the container to space its children. `.ph-stack` stretches its children to full width, so put buttons in a `.ph-row`.

## Names

- All classes start with `ph-`, for example `.ph-button` and `.ph-screen`.
- Variants use `--`, for example `.ph-button--lamp`.
- Parts of a component use `__`, for example `.ph-card__header`.
- All tokens are CSS custom properties that start with `--ph-`, for example `--ph-green` and `--ph-metal`.

## See every component

Open `examples/index.html` in a browser. This page shows each component with its class name, plus composed examples.

The other pages show the components in use:

| Page | Shows |
| --- | --- |
| `examples/login.html` | A terminal login with error states |
| `examples/barter.html` | A trade screen with lists, totals and a slider |
| `examples/options.html` | A settings screen with tabs, sliders and switches |
| `examples/bulletin.html` | A normal web page in the style |

## Notes

- **Interactive parts:** Tabs, the drop zone, toasts, the context menu and the tooltip need a small script. The scripts are in `examples/index.html` for now. The CSS works without them.
- **Animations:** `.ph-static`, `.ph-skeleton` and `.ph-spinner` animate without end. Use them only while content loads. They stop when the viewer turns on "reduce motion".
- **Soft blur:** Add `.ph-crt` to a container to give it a soft CRT blur. It can make scrolling slower on weak devices.
- **Accessibility:** The text colors pass WCAG 2.1 AA contrast. If a radio or checkbox is hidden inside a `.ph-tile`, use `.ph-sr-only` so keyboards and screen readers can still reach it.

## License

Phosphor UI uses the MIT license. See `LICENSE`.

The fonts VT323 and Francois One use the SIL Open Font License. The pages load them from Google Fonts. If you put the font files in your own package, include their license too.
