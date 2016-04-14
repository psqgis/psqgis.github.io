###psqgis.github.io
#Puget Sound QGIS User Group landing page
All of our meeting updates and blog posts are curated through these files. Check out the wiki for details on how the website works and how to edit or add content.

###Site Development
The site is built on Jekyll and Github Pages, while the template files, JavaScript, and CSS are all hand-rolled by the members of PSQGIS.

If you're interested in helping out with the development of the site, please feel free to fork and edit locally before creating a pull-request. The following steps assume you have Jekyll 2.0 installed (including jekyll-sitemap, perhaps by: gem install jekyll-sitemap) and running properly on your machine.

###Fork this repository into your own working repo
Clone your newly created repository into your local machine
Navigate into the newly created cugos.github.com directory.
Run jekyll, which will serve the site at localhost:4000 and watch for changes.
Commit and push your changes to your forked repository
Create a pull request to merge your changes into the cugos master repository!
Have a beer!
Command line steps after forking the repository:
```
git clone https://github.com/YOUR-USERNAME/psqgis.github.io.git
cd psqgis.github.io
jekyll serve --watch
...make changes...

git add --all
git commit -m 'YOUR COMMIT MESSAGE'
git push origin master
```
Create a pull request between your repository and this repository.

