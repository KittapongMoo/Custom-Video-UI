# Custom Video UI

Lightweight custom controls for a YouTube iframe player: play/pause, restart, mute/unmute, volume slider, and seek bar—using the YouTube Iframe API with the native UI hidden.

## What’s here
- `index.html`: Embeds a YouTube player with custom controls wired to the Iframe API.
- `styles.css`: Layout, gradient background, control styling, and iframe masking to hide default YouTube chrome.

## Features
- Play/pause toggle
- Restart (seek to 0)
- Mute/unmute with volume sync
- Volume slider (0–100)
- Seek bar synced each second
- Default YouTube controls hidden via oversized iframe positioning

## Setup & Run
1. Open `index.html` in a modern browser with internet access (the YouTube API is loaded from CDN).
2. Replace the `videoId` in `onYouTubeIframeAPIReady` with your desired YouTube video ID.
3. (Optional) Host via a simple server if your browser blocks local file access. Examples:
   - Python: `python -m http.server 8000`
   - Node: `npx serve .`

## Notes
- The `<script crossorigin="anonymous"></script>` tag is empty; you can remove it or point it to an icon library (e.g., Font Awesome) if you swap out the emoji icons.
- Emoji icons are used for buttons; replace with your preferred icon set if desired.
- `controls: 0` disables default YouTube controls; custom controls handle playback.
- `disablekb: 1` disables keyboard controls for the iframe; remove if you want YouTube keyboard shortcuts.
- The iframe is widened and shifted to hide the native UI while preserving interaction.

## Styling
- Gradient page background and centered container with 16:9 aspect.
- Rounded, hoverable control buttons and sliders.
- Editable via `styles.css` to tweak colors, spacing, or sizing.

## Known limitations
- No fullscreen toggle is provided (YouTube fullscreen UI is disabled). Add a custom button if needed.
- Seek/volume updates poll every 1s; reduce the interval for smoother UI at the cost of more API calls.
