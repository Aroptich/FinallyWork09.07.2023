# 1
mkdir AnimalNursery
cd AnimalNursery
cat > homeAnimals
cat > packAnimals
cat Animals
mv Animals MansFriends
ls -ali
# 2 
mkdir AnimalNurseryCpoy
ls
cd AnimalNursery
mv MansFriends /home/alexsandr/AnimalNurseryCopy/
cd ..
ls
# 3
wget https://dev.mysql.com/get/mysql-apt-config_0.8.23-1_all.deb
dpkg -i mysql-apt-config_0.8.23-1_all.deb
apt-get update
apt-get install mysql-server
# 4
wget https://download.docker.com/linux/ubuntu/dists/jammy/pool/stable/amd64/docker-ce-cli_24.0.4-1~ubuntu.22.04~jammy_amd64.deb
dpkg -i docker-ce-cli_24.0.4-1~ubuntu.22.04~jammy_amd64.deb
dpkg -r docker-ce
dpkg -r docker-ce-cli
