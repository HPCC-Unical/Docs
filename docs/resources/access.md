In here we describe how to access the resources.
All resources at HPCC have an SSH access.
They can only be reached from within the Unical network.
If you want to access them from outside you will need to request a VPN account. Please follow the instructions on the Unical website.

#Password
When your account is created on one of our machines you will get a password. 
You can then access the requested resource using `ssh`.
Opena a terminal and use the command:

```
ssh <username>@resource_name.hpcc.unical.it
```

When prompted, digit your password to access.
Please remember to change your password frequently in order to ensure

#Private-public key authentication
A more secure, and also smoother, way of accessing our resources is through a private-public key authentication.
This can be setup in few easy steps and has the advantage of not requiring you to digit your password at every access.

##Create the key pair
To create your key pair you can use the command:

```
ssh-keygen -t rsa -b 4096
```
When asked for a file name, you can either use the standard one or create a specific one. It is a good practice to use different pairs for different machines you need to access.
Let us assume that you used the name `id_rsa_<hostname>` where `<hostname>` is the hostname of the machine you will access via the newly generated key pair.

When asked for a passphrase you can avoid to create one by pressing enter although it is good practice to protect your private key with a passphrase.

This will create a pair of keys in the folder `~/.ssh/`.


##Uplodad the key on the host
Once the pair is created, you will now need to upload the public part of the key to the machine you will access. You can do it in two ways:

* Manually by copying the public key from `~/.ssh/id_rsa_<hostname>.pub`on your **local machine** to the file `~/.ssh/authorized_keys` on the **host machine**
* Use the `ssh-copy-id` command as follows:
```
ssh-copy-id -i $HOME/.ssh/id_rsa_<hostname>.pub <username>@<resource>.hpcc.unical.it
```

##Accessing the remote machine
You can now access the remote machine using the command:
```
ssh -i $HOME/.ssh/id_rsa_<hostname> <username>@<resource>.hpcc.unical.it
```

Please notice that you can drop the `-i $HOME/.ssh/id_rsa_<hostname>` if your are using the default name for the key file name (id_rsa).

##SSH config file
To make the access even easier you can setup the configuration of the ssh access to the remote machine using the `config` file of `ssh`.
To do so you can append the following to the file `$HOME/.ssh/config`:

```
Host <resource>
Hostname <resource>.hpcc.unical.it
User <username>
IdentityFile %d/.ssh/id_rsa_<hostname>
IdentitiesOnly yes
ForwardAgent yes
```

Once you have saved the file it will be enough to run the command:
```
ssh <resource>
```
to access the remote machine.
