# B2Bi-SFG-on-Daffy-RHOCP

Auto-installation scripts for IBM-Sterling B2Bi-SFG.

These BASH shell scripts were developed to simplify the basic installation of containers for IBM Sterling B2Bi-SFG on RHOCP.

Note: If you have access to IBM Techzone you may provision a ROKS cluster for this installation.

## Basic assumptions:

- You are using a UNIX/Linux bastion host to install and run the scripts.
- You have created a file containing your IBM software entitlement key on the bastion host.  This key will allow access to the IBM B2Bi/SFG software on the IBM Container registry.
- You have access to the ROKS cluster where you will be installing this software.
- You know the ingress subdomain of the cluster where you will be installing this software.  This is available on the cluster dashboard webpage.

## Installation:

1. Download the tar file to your bastion host and place it in an empty directory. Then type the following to expand the tar file:

<pre><code><b>tar xvzf</b> ./Latest-Cluster-Autoinstall-Scripts.tgz
</code></pre>

2. Install the OpenShift command line tools if you haven't already done so:

<pre><code><b>./1-install-tools.sh</b>
</code></pre>

3. Open the web console and copy the login token, then at the shell command line use that token to log into your cluster.

#### Example:

<pre><code><b>oc</b> login --token=sha256~041TPoNcmmgheURy6d8C84edB4E6Buu2KYfXopJfyRg --server=https://c000-e.us-south.containers.cloud.ibm.com:31177</code></pre>

4. Finally, type this command to begin the installation:

<pre><code><b>./2-install-B2Bi-SFG-cluster.sh</b> <i>AdminEmailAddress</i> <i>ReleaseName</i> <i>NameSpace</i> <i>DB2aaSFlag</i> <i>IngressSubDomain</i> <i>IBM-Entitlement-Key-File</i></code></pre>


#### Where:

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
