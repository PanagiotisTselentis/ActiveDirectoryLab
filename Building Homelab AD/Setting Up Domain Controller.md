I used a **Windows Server 2022** ISO file in order to build the Domain Controller.


## Setting up the VM
After the initial download, I setup the VM and when prompted for a password for the `Administrator` I used `P@$$w0rd!`

![](attachments/Pasted%20image%2020251127215827.png)

So after I logged in, I wanted to change the name of the PC, so I went to `View your PC Name` :

![](attachments/Pasted%20image%2020251127220228.png)

and I picked `Rename this PC`:

![](attachments/Pasted%20image%2020251127220343.png)

and I named it `HYDRA-DC`:

![](attachments/Pasted%20image%2020251127220448.png)

So after that, we want to make this server a Domain Controller, so we go to `Manage -> Add Roles and Features`:

![](attachments/Pasted%20image%2020251127220734.png)

and this Wizard will appear, so we hit `Next`:

![](attachments/Pasted%20image%2020251127220843.png)

We pick `Role-based or feature-based installation` and we hit `Next`:

![](attachments/Pasted%20image%2020251127220953.png)

We pick `Next`:

![](attachments/Pasted%20image%2020251127221035.png)

In the `Server Roles` the very important thing is to pick `Active Directory Domain Services` and then we pick `Next`:

![](attachments/Pasted%20image%2020251127221219.png)

In the `Features` section we just pick `Next`:

![](attachments/Pasted%20image%2020251127221322.png)

Again `Next`:

![](attachments/Pasted%20image%2020251127221402.png)

Pick on `Restart the destination server automatically if required` and then pick `Install` to install our Domain Controller:

![](attachments/Pasted%20image%2020251127221510.png)

After it finishes installing the Domain Controller we click on `Promote this server to a domain controller`:

![](attachments/Pasted%20image%2020251127221649.png)

We pick `Add a new forest` and we name whatever we want the `Root domain` and hit `Next`:

![](attachments/Pasted%20image%2020251127221824.png)

We pick a Password and I am going to use the same password as the administrator: `P@$$w0rd!` and then pick `Next`

![](attachments/Pasted%20image%2020251127222004.png)

And then we pick again `Next`:

![](attachments/Pasted%20image%2020251127222058.png)

The section `NetBIOS domain name` was populated by itself with the name `MARVEL` and we just pick `Next`:

![](attachments/Pasted%20image%2020251127222213.png)

We pick `Next` again:

![](attachments/Pasted%20image%2020251127222257.png)

Again we pick `Next`:

![](attachments/Pasted%20image%2020251127222324.png)

We see the message `All prerequisite checks passed successfully.` and we press `Install`:

![](attachments/Pasted%20image%2020251127222448.png)

After the Installation we see this message and we are prompted to reboot our system:

![](attachments/Pasted%20image%2020251127222638.png)

After that we see that when we try to log in we are entering to the domain `MARVEL`:

![](attachments/Pasted%20image%2020251127223235.png)

So after we are logged in we need to setup the `Cerificates Services`, which are used to verify identities in a domain controller and this is a form of enhanced security, because it allows us to use secure **LDAP (Lightweight Directory Access Protocol)**.

Again we go to `Manage -> Add Roles and Features`:

![](attachments/Pasted%20image%2020251127223514.png)

We follow the same drill as before, but in the `Server Roles` we pick `Active Directory Certificate Services`

![](attachments/Pasted%20image%2020251127223645.png)

and then we just pick `Next` until we get to `Confirmation` and we pick `Install`:

![](attachments/Pasted%20image%2020251127224225.png)

We pick `Configure Active Directory Certificate Services on the destination server`:

![](attachments/Pasted%20image%2020251127224348.png)

We pick `Next`:

![](attachments/Pasted%20image%2020251127224424.png)

We check the `Certification Authority`:

![](attachments/Pasted%20image%2020251127224521.png)

We pick `Enterprise CA` and hit `Next`:

![](attachments/Pasted%20image%2020251127224556.png)

We pick `Root CA` and hit `Next`:

![](attachments/Pasted%20image%2020251127224630.png)

We create a new private key:

![](attachments/Pasted%20image%2020251127224709.png)

With `SHA256` and hit `Next`:

![](attachments/Pasted%20image%2020251127224744.png)

![](attachments/Pasted%20image%2020251127224810.png)

![](attachments/Pasted%20image%2020251127224842.png)

![](attachments/Pasted%20image%2020251127224901.png)

And we finish it we pressing `Configure`:

![](attachments/Pasted%20image%2020251127224931.png)

After it is done we `Close`:

![](attachments/Pasted%20image%2020251127225011.png)

and then reboot the server.

AND OUR DOMAIN CONTROLLER IS DONE!!!