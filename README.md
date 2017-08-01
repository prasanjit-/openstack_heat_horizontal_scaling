# SCALING OPENSTACK INSTANCES USING HEAT TEMPLATES

Using Heat ResourceGroup resources

This has come up a few times recently, so I wanted to share a how to showing how (and how not) to use the group resources in Heat, e.g OS::Heat::ResourceGroup and OS::Heat::AutoScalingGroup.

The key thing to remember when dealing with these resources is that they can multiply any number of resources (expressed as a heat stack), not just individual resources. This is a very cool feature when you get your head around it! :)

Lets go through a worked example, where we use ResourceGroup to create 3 identical servers. You can modify the `cirros_server_group.yaml` file to Scale Up/Down the stack and re-launch.


# Command to launch Stack
`openstack stack create -t cirros_server_group.yaml scaling_group`


# Command to update Stack (Scale Up/Down)
(Modify the instance count in server_group file before updating)
`openstack stack update -t cirros_server_group.yaml scaling_group`

```Note: This is not Auto-scaling. This is manual scaling based which can be used for Horizantal and vertical scaling of Stacks ```
