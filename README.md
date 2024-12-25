name: Snake

on:
  schedule:
    - cron: "*/5 * * * *"  # Runs every 5 minutes (adjust as needed)
  push:
    branches:
      - main  # Runs when changes are pushed to the main branch

jobs:
  update-snake:
    runs-on: ubuntu-latest

    steps:
      - name: Generate Snake Game
        uses: Platane/snk@v2
        with:
          github_user: 'shahehsan2002'  # Replace with your GitHub username
          svg: true  # Ensures that the output is an SVG file

      - name: Commit & push generated file
        uses: EndBug/add-and-commit@v7
        with:
          author_name: 'GitHub Actions'
          author_email: 'action@github.com'
          message: 'Update Snake game'
