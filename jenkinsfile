#Create vhosts main folder & add permissions
sudo mkdir /srv/www/vhosts
chmod -R 775 vhosts
cd /srv/www/vhosts

#Create repo folders & add permissions

#for dir in PsCore Common Interface Logs Mounts PsCoreConfig
for dir in PsCore Common PsCoreConfig Interfaces PsLibraries
do 
  sudo mkdir -p trunk/${dir}
  sudo  mkdir -p rapidstage/${dir}
  sudo  mkdir -p rapidproduction/${dir}
  sudo  mkdir -p standardstage/${dir}
  sudo  mkdir -p standardproduction/${dir}

  sudo chmod -R 775 trunk/${dir} 
  sudo chmod -R 775 rapidstage/${dir} 
  sudo chmod -R 775 rapidproduction/${dir} 
  sudo chmod -R 775 standardstage/${dir} 
  sudo chmod -R 775 standardproduction/${dir} 
done


# Checkout Mounts folder
cd  /srv/www/vhosts/Mounts
svn checkout https://code.propertysolutions.com/svn/Mounts/ . > setup.log


#Check out repositories

for dir in PsCore Common
do
    cd  /srv/www/vhosts/trunk/PsCore
    svn checkout https://code.propertysolutions.com/svn/PsCore/trunk/ . >  /srv/www/vhosts/setup.log &
    cd  /srv/www/vhosts/trunk/Common
    svn checkout https://code.propertysolutions.com/svn/PsCoreCommon/trunk/ . > /home/likewise-open/DC2/$ldap_name/Desktop/setup.log &
    cd  /srv/www/vhosts/trunk/PsLibraries
    svn checkout https://code.propertysolutions.com/svn/PsLibraries/trunk/ . > /home/likewise-open/DC2/$ldap_name/Desktop/setup.log &

done

sudo mkdir  /srv/www/vhosts/Logs
sudo chmod -R 775  /srv/www/vhosts/Logs

sudo mkdir  /srv/www/vhosts/Mounts
sudo chmod -R 775  /srv/www/vhosts/Mounts

sudo mkdir  /srv/www/vhosts/vhosts
sudo chmod -R 775  /srv/www/vhosts/vhosts
