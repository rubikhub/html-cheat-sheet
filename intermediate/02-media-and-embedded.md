# Media & Embedded Elements

> Elements replaced by external content — images, media players, iframes, and embedded resources.

---

## Images, Media & Embeds

### `<img>`

- **Type:** Replaced
- **Image** — self-closing. Needs **src** + **alt**. Use **srcset** for responsive, **loading="lazy"** for performance, **width/height** to prevent layout shift.

```html
<img
  src="photo.jpg"
  alt="Description"
  loading="lazy"
  width="400"
  height="100"
/>
```

### `<picture>`

- **Type:** Replaced
- **Responsive images** — multiple `<source>` for art direction, format switching (WebP/AVIF), and resolution switching.

```html
<picture>
  <source srcset="img.webp" media="(min-width:600px)" />
  <img src="img.jpg" alt="Responsive" />
</picture>
```

### `<video>`

- **Type:** Replaced
- **Video player** — controls, autoplay, loop, muted, poster. Multiple `<source>` fallbacks. Used for product demos, tutorials, testimonials.

```html
<video controls width="100%">
  <source src="video.mp4" type="video/mp4" />
  Not supported.
</video>
```

### `<audio>`

- **Type:** Replaced
- **Audio player** — podcast players, music players, sound effects, voice messages.

```html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg" />
  Not supported.
</audio>
```

### `<iframe>`

- **Type:** Replaced
- **Embedded page** — YouTube videos, Google Maps, Stripe payments, social widgets, Google Docs. Use **sandbox** for security.

```html
<iframe src="https://example.com" title="Embedded" sandbox></iframe>
```

### `<map>` + `<area>`

- **Type:** Replaced
- **Image map** — clickable regions on an image linking to different destinations. For infographics and interactive diagrams.

```html
<img src="map.jpg" alt="Map" usemap="#map" />
<map name="map">
  <area shape="rect" coords="0,0,150,80" href="/left" alt="Left" />
  <area shape="rect" coords="150,0,300,80" href="/right" alt="Right" />
</map>
```
