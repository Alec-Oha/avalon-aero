# Avalon Aero — site

Single self-contained file: `index.html`. No build step.

## Swap in your real Excalibur model

1. Export your model as `.glb` (glTF binary — smallest, most reliable for the web).
2. Drop it in `models/excalibur.glb` (path is already wired up).
3. Reload the page. The viewer tries to load that file on start; if it's not
   there yet, it silently keeps the placeholder rig so the page never breaks.
4. If your model is a different filename or hosted elsewhere (e.g. Cloudflare
   R2, like your personal site's images), just change `MODEL_URL` near the
   top of the `<script type="module">` block in `index.html`.

Keep the file under ~15-20MB for reasonable load times. If it's heavier,
run it through `gltf-transform` or Blender's glTF export with Draco
compression before dropping it in.

## Viewer controls

- Drag = orbit (rotate around the model)
- Scroll = zoom
- Panning is disabled on purpose (`controls.enablePan = false` in the script)
- Auto-rotates until the user first drags, then stops

## Deploying

This is a static file — works anywhere:
- **Simplest**: upload `index.html` (+ `models/`) to Netlify Drop or GitHub Pages.
- **Keep Squarespace**: harder to do a full swap since Squarespace controls
  the shell; you'd need to either eject to a custom domain + static host, or
  embed just the 3D viewer section into a Squarespace Code Block (in which
  case the surrounding page keeps Squarespace's chrome, not this design).

Let me know which direction you want and I can adjust the file structure
(e.g. split into Hugo layout + partial, if you'd rather host this the same
way as alecohanesian.com).
"# avalon-aero" 
