# tmpMaptoolDocs

apt-get update

apt install php7.2-cli

sudo apt-get install php7.2-xml

sudo apt-get install php-mbstring

wget https://github.com/jgm/pandoc/releases/download/2.7.3/pandoc-2.7.3-1-amd64.deb
sudo pgk -i pandoc-2.7.3-1-amd64.deb

git clone https://github.com/outofcontrol/mediawiki-to-gfm.git

cd mediawiki-to-gfm

php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"

php -r "if (hash_file('sha384', 'composer-setup.php') === 'a5c698ffe4b8e849a443b120cd5ba38043260d5c4023dbf93e1558871f1f07f58274fc6f4c93bcfd858c6bd0775cd8d1') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

php composer-setup.php

php -r "unlink('composer-setup.php');"

php composer.phar update --no-dev


Paste all page names into Mediawiki/Special Pages/Export (get them from http://lmwcs.com/rptools/wiki/Special:AllPages, export from all pages).

sed -i '/Do not edit this line/d' ./MapToolDoc-20190913172147.xml

./convert.php --filename=MapToolDoc-20190913172147.xml --output=output --format=gfm


Look at the output. :)
Macros look bad. Export needs some sed/awk love to remove {{macro and convert innards to proper formatting.

