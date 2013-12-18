VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  #Ubuntu 10.04
  config.vm.define "ubuntu10" do |ubuntu10_config|
    ubuntu10_config.vm.box = "ubuntu_10.04_x64"
    ubuntu10_config.vm.box_url = "http://opscode-vagrant-boxes.s3.amazonaws.com/ubuntu10.04-gems.box"
    ubuntu10_config.vm.hostname = "ubuntu10.qubell.int"
    ubuntu10_config.vm.network "forwarded_port", guest: 8080, host: 8080
    ubuntu10_config.vm.network "public_network", :bridge => 'en0: Wi-Fi (AirPort)'
    ubuntu10_config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "2048"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
    end
    ubuntu10_config.vm.provision "chef_solo" do |chef| 
      chef.log_level = "debug"
      chef.cookbooks_path = "cookbooks"
      chef.add_recipe "mysql::server"
      chef.add_recipe "mysql-component::db_create"
      chef.add_recipe "mysql-component::sql_query"
      chef.add_recipe "mysql-component::user_modify"
        chef.json = {
          "mysql" => {
            "server_root_password" => "uR1zaebah0Qu",
            "server_repl_password" => "uR1zaebah0Qu",
            "server_debian_password" => "uR1zaebah0Qu"
          },
          "mysql-component" => {
            "db_name" => "petclinic",
            "host" => ["%"],
            "db_user" => "petclinic_user",
            "db_pass" => "petclinic_pass",
            "sql_url" => ["https://raw.github.com/qubell/starter-java-web/master/src/main/resources/db/mysql/petclinic-mysql-schema.sql", "https://raw.github.com/qubell/starter-java-web/master/src/main/resources/db/mysql/petclinic-mysql-dataload.sql"],
            "privileges" => ["all"]
          }
        }
    end
  end
  
  #Ubuntu 12.04
  config.vm.define "ubuntu12" do |ubuntu12_config|
    ubuntu12_config.vm.box = "ubuntu_12.04_x64"
    ubuntu12_config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/precise/current/precise-server-cloudimg-amd64-vagrant-disk1.box"
    ubuntu12_config.vm.hostname = "ubuntu12.qubell.int"
    ubuntu12_config.vm.network "forwarded_port", guest: 8080, host: 8090
    ubuntu12_config.vm.network "public_network", :bridge => 'en0: Wi-Fi (AirPort)'
    ubuntu12_config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "2048"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
    end
    ubuntu12_config.vm.provision "chef_solo" do |chef| 
      chef.log_level = "debug"
      chef.cookbooks_path = "cookbooks"
      chef.add_recipe "mysql::server"
      chef.add_recipe "mysql-component::db_create"
      chef.add_recipe "mysql-component::sql_query"
      chef.add_recipe "mysql-component::user_modify"
        chef.json = {
          "mysql" => {
            "server_root_password" => "uR1zaebah0Qu",
            "server_repl_password" => "uR1zaebah0Qu",
            "server_debian_password" => "uR1zaebah0Qu"
          },
          "mysql-component" => {
            "db_name" => "petclinic",
            "host" => ["%"],
            "db_user" => "petclinic_user",
            "db_pass" => "petclinic_pass",
            "sql_url" => ["https://raw.github.com/qubell/starter-java-web/master/src/main/resources/db/mysql/petclinic-mysql-schema.sql", "https://raw.github.com/qubell/starter-java-web/master/src/main/resources/db/mysql/petclinic-mysql-dataload.sql"],
            "privileges" => ["all"]
          }
        }
    end
  end
  
  #CentOS 5.6
  config.vm.define "centos56" do |centos56_config|
    centos56_config.vm.box = "centos_5_x64"
    centos56_config.vm.box_url = "https://dl.dropbox.com/u/7196/vagrant/CentOS-56-x64-packages-puppet-2.6.10-chef-0.10.6.box"
    centos56_config.vm.hostname = "centos56.qubell.int"
    centos56_config.vm.network "forwarded_port", guest: 8080, host: 9000
    centos56_config.vm.network "public_network", :bridge => 'en0: Wi-Fi (AirPort)'
    centos56_config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "2048"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
    end
    centos56_config.vm.provision "chef_solo" do |chef| 
      chef.log_level = "debug"
      chef.cookbooks_path = "cookbooks"
      chef.add_recipe "mysql::server"
      chef.add_recipe "mysql-component::db_create"
      chef.add_recipe "mysql-component::sql_query"
      chef.add_recipe "mysql-component::user_modify"
        chef.json = {
          "mysql" => {
            "server_root_password" => "uR1zaebah0Qu",
            "server_repl_password" => "uR1zaebah0Qu",
            "server_debian_password" => "uR1zaebah0Qu"
          },
          "mysql-component" => {
            "db_name" => "petclinic",
            "host" => ["%"],
            "db_user" => "petclinic_user",
            "db_pass" => "petclinic_pass",
            "sql_url" => ["https://raw.github.com/qubell/starter-java-web/master/src/main/resources/db/mysql/petclinic-mysql-schema.sql", "https://raw.github.com/qubell/starter-java-web/master/src/main/resources/db/mysql/petclinic-mysql-dataload.sql"],
            "privileges" => ["all"]
          }
        }
    end
  end

  #CentOS 6.3
  config.vm.define "centos63" do |centos63_config|
    centos63_config.vm.box = "centos_6_x64"
    centos63_config.vm.box_url = "https://dl.dropbox.com/u/7225008/Vagrant/CentOS-6.3-x86_64-minimal.box"
    centos63_config.vm.hostname = "centos63.qubell.int"
    centos63_config.vm.network "forwarded_port", guest: 8080, host: 9010
    centos63_config.vm.network "public_network", :bridge => 'en0: Wi-Fi (AirPort)'
    centos63_config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "2048"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
    end
    centos63_config.vm.provision "chef_solo" do |chef| 
      chef.log_level = "debug"
      chef.cookbooks_path = "cookbooks"
      chef.add_recipe "mysql::server"
      chef.add_recipe "mysql-component::db_create"
      chef.add_recipe "mysql-component::sql_query"
      chef.add_recipe "mysql-component::user_modify"
        chef.json = {
          "mysql" => {
            "server_root_password" => "uR1zaebah0Qu",
            "server_repl_password" => "uR1zaebah0Qu",
            "server_debian_password" => "uR1zaebah0Qu"
          },
          "mysql-component" => {
            "db_name" => "petclinic",
            "host" => ["%"],
            "db_user" => "petclinic_user",
            "db_pass" => "petclinic_pass",
            "sql_url" => ["https://raw.github.com/qubell/starter-java-web/master/src/main/resources/db/mysql/petclinic-mysql-schema.sql", "https://raw.github.com/qubell/starter-java-web/master/src/main/resources/db/mysql/petclinic-mysql-dataload.sql"],
            "privileges" => ["all"]
          }
        }
    end
  end
end
