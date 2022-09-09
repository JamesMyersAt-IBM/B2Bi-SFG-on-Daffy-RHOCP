# B2Bi-SFG-on-Daffy-RHOCP

Auto-installation scripts for IBM-Sterling B2Bi-SFG.

These BASH shell scripts were developed to simplify the basic installation of containers for IBM Sterling B2Bi-SFG on RHOCP.

Note: If you have access to IBM Techzone you may provision a ROKS cluster for this installation.

## Basic assumptions:

- You have an entitlement key file for access to the B2Bi/SFG software from DSW.
- You are using a UNIX/Linux bastion host to install and run the scripts.

## Installation:

1. Download the tar file to your bastion host, place it in an empty directory then expand the tar file:

<pre><code><b>tar xvzf</b> ./Latest-Cluster-Autoinstall-Scripts.tgz
</code></pre>

2. Install the OpenShift command line tools if you haven't already done so:

<pre><code><b>./1-install-tools.sh</b>
</code></pre>

3. Open the web console and copy the login token, then at the shell command line use that token to log into your cluster. 

Finally, type in this command:

<pre><code><b>./2-install-B2Bi-SFG-cluster.sh</b> <i>AdminEmailAddress</i> <i>ReleaseName</i> <i>NameSpace</i> <i>DB2aaSFlag</i> <i>IngressSubDomain</i> <i>IBM-Entitlement-Key-File</i></code></pre>


## Where:

| Parameter                   | Description                                                                          |
| :---                        | :---                                                                                 |
| **AdminEmailAddress:**      | *Email address of the cluster administrator.*                                        |
| **ReleaseName:**            |  *Name of the release for this cluster install.*                                     |
| **NameSpace:**              | *A unique namespace prefix for the resources that will be created for this cluster.* |
| **DB2aaSFlag:**             | *Use a DB2 service in a cloud - Y or N.*                                             |
| **IngressSubDomain:**       | *Cluster ingress sub-domain.*                                                        |
| **IBM-Entitlement-Key-File:**| *Full path to a file containing your entitlement key.*

#  Note:
  
  DB2 as a Service functionality is not available yet.
