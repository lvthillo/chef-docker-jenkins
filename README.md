# chef_docker_jenkins

## Test setup

```
# Create test environment
$ kitchen create

# Test in kitchen environment
$ kitchen converge

# Verify
$ kitchen login

# Destroy kitchen environment
$ kitchen destroy
```

## Upload cookbook

```
# Check node(s)
$ knife node list

# Check info about node
$ knife node show node1-centos

# Check cookbooks
$ knife cookbook list

# install dependency (docker cookbook)
# berks install

# Upload new version (metadata.rb)
$ knife cookbook upload chef_docker_jenkins

# Add recipe to run list
$ knife node run_list add node1-centos 'recipe[chef_docker_jenkins]' 
```

## Execute chef-client 

```
# Upload new version (metadata.rb)
$ knife node upload node1-centos 'recipe[chef_docker_chef_docker]' 

$ knife ssh 'name:node1-centos' 'sudo chef-client' --ssh-user xxx --ssh-password 'xxx' --attribute ipaddress
```



