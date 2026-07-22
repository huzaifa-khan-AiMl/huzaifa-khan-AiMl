# Setup Steps

Everything in this repo is designed to work as-is, but three things need one-time setup on GitHub's side.

## 1. Repo name must match your username exactly
GitHub only renders a profile README if the repo is named **exactly** your username (case doesn't matter for this part, GitHub normalizes it). Confirm the repo is `huzaifa-khan-AiMl/huzaifa-khan-AiMl`, public, with a README.

## 2. Fix the zero-streak widgets
The stats/streak images in the README use the casing `huzaifa-khan-AiMl` consistently. If they still show 0 after uploading:
- Go to your GitHub profile settings → confirm "Include private contributions" is checked if you want private repo activity counted.
- Give the streak-stats service ~24h to build its cache after first load.

## 3. Turn on the snake animation
The snake graph doesn't work from a plain image URL — it needs a GitHub Action to run once and publish an `output` branch.

1. Push this repo (including `.github/workflows/snake.yml`) to `huzaifa-khan-AiMl/huzaifa-khan-AiMl`.
2. Go to the **Actions** tab of that repo → you may need to click "I understand my workflows, enable them" the first time.
3. Run the **"generate snake animation"** workflow manually once (Actions tab → select it → "Run workflow"). This creates the `output` branch.
4. After it finishes (~1-2 min), the snake image in the README will render. It re-runs automatically every 24h after that.

No secrets or tokens need to be added manually — the workflow uses the automatically-provided `GITHUB_TOKEN`.

## 4. Assets folder
Everything under `assets/` (banner, roadmap, divider) is plain SVG generated for this profile — no external image hosting needed. If you want to tweak colors or text later, they're just text files you can edit directly.
