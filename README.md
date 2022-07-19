# B2Bi-SFG-on-Daffy-RHOCP
Auto-installation scripts for IBM-Sterling B2Bi-SFG

These BASH shell scripts were developed to simplify the basic installation of containers for IBM Sterling B2Bi-SFG on RHOCP.

Installation:

Download the tar file and place it in your $HOME directory, then type:

1. tar xvzf ./Latest-Cluster-Autoinstall-Scripts.tgz

2. Log into OpenShift and make a copy of the ingress subdomain for your cluster.

3. Open the web console and copy the login token, then at the shell command line use that token to log into your cluster. 

Finally, type in this command:

./2-install-B2Bi-SFG-cluster.sh _AdminEmailAddress_ _ReleaseName_ _NameSpace_ _DB2aaSFlag_ _IngressSubDomain_ _<IBM-Entitlement-Key-File>_
  
Where:
  
  AdminEmailAddress:        Email address of the cluster administrator.
  ReleaseName:              Name of the release for this cluster install.
  NameSpace:                A unique namespace prefix for the resources that will be created for this cluster.
  DB2aaSFlag:               Use a DB2 service in a cloud - Y or N.
  IngressSubDomain:         Cluster ingress sub-domain.
  IBM-Entitlement-Key-File: Full path to a file containing your entitlement key.

  Note:
  
  DB2 as a Service functionality is not available yet.
  
