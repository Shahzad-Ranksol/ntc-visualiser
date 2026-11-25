# NTC Visualiser

A 3D door and kitchen visualiser built as a white-label concept (currently branded "Ashford Living"). Customers design a front door or kitchen in the browser, see it on a photo of their own house, and book a free home visit.

**Live:** https://ntc-visualiser.vercel.app

## Features

- **3D front doors and kitchens.** Rendered with [three.js](https://threejs.org/). You can rotate the view, open and close the door, and reset the camera.
- **Materials and finishes.** Choose woods such as oak and walnut, marble and granite surfaces, and different handles and hinges. The price updates as you change options.
- **Day and evening lighting.** Preview the design in daylight or at night.
- **On my house.** Take or upload a photo of your house and place the door on it, or try a sample house.
- **Snapshot.** Save an image of your design.
- **Booking flow.** Book a free visit with your name, WhatsApp number, city, area or society, house number and a preferred time to call.
- **English UI and US dollar pricing**, white-label branding set in the `BRANDS` config. Amounts use international formatting ($42.5K, $1.25M).
- **Mobile-first.** The layout is responsive and works on phones.

## Realistic version

**Live:** https://ntc-visualiser.vercel.app/realistic (`realistic.html`)

This version has the same designer, pricing and booking flow, with a more photoreal renderer:

- **Real lighting.** HDRI skies and studio light replace the generated room environment.
- **Scanned materials.** PBR texture sets (colour, normal and roughness maps) for oak veneer, stone cladding, sandstone, plaster, pavers and floor tiles. The oak is desaturated in the browser and tinted to each finish, so every wood option keeps its colour.
- **Real glass.** Transmissive, refractive glass, so you can see the hallway through clear panels.
- **Rounded edges, ambient occlusion and bloom.** Bevelled geometry, GTAO and gentle bloom for the evening lights, with neutral tone mapping so finish colours stay accurate.
- **Photo render.** The ✦ button path-traces the current design with [three-gpu-pathtracer](https://github.com/gkjohnson/three-gpu-pathtracer). It takes about 30–40 s, then the image is denoised and can be downloaded. On kitchens, the render is also added to the enquiry.
- **Lighter mode for slower phones.** It lowers the pixel ratio, turns off ambient occlusion and uses fewer path-tracing samples.

The classic page links to the realistic one and back.

### Asset credits

The HDRIs and textures in `assets/` are from [Poly Haven](https://polyhaven.com) and are CC0 (public domain). They are `kloofendal_48d_partly_cloudy_puresky`, `studio_small_09`, `oak_veneer_01`, `castle_wall_slates`, `marble_01`, `painted_plaster_wall`, `interlocking_concrete_pavers` and `large_floor_tiles_02`.

## Tech

The app is a single static `index.html` with no build step.

- three.js `0.170.0`, loaded from jsDelivr through an import map
- Google Fonts: Manrope
- Hosted on Vercel; `vercel.json` sets clean URLs and no-cache headers

## Run locally

Serve the folder with any static server, for example:

```bash
npx serve .
# or
python3 -m http.server 8000
```

Then open http://localhost:8000. Camera access for the "On my house" photo needs `localhost` or HTTPS.

## Deploy

The repo is connected to Vercel. Every push to `main` deploys to production. To deploy by hand:

```bash
npx vercel deploy --prod
```
