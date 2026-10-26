# Copperleaf Grounds Co. (scroll-to-clean-up landscaping demo)

A single-page demo site for a landscaping and yard care business. The hero says **"Scroll to pick up your leaves and mow the lawn"**. As you scroll, a buried, overgrown front yard gets its leaves cleared, gets mowed into stripes, and finally lights up at dusk. A live counter tracks leaves picked up, lawn mowed and lights on as you go.

Plain HTML, CSS and JavaScript. No build step. Deploys to Vercel, Netlify or GitHub Pages as a static site. Light theme only.

## Deploying on Vercel

Framework Preset: **Other**. Leave Root Directory, Build Command and Output Directory blank. `vercel.json` sets long cache headers for the frames, video and images.

## How the scroll story works

- The transformation is real video, cut into 203 still frames: `frames/d/` (1600x900, desktop) and `frames/m/` (720x960 portrait crop, phones), both AVIF.
- Scroll position picks a frame and draws it on a `<canvas>`, blending between neighbouring frames so the motion stays smooth.
- Frames load in the background: the four key moments first, then a coarse pass, then the rest. Browsers that can't show AVIF cross-fade the four still photos in `images/yard-*.webp` instead.
- Timing lives in `CFG` at the top of the script in `index.html`: `keys` are the frame numbers of the four moments (mess, leaves cleared, mowed, dusk) and `map` sets where in the scroll each one lands and how long it holds.

## Sections

Scroll story hero, service marquee, drag-to-compare before and after slider, stats, services grid, landscape lighting feature, cleanup process, September to December season plan (the current month is highlighted), pricing, reviews, FAQ with service area, quote form over a looping dusk video, footer, and a mobile call bar.

## Making it yours

Everything lives in `index.html`.

- **Business details:** search for `Copperleaf`, `(610) 555-0147`, `hello@copperleafgrounds.com`, `West Chester` and `Brandywine Valley` and replace them. The LocalBusiness JSON-LD in the `<head>` has the same details.
- **Colors and fonts:** edit the tokens at the top of the `<style>` block (`--copper`, `--evergreen`, `--bg` and so on).
- **Prices, reviews, stats, towns and FAQ:** all sample content. Replace with real numbers and real customer quotes before using this for a live business.
- **Quote form:** with no endpoint set, the form runs in demo mode and only shows the thank-you message. To receive submissions, create a form at a service like [Formspree](https://formspree.io) and paste its URL into `data-endpoint=""` on the `<form id="quote-form">` tag.

## Media credits

- **Scroll story, before/after, dusk photos and dusk video** (`frames/`, `video/`, `images/yard-*`, `images/og.jpg`) are AI-generated sample visuals made with Higgsfield (GPT Image 2.5 stills, MiniMax H3 and Kling 3.0 video). The house is not a real property. Swap in real job footage before presenting them as a company's own work.
- The remaining photos are from [Pexels](https://www.pexels.com) and free to use under the [Pexels license](https://www.pexels.com/license/):
  [leaf blower](https://www.pexels.com/photo/9620213/),
  [porch mums](https://www.pexels.com/photo/3142467/),
  [pruning](https://www.pexels.com/photo/38936344/),
  [leaves on grass](https://www.pexels.com/photo/9779101/),
  [rake](https://www.pexels.com/photo/9735037/),
  [leaf pile](https://www.pexels.com/photo/10559047/),
  [lawn](https://www.pexels.com/photo/10258631/).
