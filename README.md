# chef_docker_jenkins

```
# Create test environment
$ kitchen create

# Test in kitchen environment
$ kitchen converge

# Verify
$ kitchen login

# Destroy kitchen environment
$ kitchen destroy

# Check node(s)
$ knife node list

# Check info about node
$ knife node show node1-centos

# Check cookbooks
$ knife cookbook list

# Upload new version (metadata.rb)
$ knife cookbook upload chef_docker_jenkins #fails

# Install missing dep cookbook (docker) from supermarket
$ knife cookbook site install docker 4.0.1

# Upload dependent cookbook
$ knife cookbook upload docker 4.0.1

# Try again (check with list)
knife cookbook upload chef_docker_jenkins

# Add recipe to run list
$ knife node run_list add node1-centos 'recipe[chef_docker_jenkins]' 

# Upload new version (metadata.rb)
$ knife node upload node1-centos 'recipe[chef_docker_chef_docker]' 
$ knife ssh 'name:node1-centos' 'sudo chef-client' --ssh-user xxx --ssh-password 'xxx' --attribute ipaddress
```



