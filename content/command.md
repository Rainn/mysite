Title: Command list
Date: 2014-02-27
Category: Linux
Tag: Pelican, Web

### 1. 安装Python, Pelican环境

virtualenv .env/ --python=python3.3
source .env/bin/activate

### 2. 生成网站
make html

### 3. 上传Github
pelican content/ -o output/ -s pelicanconf.py
ghp-import output/

- Update to [mysite] branch gh-pages
git push origin gh-pages

- Update to [rainn.github.io] master
git push https://github.com/Rainn/rainn.github.io.git gh-pages:master

- 自动部署
add following to .git/hooks/post-commit
"pelican content/ -o output/ -s pelicanconf.py && ghp-import output/ && git push origin gh-pages && git push https://github.com/Rainn/rainn.github.io.git gh-pages:master"