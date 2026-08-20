# Publishing the RangeBreak release — click by click

The repo at `github.com/algoedgesystems/rangebreak` is currently **empty**, and an
empty repo has no Releases section at all. That is the thing you have to do first:
a release is a *tag on a commit*, and there are no commits yet.

So it is two jobs. Five minutes total.

---

## Job 1 — put one file in the repo

Any single file will do; a README is the useful choice.

1. Sign in to GitHub, go to **https://github.com/algoedgesystems/rangebreak**
2. On the empty-repo page, find the line *"…or create a new file"* and click
   **creating a new file**
   (direct link if you can't see it: `https://github.com/algoedgesystems/rangebreak/new/main`)
3. In the filename box at the top, type:  `README.md`
4. Paste in the contents of the `README.md` I sent alongside this file
5. Scroll down, click the green **Commit changes...**, then **Commit changes** in
   the dialog

The repo now has a `main` branch and a first commit. Refresh the page — a
**Releases** section appears in the right-hand sidebar.

---

## Job 2 — create the backtest release

1. Go to **https://github.com/algoedgesystems/rangebreak/releases/new**
   (or: repo → **Releases** in the right sidebar → **Draft a new release**)

2. **Choose a tag** — click the dropdown and *type* the tag; it does not exist yet,
   so it will not be in the list:

   ```
   backtest-2019-2026
   ```

   Then click the option that appears: **+ Create new tag: backtest-2019-2026 on publish**.
   This is the step people miss — if you don't click that, no tag is set.

3. **Target** — leave it on `main`.

4. **Release title** — paste:

   ```
   RangeBreak backtest — 2019–2026 (Balanced 0.70%, $100k fixed)
   ```

5. **Describe this release** — paste the description block from
   `rangebreak-release-notes.txt`.

6. **Attach the two zips.** Drag them both onto the
   *"Attach binaries by dropping them here or selecting them"* box, or click the box
   and pick them:

   - `RangeBreak-Backtest-Balanced-2019-2026-Eightcap.zip`
   - `RangeBreak-Backtest-BTCUSD-2020-2026-BlackBull.zip`

   **Do not rename them.** GitHub builds the download URL out of the filename, and
   the live results page is already pointing at those two exact names.

7. **Wait for both progress bars to finish** and for both filenames to appear as
   finished rows. Publishing while an upload is still running gives you a release
   that is missing an asset — the same way the Cloudflare deploy silently dropped
   files when it was clicked too early.

8. Tick **Set as a pre-release**. (Same as your FusionBreak backtest release: it
   keeps a data drop from being the repo's "latest release", so `RangeBreak 1.00`
   can hold that spot once you publish the EA.)

9. Click **Publish release**.

---

## Check it worked

Open both of these. Each should start a download, not show a 404:

```
https://github.com/algoedgesystems/rangebreak/releases/download/backtest-2019-2026/RangeBreak-Backtest-Balanced-2019-2026-Eightcap.zip
https://github.com/algoedgesystems/rangebreak/releases/download/backtest-2019-2026/RangeBreak-Backtest-BTCUSD-2020-2026-BlackBull.zip
```

If either 404s, the usual cause is one of three things: the tag came out different
(check it reads exactly `backtest-2019-2026` under the release title), a filename
got changed on upload, or an asset didn't finish uploading before you published.

Then tell me and I'll click both buttons on the live page myself.

---

## Later — the EA release

Your members install guide sends people to
`github.com/algoedgesystems/rangebreak/releases` to download the `.ex5`, so that
page needs a normal release too. Same flow as Job 2, with:

- tag: `v1.00`
- title: `RangeBreak 1.00`
- asset: `RangeBreak.ex5` (compiled — I only have the source, so this one is yours)
- **do not** tick pre-release — this one should be the repo's latest release, the
  way `FusionBreak 1.0` is on the other repo

Until that exists, the download link in the RangeBreak install guide lands on an
empty releases page.
