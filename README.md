# NTC Visualiser

A 3D door and kitchen visualiser built as a concept for Naeem Trading. Customers design a front door or kitchen in the browser, see it on a photo of their own house, and book a free home visit.

**Live:** https://ntc-visualiser.vercel.app

## Features

- **3D front doors and kitchens.** Rendered with [three.js](https://threejs.org/). You can rotate the view, open and close the door, and reset the camera.
- **Materials and finishes.** Choose woods such as oak and walnut, marble and granite surfaces, and different handles and hinges. The price updates as you change options.
- **Day and evening lighting.** Preview the design in daylight or at night.
- **On my house.** Take or upload a photo of your house and place the door on it, or try a sample house.
- **Snapshot.** Save an image of your design.
- **Booking flow.** Book a free visit with your name, WhatsApp number, city, area or society, house number and a preferred time to call.
- **English and Urdu.** Urdu text uses the Noto Nastaliq Urdu font.
- **Mobile-first.** The layout is responsive and works on phones.

## Tech

The app is a single static `index.html` with no build step.

- three.js `0.170.0`, loaded from jsDelivr through an import map
- Google Fonts: Geist, Instrument Serif and Noto Nastaliq Urdu
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
