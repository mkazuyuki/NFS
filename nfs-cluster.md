# EXPRESSCLUSTER X Quick Start Guide for NFS server on Linux

## OS settings

1. Install NFS server

		# Example for CentOS 7 and NFS ver.4
		yum -y install nfs-utils

2. Configure it to manual startup

		systemctl disable nfs

3. Modify /etc/exports for NFS server to export the mount point of (mirror) disk resource.

## EC settings

0. Create a cluster with File Server Agent
1. Add a failover group for NFS service
2. Add a disk, md or hd resource
3. Add a execute resource

	1. edit start.sh / stop.sh as below

		- start.sh

				systemctl start nfs

		- stop.sh

				systemctl stop nfs
4. Add FIP resource 
5. Configure the starting order of the resources as below

	1. disk, md or hd resource
	2. exec resource which is defined as above.
	3. FIP resource

6. Add NFS Monitor resource