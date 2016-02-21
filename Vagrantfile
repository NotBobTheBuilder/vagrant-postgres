Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "forwarded_port", guest: 5432, host: 5432

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y postgresql postgresql-contrib postgresql-9.3-postgis-2.1{,-scripts}
    sudo -u postgres createuser vagrant
    sudo -u postgres createdb -O vagrant vagrant
    sudo -u postgres psql -c "ALTER ROLE vagrant WITH PASSWORD 'vagrant';"
    sudo -u postgres psql -d vagrant -c "CREATE EXTENSION postgis;"
    sudo sh -c "echo host all all 0.0.0.0/0 md5 >> /etc/postgresql/9.3/main/pg_hba.conf"
    sudo sh -c "echo listen_addresses = \\'*\\' >> /etc/postgresql/9.3/main/postgresql.conf"
    sudo service postgresql restart
  SHELL
end


