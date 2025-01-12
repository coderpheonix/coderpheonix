name: Generate Snake Animation 🐍

on:
  push:
    branches:
      - master  # or main, depending on your default branch
  schedule:
    - cron: "0 0 * * *"  # Runs once daily at midnight

jobs:
  generate-snake:
    runs-on: ubuntu-latest
    steps:
      - name: ✅ Checkout repository
        uses: actions/checkout@v3

      - name: 🐍 Generate snake animation
        uses: Platane/snk@v2
        with:
          github_user_name: coderpheonix  # Replace with your GitHub username
          svg_out_path: dist/github-contribution-grid-snake.svg
          output_format: svg

      - name: 🚀 Upload the snake animation
        uses: actions/upload-artifact@v3
        with:
          name: snake-animation
          path: dist/github-contribution-grid-snake.svg

      - name: 🎉 Commit snake animation to branch
        if: success()
        run: |
          git config --global user.name "GitHub Actions Bot"
          git config --global user.email "actions@github.com"
          git add dist/github-contribution-grid-snake.svg
          git commit -m "🐍 Update snake animation [skip ci]"
          git push
