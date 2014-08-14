# Chef metal driver for Hanlon

This is a chef-metal driver for Hanlon; currently this relies on a
slightly modified version of Hanlon and the hanlon-api Ruby gem.

Documentation forthcoming, this is a super-early release. 

Example usage (currently):

```
require 'chef_metal_hanlon'

machine 'web00' do
  recipe 'apache2'

  machine_options :image_uuid => '438CHtqAlKJoVHvNEVSArf',
    :model => {
        label: 'Chef metal model',
        template: 'ubuntu_precise',
        hostname_prefix: 'test',
        domainname: 'testdomain.com',
        root_password: 'test1234'
    },
    :policy => {
        label_prefix: 'Chef Metal Policy',
        template: 'linux_deploy',
        tags: 'vmware_vm'
    },
    :convergence_options => {
        :chef_version => '11.14.2',
        :chef_server_url => 'https://api.opscode.com/organizations/my-org'
    }

end
```
