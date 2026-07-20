# Enhanced Light Crosswalk Illumination

Project showcase website for **WisDOT Research Project 0092-25-23***Enhanced Light Crosswalk Illumination*.

A collaboration between **UW–Milwaukee**, **UW–Madison**, and **TAPCO**, sponsored by the **Wisconsin Department of Transportation** and FHWA.

**Key finding:** Blue-spectrum crosswalk lighting let drivers detect pedestrians **~40 ft sooner** than the existing baselineand ~26 ft sooner than conventional 4000 K whitewith faster reaction times, across 281 nighttime field rounds at two Wisconsin sites.

## Site contents

- `index.html`the full single-page showcase (self-contained CSS/JS)
- `assets/`all figures and field photos extracted from the close-out presentation

Sections: Problem → System (SafeWalk™, 7 spectra) → Field Testing (Madison & Milwaukee) → Method (deep-learning eye tracking) → Videos → Results (spectrum tables, recommended configurations, physiological metrics, final specs) → Design Guidelines (scaling, OLS, SSD screening) → WisDOT Recommendations → Team.

## Adding the demonstration videos (YouTube)

1. Upload the three videos to YouTube (Milwaukee demo, Madison demo, eye-tracking pipeline).
2. Open `index.html` and find the `VIDEO_IDS` block near the bottom (inside `<script>`):

```js
const VIDEO_IDS = {
  YOUTUBE_ID_MILWAUKEE: "",   // Milwaukee demonstration video
  YOUTUBE_ID_MADISON:   "",   // Madison demonstration video
  YOUTUBE_ID_EYETRACK:  ""    // Eye-tracking pipeline video
};
```

3. Paste each video's ID between the quotesthe ID is the part after `v=` in the URL.
   Example: `https://www.youtube.com/watch?v=dQw4w9WgXcQ` → `"dQw4w9WgXcQ"`.
4. Save and push. The placeholder cards automatically become embedded players.

## Deploying on GitHub Pages

1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under *Build and deployment*, choose **Deploy from a branch**, select the `main` branch and the `/ (root)` folder, then save.
4. The site publishes at `https://<username>.github.io/<repository-name>/`.

No build step is requiredeverything is static.

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Credits

**PI:** Xiaowei (Tom) Shi, Ph.D. (UW–Milwaukee) · **Co-PIs:** Xiao Qin, P.E., Ph.D. (UW–Milwaukee), Xiaopeng Li, P.E., Ph.D. (UW–Madison), Brian Scharles Sr. (TAPCO) · **GRA:** Muhammad Fahad (UW–Milwaukee)

Student team: Narayan Rai, Xiao Liang (UWM); Bofeng Cao, Chengyuan Ma, Hangyu Li, Keke Long, Jiaxi Liu (UW–Madison); Aleischa Kronshagen, Denise Lawien (TAPCO).

With sincere thanks to the WisDOT Project Oversight Committee and all participants.

*This research was funded by the Wisconsin Department of Transportation and the Federal Highway Administration under Project 0092-25-23. The contents reflect the views of the authors, who are responsible for the facts and accuracy of the data presented.*
