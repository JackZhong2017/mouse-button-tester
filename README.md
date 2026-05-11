# 🖱 Mouse Button Tester

A minimal, standalone HTML tool for detecting mouse button events in the browser.

**Live demo**: open `index.html` directly — no build step, no dependencies.

## Features

- Detects left / middle / right mouse button press and release
- Uses `setPointerCapture` to correctly track hold state even when the cursor leaves the element
- Logs raw `button` and `buttons` values for debugging
- Right-click context menu suppressed for clean testing

## Why `setPointerCapture`?

Standard `mousedown` / `mouseup` listeners on a DOM element lose track of the pointer once it leaves that element's bounds. `setPointerCapture` tells the browser to route all subsequent pointer events to the capturing element until `pointerup` or `pointercancel` fires — regardless of where the cursor moves.

```js
zone.addEventListener('pointerdown', (e) => {
  zone.setPointerCapture(e.pointerId) // key line
  // ... your logic
})
```

## Usage

```bash
# Clone
git clone https://github.com/<your-username>/mouse-button-tester.git

# Open
open index.html
```

No npm, no bundler. Single file.

## License

MIT