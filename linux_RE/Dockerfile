FROM archlinux:latest

MAINTAINER lopqto <morpix@protonmail.com>

# availabe command => gdb-peda gef radare2

RUN echo -e "## Germany\nServer = https://mirror.23media.com/archlinux/\$repo/os/\$arch" > /etc/pacman.d/mirrorlist

RUN pacman -Syu --noconfirm 

RUN pacman -S radare2 gdb git wget python-pip gcc python-keystone keystone python-capstone capstone python-ropper ropper --noconfirm

RUN mkdir ~/tools

RUN git clone https://github.com/longld/peda.git ~/tools/peda

RUN wget -O ~/tools/gdbinit-gef.py -q https://github.com/hugsy/gef/raw/master/gef.py

RUN echo -e "alias gef='gdb -x ~/tools/gdbinit-gef.py -q '\nalias gdb-peda='gdb -x ~/tools/peda/peda.py'" > /root/.bashrc