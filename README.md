# Koenigsegg AR

A printed QR code that opens a web page; the page finds that same QR code through the phone camera and shows a 3D Koenigsegg driving laps around it on the paper, with spinning wheels, steering front wheels, and headlights and taillights you can switch on and off.

- **Live page:** https://appscode-26.github.io/koenigsegg-ar/
- **Print:** `print-me.pdf` (letter paper, print at 100% so the code is 3 inches across), or `qr.png`.
- Tap **Start AR**, allow the camera, and point the phone at the code. Hold it about 12 inches away so you can see the whole lap.
- **💡 Lights** (top right) switches the headlights and taillights on and off.
- **Pinch** with two fingers to resize. No printout handy? Tap "No QR? View in 3D".

## How the driving works

- The rear-axle centre follows an oval around the code and the car points along it, so the rear tyres never slide sideways.
- The front wheels steer to the Ackermann angle for the current curve (inner wheel up to 33°, outer 24.5°).
- Each wheel spins at its own ground speed divided by its own radius. Inner and outer wheels differ, and so do the larger rear wheels and the smaller fronts. The brake calipers steer with the wheel but don't spin.
- On a slow phone the car drives a little slower, so the 5-spoke wheels never look like they're spinning backwards.

Settings (car size, lap size, speed, direction) are in the `CONFIG` block at the top of the script in `index.html`. Bump `version` and the visible `v1` label on every redeploy.

Built with [MindAR](https://github.com/hiukim/mind-ar-js) image tracking + three.js.

## Credit

3D model: "Koenigsegg One Pro" (https://sketchfab.com/3d-models/koenigsegg-one-pro-26d50f742f3241f5a36081d93205c764) by Head to Turbosquid - Allay Design (https://sketchfab.com/Alister.Dsa), licensed under CC BY 4.0 (http://creativecommons.org/licenses/by/4.0/).
Changes: the wheels, brake calipers and lights were split into separate parts so they can be animated. The model was also simplified (703k → 205k triangles) and its textures resized for phones.
