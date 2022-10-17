## Olá eu sou o Johnatan Cardozo!

Here are some ideas to get you started:

- 🌱 Estudando JavaScript e HTML/CSS

![Johnatan Moreira GitHub stats](https://github-readme-stats.vercel.app/api?username=JohnatanMoreira1&show_icons=true&theme=midnight-purple)


### Technologies

<div style="display: inline_block">
    <img align="center" src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white">
    <img align="center" src="https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E">
    <img align="center" src="https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white">
    <img align="center" src="https://img.shields.io/badge/CSS-239120?&style=for-the-badge&logo=css3&logoColor=white">
     <img align="center" src="https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white">
     <img align="center" src="https://aleen42.github.io/badges/src/photoshop.svg"><br><br><br>


     Sempre em busca de conhecimento e com sede de crescimento!
</div>
name: Snake Game
on:
  schedule:
    - cron: "0 */5 * * *"
    
  workflow_dispatch:


jobs:
  build:
    runs-on: ubuntu-latest
    steps:

      - uses: actions/checkout@v2

      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: JohnatanMoreira1
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

      - run: git status
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
