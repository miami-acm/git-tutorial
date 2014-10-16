index.html : slides.rst
	pandoc -t revealjs -s -o index.html slides.rst

gh-pages : index.html
	git checkout gh-pages
	cd ..
	mv slides/index.html ./index.html
	git add index.html
	git commit
