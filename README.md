# Create a Storage Spaces Direct (S2D) Scale-Out File Server (SOFS) Cluster with Windows Server 2016 on an existing VNET
This template will create a Storage Spaces Direct (S2D) Scale-Out File Server (SOFS) cluster using Windows Server 2016 in an existing VNET and Active Directory environment.

This template creates the following resources by default:

+	A Premium Storage Account for storing VM disks for each storage node
+   A Standard Storage Account for a Cloud Witness
+	A Windows Server 2016 cluster for storage nodes, provisioned for Storage Spaces Direct (S2D) and the Scale-Out File Server (SOFS) role
+	One Availability Set for the cluster nodes

Click the button below to deploy from the portal:

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Faaronlafferty%2FSOFS%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Faaronlafferty%2FSOFS%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

## Notes

+	The default settings for storage are to deploy using **premium storage**, which is **strongly** recommended for S2D performance.  When using Premium Storage, be sure to select a VM size (DS-series, GS-series) that supports Premium Storage.

+   The default settings deploy 2 data disks per storage node, but can be increased to up to 32 data disks per node.  When increasing # of data disks, be sure to select a VM size that can support the # of data disks you specify.

+ 	The default settings for compute require that you have at least 2 cores of free quota to deploy.

+ 	The images used to create this deployment are
	+ 	Windows Server 2016 Datacenter Edition - Latest Image

+	To successfully deploy this template, be sure that the subnet to which the storage nodes are being deployed already exists on the specified Azure virtual network, AND this subnet should be defined in Active Directory Sites and Services for the appropriate AD site in which the closest domain controllers are configured.


Tags: ``cluster, ha, storage spaces, storage spaces direct, S2D, windows server 2016, ws2016``
