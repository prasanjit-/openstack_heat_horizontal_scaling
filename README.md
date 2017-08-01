# Command to launch Stack
`. adminrc`
`openstack stack create -t cirros_server_group.yaml scaling_group`


# Command to update Stack
(Modify the instance count in server_group file before updating)
`. adminrc`
`openstack stack update -t cirros_server_group.yaml scaling_group`
