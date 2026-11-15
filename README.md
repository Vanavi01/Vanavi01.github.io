# Victor Anavian – Engineering Portfolio

A single-file portfolio site (`index.html`). No build tools, no WordPress.

## Put it online with GitHub Pages (about 5 minutes)

1. Create a free GitHub account, then a new **public** repository named `yourusername.github.io` (use your exact username).
2. Click **Add file → Upload files**, drag in `index.html` (and an `images/` folder if you have one), then **Commit changes**.
3. Open **Settings → Pages**. Under *Source*, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
4. After a minute or two the site is live at `https://yourusername.github.io`.

To update the site later, upload the new `index.html` over the old one. GitHub redeploys automatically.

## First things to fill in

Open `index.html` in any text editor (VS Code is free). Everything you'll edit is in the first `<script>` block:

- `CONFIG.email`, `linkedin`, `resume`, `github`: the Contact section appears once at least one is filled.
- Each project's `role`, `highlights`, and `outcome`. These are what recruiters read in the detail view. Empty fields are hidden.
- Double-check the `skills` and `industries` on each project.

## Images and video

The images currently load from your Tufts site. To make the portfolio independent of it:

1. Make an `images/` folder next to `index.html` and save your photos there.
2. Change paths to `"images/solar-1.jpg"` and similar.

Gallery items can be:

```js
{ type: "image",   src: "images/robot-1.jpg", caption: "Drive base" }
{ type: "video",   src: "images/robot-demo.mp4", caption: "Driving test" }   // keep under ~25 MB
{ type: "youtube", src: "dQw4w9WgXcQ", caption: "Full demo" }             // just the video ID
```

## Choosing what employers see first

- `priority`: 1 appears first, then 2, and so on.
- `featured: true`: makes the card double-width. Use it for your 1–3 strongest projects.
- `hidden: true`: removes a project from the site without deleting it.
- `industries`: these become the filter buttons. Keep the list short and reuse the same names (for example Automotive, Robotics, Consumer products, Medical & assistive, Electronics, Aerospace, Manufacturing).

## Adding an entry with Claude

Attach `index.html` and send something like:

> Add a new portfolio entry to my site.
> Title: Pneumatic Gripper
> Date: 2026-04
> Priority: 2, featured
> Industries: Robotics, Manufacturing
> Skills: SolidWorks, FEA, pneumatics, 3D printing
> Summary / what I did / results: (paste your notes)
> Media: images/gripper-1.jpg, images/gripper-cad.png, YouTube ID abc123
> Links: GitHub https://github.com/...

Claude will add it to `PROJECTS` and give you the updated file to upload.
