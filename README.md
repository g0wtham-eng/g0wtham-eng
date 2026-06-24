name: Update README

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

jobs:
  update-readme:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Recent Activity
        uses: Readme-Workflows/recent-activity@main
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          GH_USERNAME: g0wtham-eng
          CONFIG_FILE: .github/recent-activity.config.yml
