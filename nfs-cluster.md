# EXPRESSCLUSTER X Quick Start Guide for NFS server on Linux

## OS settings

1. Install NFS server
2. Configure it to manual startup

		systemctl disable nfs

3. Modify /etc/exports for NFS server to export the mount point of (mirror) disk resource.

## EC settings

0. Create a cluster
1. Add a failover group for NFS service
2. Add a (mirror) disk resource
3. Add a execute resource
3.1. edit start.sh / stop.sh as below

	- start.sh

		service nfs start

	- stop.sh

		service nfs stop
4. Add FIP resource 
5. Configure the starting order of the resources as below

	1. disk resource (or md resource)
	2. exec resource which is defined as above.
	3. FIP resource

6. Add NFS Monitor resource