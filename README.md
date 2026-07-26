## 📈 Contribution Graph

<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=PrafulBowade73-Netizen&theme=tokyo-night&hide_border=true"/>
</p>
## 🐍 Contribution Snake

<p align="center">
  <img src="https://raw.githubusercontent.com/PrafulBowade73-Netizen/PrafulBowade73-Netizen/output/github-contribution-grid-snake-dark.svg" alt="Snake Animation"/>
</p>
name: Generate Snake

on:
  schedule:
    - cron: "0 */12 * * *"
  workflow_dispatch:

permissions:
  contents: write

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: Platane/snk@v3
        with:
          github_user_name: PrafulBowade73-Netizen
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark

      - uses: crazy-max/ghaction-github-pages@v4
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
