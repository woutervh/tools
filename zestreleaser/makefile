# This is a comment.
# Important: You *must* indent using <TAB>s, not spaces.

PYTHON_VERSION=`~/bin/pyenv versions --bare |grep '3.11'| tail -n 1`
# PYTHON_VERSION='3.11.2'


.PHONY: install
install: create-venv upgrade-pip install-packages install-symlinks


.PHONY: update
update: upgrade-pip install-packages


.PHONY: create-venv
create-venv:
	- python -m venv .


.PHONY: upgrade-pip
upgrade-pip:
	- bin/python -m pip install --upgrade pip


.PHONY: install-packages
install-packages:
	- bin/pip install --upgrade zest.releaser


.PHONY: install-symlinks
install-symlinks:
	@ echo -e "Create symlinks in ~/bin/"
	- ln -fs $(realpath bin/release) ~/bin/
	- ln -fs $(realpath bin/fullrelease) ~/bin/
	- ln -fs $(realpath bin/prerelease) ~/bin/
	- ln -fs $(realpath bin/longtest) ~/bin/