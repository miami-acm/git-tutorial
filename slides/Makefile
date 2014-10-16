index.html : slides.rst
	pandoc -t revealjs -s -o index.html slides.rst

gh-pages : index.html
	git checkout gh-pages
	cd ..
	tree
	mv slides/index.html ./index.html
	git add index.html
	git commit
