# Enhanced Light Crosswalk Illumination

Project showcase website for **WisDOT Research Project 0092-25-23** — *Enhanced Light Crosswalk Illumination*.

A collaboration between **UW–Milwaukee**, **UW–Madison**, and **TAPCO**, funded by the **Wisconsin Department of Transportation**.

**Key finding:** Blue-spectrum crosswalk lighting let drivers detect pedestrians **~40 ft sooner** than the existing baseline — and ~26 ft sooner than conventional 4000 K white — with faster reaction times, across 281 nighttime field rounds at two Wisconsin sites.

## Site contents

- `index.html` — the full single-page showcase (self-contained CSS/JS)
- `assets/` — all figures and field photos extracted from the close-out presentation

Sections: Team → Problem → System (SafeWalk™, 7 spectra) → Field Testing (Madison & Milwaukee) → Method (deep-learning eye tracking) → Videos → Results (spectrum tables, recommended configurations, physiological metrics, final specs) → Design Guidelines (scaling, OLS, SSD screening) → WisDOT Recommendations.

## Demonstration videos (YouTube)

The three project videos are already embedded:

- Milwaukee demonstration — `OokYYv6QPt8`
- Madison demonstration — `8C_XTcvsUaI`
- Eye-tracking pipeline — `2JYV7oc0QAc`

To change any video, open `index.html`, find the `VIDEO_IDS` block near the bottom (inside `<script>`), and replace the ID — the part after `v=` in a YouTube URL:

```js
const VIDEO_IDS = {
  YOUTUBE_ID_MILWAUKEE: "OokYYv6QPt8",
  YOUTUBE_ID_MADISON:   "8C_XTcvsUaI",
  YOUTUBE_ID_EYETRACK:  "2JYV7oc0QAc"
};
```

## Comments and suggestions

The site has a **Comments** section where reviewers can send questions, corrections, and
implementation suggestions.

GitHub Pages only serves static files, so it cannot store comments on its own. The form
therefore uses one of the options below. Settings live in the `FEEDBACK` block near the
bottom of `index.html` (inside the last `<script>`).

### Option B - works right now, no signup (current default)

Leave `formEndpoint` empty. When someone presses **Send comment**, their own email app opens
with the comment pre-filled and addressed to **both** project addresses. They press send in
their mail app to deliver it.

Nothing to set up. Add or change addresses here:

```js
recipients: ["muhamm72@uwm.edu", "tomshi@uwm.edu"],
```

### Option A - recommended, comments arrive in your inbox automatically

1. Create a free account at <https://formspree.io> and add a new form (no card required;
   free tier allows 50 submissions per month).
2. Copy the endpoint it gives you, e.g. `https://formspree.io/f/abcdwxyz`.
3. Paste it into `index.html`:

```js
const FEEDBACK = {
  formEndpoint: "https://formspree.io/f/abcdwxyz",
  ...
};
```

4. To notify **both** addresses, verify each one in Formspree
   (**Account → Emails**), then open the form's **Rules** tab and add two rules, each with
   the condition **Always → Send email**, one pointing at `muhamm72@uwm.edu` and one at
   `tomshi@uwm.edu`. Formspree's free plan allows up to two linked notification addresses,
   which is exactly what this project needs.

Visitors then submit without leaving the page, and each comment is emailed to both of you
with the sender's name, affiliation, email, and topic. No GitHub account needed to comment.

Keep the `recipients` list in `index.html` accurate even when using Formspree - it is what
the on-page fallback and the error messages show visitors if a submission fails.

### Option C - optional public thread everyone can read

Adds a giscus thread backed by your repository's GitHub Discussions. Commenters need a
GitHub account, so treat this as an addition to the form rather than a replacement.

1. Enable **Discussions** in the repository settings.
2. Install the giscus app: <https://github.com/apps/giscus>
3. Go to <https://giscus.app>, enter the repository, and copy the generated
   `data-repo-id` and `data-category-id`.
4. Fill them in and flip the switch:

```js
publicThread: {
  enabled: true,
  repo: "iamfahad289/Enhanced-Light-Crosswalk-Illumination",
  repoId: "R_xxxxxxxxxx",
  category: "Announcements",
  categoryId: "DIC_xxxxxxxxxx"
}
```

The form includes a hidden spam-trap field, so automated submissions are discarded.

## Deploying on GitHub Pages

1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under *Build and deployment*, choose **Deploy from a branch**, select the `main` branch and the `/ (root)` folder, then save.
4. The site publishes at `https://<username>.github.io/<repository-name>/`.

No build step is required — everything is static.

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Credits

**PI:** Xiaowei (Tom) Shi, Ph.D. (UW–Milwaukee) · **Co-PIs:** Xiao Qin, P.E., Ph.D. (UW–Milwaukee), Xiaopeng Li, P.E., Ph.D. (UW–Madison), Brian Scharles Sr. (TAPCO) · **GRA:** Muhammad Fahad (UW–Milwaukee)

Student team: Narayan Rai, Xiao Liang (UWM); Bofeng Cao, Chengyuan Ma, Hangyu Li, Keke Long, Jiaxi Liu (UW–Madison); Aleischa Kronshagen, Denise Lawien (TAPCO).

With sincere thanks to the WisDOT Project Oversight Committee and all participants.

*This research was funded by the Wisconsin Department of Transportation under Project 0092-25-23. The contents reflect the views of the authors, who are responsible for the facts and accuracy of the data presented.*
