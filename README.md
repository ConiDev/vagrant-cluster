# Vagrant-Cluster
A simple and easy vagrantfile to spin up multiple vm. The default is 2 masters and 4 slaves, you can modify the BOXES variables if needed.

> [!NOTE]  
> You might need / want to change the private network to fit you're needs.

## Overview
- [Requirements](#requirements)
- [Usage](#usage)
- [License](#license)

## Requirements
- [Vagrant](https://www.vagrantup.com/)
- [Virtualbox](https://www.virtualbox.org/)

## Usage
You can find more instructions on the official documentation [here](https://developer.hashicorp.com/vagrant/docs).  

- Create / Launch all vms  
  ```vagrant up```

- Stop all vms  
  ```vagrant halt```

- Destroy all vms  
  ```vagrant destroy -f```

## License
This Project is under the [MIT License](/LICENSE)
