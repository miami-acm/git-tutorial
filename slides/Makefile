index.html : slides.rst
	pandoc -t revealjs -s -o index.html slides.rst

gh-pages : index.html
	mv index.html ..
