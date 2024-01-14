<table border="0">
  <tr>
    <td>
      <a href="#TOP">
        <img src="https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api/top-langs/?username=Saltrol&layout=compact&hide=VHDL,javascript&langs_count=8&hide_border=true" style="color:gray;cursor:pointer;pointer-events:none;">
      </a>
    </td>
    <td>
      <a href="#TOP">
        <img src="https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api?username=Saltrol&count_private=true&show_icons=true&theme=buefy&hide_border=true" style="color:gray;cursor:pointer;pointer-events:none;">
      </a>
    </td>
  </tr>
</table>

name: Generate Snake

on:
schedule:
- cron: "0 0 * * *"
workflow_dispatch:

jobs:
build:
runs-on: ubuntu-latest

steps:
- name: Checkout
uses: actions/checkout@v2.3.4

- name: Generate Snake
uses: Platane/snk@master
id: snake-gif
with:
github_user_name: ${{ github.repository_owner }}
gif_out_path: ./assets/github-contribution-grid-snake.gif
svg_out_path: ./assets/github-contribution-grid-snake.svg

- name: Push to GitHub
uses: EndBug/add-and-commit@v7.2.1
with:
branch: main
message: 'Generate Contribution Snake'
