# Scroll dessert sites

Two scroll-driven landing pages. Each one is a single HTML file: no framework, no build step.

| Folder | What it is |
| --- | --- |
| [`indulge/`](indulge/) | "Cream — Indulge". A photoreal vanilla scoop gets wrapped in blueberry sauce, splashes and melts as you scroll, then a purple wave floods into a flavour carousel, menu, basket and subscribe footer. |
| [`cake-studio/`](cake-studio/) | Portfolio hero where scrolling slices a chocolate layer cake, pipes cream and drops a cherry, plus a "Your turn" playground (knife, cream, cherry). Drawn entirely on canvas. |

## Run locally

```bash
python -m http.server 8000
```

Then open http://localhost:8000. The root page links to both sites.

## How the Indulge hero works

- `indulge/assets/frames/1280/` and `indulge/assets/frames/720/` hold 150 WebP frames cut from a 10-second AI-generated clip. Desktop loads the 1280px set and phones load the 720px set.
- Frames load coarse-to-fine, so scrubbing works before every frame has arrived.
- Scroll position picks the frame and draws it to a canvas. The last part of the scroll draws a rising purple wave that matches the carousel's background.
- `indulge/assets/src/` keeps the original full-size PNGs and the source MP4. The site doesn't load them.

## Not wired up yet

- The basket and checkout are a demo. No payment is taken.
- The subscribe form only shows a confirmation message and doesn't send the email anywhere.
- Brand name, flavours, prices and contact links are placeholders.
