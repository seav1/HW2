name: Sync Files
on:
  push:
    branches:
      - main
  workflow_dispatch:
jobs:
  sync:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@main
      - name: Sync Template Generated Repositories
        uses: benjivesterby/update-sync-for-templates@main
        with: 
          token: "${{ secrets.GH_PAT }}"
      - name: Run Repo File Sync Action
        uses: BetaHuhn/repo-file-sync-action@latest
        with:
          GH_PAT: ${{ secrets.GH_PAT }}
          CONFIG_PATH: sync.yml
          COMMIT_EACH_FILE: false
