# Known issues

Here we collect all the known issues and, if available, any temporary fix/workaround to them. 
Please consult this section carefully before contacting anyone.
If you encounter any new issue which is not listed below, please [contact](../support.md) us 

##SSH Access
!!! failure
In trying to ssh to Newton some users experience the following error:

```
Unable to negotiate with 160.97.54.193 port 22: no matching host key type found. Their offer: ssh-rsa,ssh-dss
```

This might be cause by the outdate version of OpenSSH in Newton which we cannot currently upgrade.

!!! success
A workaround is to specify to ssh-agent which encryption method to use among those offered by the host.
This can be done by adding the following option

```
ssh -o HostKeyAlgorithms=ssh-rsa <username>@newton.hpcc.unical.it
```


##SSH keeps asking the password
!!! failure
Some users pointed that when trying to use an authentication based on a private-public ssh key pair the ssh keeps asking for the password.

!!! success

```
ssh -o PubkeyAcceptedKeyTypes=+ssh-rsa <username>@newton.hpcc.unical.it
```

If the above does not solve the problem, please follow the instructions [here](resources/access.md) on how to create correctly a public-private key pair and upload the public part in Newton.

