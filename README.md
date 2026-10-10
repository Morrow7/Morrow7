
name: Generate Arctic Snake

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

permissions:
  contents: write

jobs:
  generate:
    runs-on: ubuntu-latest

    steps:
      - name: Generate light and dark snakes
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: Morrow7
          outputs: |
            dist/github-contribution-grid-snake.svg?color_snake=%2360A5FA&color_dots=%23F8FAFC,%23DBEAFE,%23BFDBFE,%2393C5FD,%2360A5FA
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark&color_snake=%23CBD5E1

      - name: Publish snake
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
