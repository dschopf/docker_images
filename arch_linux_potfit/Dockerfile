from archlinux/base

ENV args="--noconfirm --noprogressbar --color never"

RUN pacman -Syu ${args} && \
	pacman -S --needed ${args} base-devel git pyalpm jq expac diffstat python-numpy pacutils parallel wget cmake gcc-fortran xxd && \
	cd /tmp && \
	sudo -u nobody git clone --quiet https://aur.archlinux.org/aurutils.git && \
	cd aurutils && \
	sudo -u nobody makepkg --noprogress --noconfirm -fsr && \
	pacman -U ${args} aurutils-*pkg.tar.xz && \
	cd .. && \
	sudo -u nobody aur fetch kim-api && \
	cd kim-api && \
	sudo -u nobody makepkg --noprogress --noconfirm -fsr && \
	pacman -U ${args} kim-api*pkg.tar.xz

