# AptRepo

Internet Connected Computer
~~~~~~~~~~~~~~~~~~~~~~~~~~~

sudo apt install --download-only <packagelist>

sudo mkdir ~/repo
cp /var/cache/apt/archive/*.deb ~/repo

sudo bash -c 'dpkg-scanpackages ~/repo /dev/null | gzip -c9 > ~/repo/Packages.gz'

copy repo dir to remote computer (eg via scp)


Isolated Computer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

sudo mkdir /opt/apt
sudo cp <other repo> /opt/apt

echo "deb file:/opt/apt ./" > /tmp/my-local.list
sudo mv /tmp/my-local.list /etc/apt/sources.list.d/my-local.list
sudo apt-get update --allow-insecure-repositories

sudo apt install <packageslist>
