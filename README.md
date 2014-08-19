ChefDK Box
==========

Packer template to prepare Chef Development Environment with ChefDK and
Docker(kitchen-docker)


## Environment

|Box                      |OS               |Tools                                                    |
|-------------------------|-----------------|---------------------------------------------------------|
|centos-6.5-x86_64-chef-dk|CentOS 6.5 x86_64|Docker, ChefDK, kitchen-docker, git, vim, zsh + oh-my-zsh|


## Requirement

* Virtual Box
* Vagrant
* Packer


## Usage

Make vagrant box image by using Packer:

```
$ git clone git@github.com:tkak/chef-dk-box.git
$ cd packer
$ packer build centos-6.5-x86_64.json
$ vagrant box add centos-6.5-x86_64-chef-dk ../builds/virtualbox/centos-6.5-x86_64-chef-dk.box
$ vagrant box list
```

Create Chef development environment on Virtual Box:

```
$ cd /path/to/chef-dk-box
$ vagrant up
$ vagrant ssh
```

Start Chef cookbook development:

```
i.g.)
$ zsh  ## If you want to use zsh
$ git clone https://github.com/tkak/sample-chef-repo.git
$ cd sample-chef-repo
$ kitchen init --driver=kitchen-docker 

coding...

$ kitchen test
```

## References

* [ChefDK](http://downloads.getchef.com/chef-dk/)
* [Packer](http://www.packer.io/)
* [Bento](https://github.com/opscode/bento)
* [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
* [sample-chef-repo](https://github.com/tkak/sample-chef-repo)


## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Run style checks and RSpec tests (`bundle exec rake`)
4. Commit your changes (`git commit -am 'Add some feature'`)
5. Push to the branch (`git push origin my-new-feature`)
6. Create new Pull Request

