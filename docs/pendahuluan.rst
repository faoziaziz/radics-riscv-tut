Memulai dengan RISC-V
===========================

RISC-V menjadi salah satu topik menarik pada perkembangan prosesor kali ini. Seiring dengan berkembangnya waktu, pengembangan laptop seperti MacOS sudah beralih dari arsitektur 
intel menadi arsitektur arm. Kesempatan ini menjadi menarik mengingat bahwa arm adalah processor yang berjeniskan RISC. Sayangnya akses pada arsitektur arm dibatasi oleh 
arsitekturnya yang memang propretieri. Untuk itu ada alternative lain yaitu RISC-V. 

Perjalanan menggunakan RISC-V mungkin akan cukup terjal, mengingat bahwa arsitektur ini juga masih dalam tahap pengembangan, artinya beberapa operating sistem yang berjalan 
pada umumnya seperti Ubuntu atau Windows mungkin belum berjalan secara kompactible. Sekalipun RISC-V masih tahap pengembangan hal itu juga merupakan pertanda bahwa kita bisa 
menjadi early-adopter. Iya ini adalah peluang untuk para periset, atau para pegiat startup untuk melakukan pekerjaannya mengoptimalisasi RISC-V.

Struktur dari risc bisa kita bangun dengan menggunakan FPGA, sebenernya arsitekture ARM ataupun CISC lain juga bisa namun kita bisa mengakses astiektur dari RISC sehingga 
sangat disarankan sekali untuk membangunnya dengan arsitektur RISC-V ini.


Install Beberapa pendukung
-------------------------

untuk lebih jelasnya kamu bisa ke `RiscvGit`_ untuk informasi lebih lanjut.
.. code-block:: bash
    git clone https://github.com/riscv/riscv-gnu-toolchain

kemudian recursive module
.. code-block:: bash 
    sudo apt-get install autoconf automake autotools-dev curl python3 python3-pip libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev ninja-build git cmake libglib2.0-dev

kemudian buat direktory untuk pembuatan crosscompilerna
.. code-block:: bash 
    sudo mkdir -p /opt/riscv
    sudo chown faoziaziz:faoziaziz /opt/riscv

ganti faoziaziz dengan username yang kalian punya 

.. code-block:: bash
    ./configure --prefix=/opt/riscv
    make

jika kalian ingin menggunakan multilib gunakan perintah berikut 

.. code-block:: bash
    make clean 
    ./configure --prefix=/opt/riscv --enable-multilib
    make 

Code Block Syntax
=================

To include a bash code block in reST, use the following syntax:

.. code-block:: bash

   # This is a comment in bash
   echo "Hello, World!"
   ls -la

Examples
========

Creating a Bash Script
----------------------

.. code-block:: bash

   #!/bin/bash
   # A simple bash script

   echo "Starting the script..."

   for i in {1..5}; do
       echo "Count: $i"
       sleep 1
   done

   echo "Script finished."

.. _RiscvGit: https://github.com/riscv-collab/riscv-gnu-toolchain
