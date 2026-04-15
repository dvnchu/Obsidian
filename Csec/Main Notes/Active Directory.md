[[os]]

**Windows domain** is a group of users and computers under the administration of a given business. its main idea is to centralize the administration of common components of a windows computer network in a single repository called **Active Directory**.

The server that runs the AD is knows as a **Domain Controller**

![[Pasted image 20260127193356.png]]

The main advantages of a domain are:
- Centralized identity management: From AD you can configure all users
- Managing security policies: also manageable directly from AD.

## Active Directory Domain Service
This service acts as a catalog that holds the info of "objects" on your network 

among these objects some of the most important are:

**_Users_**
One of the most common object types in AD. they are known as security principals meaning they can be authenticated by the domain and can be assigned privileges over resources like files or printers.
its an object that can act upon resources in the network

there are two type of users:
- People
- Services: You  can define users to be used by services like MSSQL. They will only have privileges needed to run their specific service

**_Machines_**

For every computer that joins the domain, a machine object will be created. They are also "security principals" and are assigned an account as any user; the account has limited rights in the domain.

The machine accounts are local admins on the computer,  but they are generally not supposed to be accessed by anyone except the computer itself.(If you have the password you can log in, they are comprised of 120 random characters tho)

**_Security Groups_**

Groups are made to assign access rights to files or other resources to entire groups instead of single users. easing manageability. they are also security principals.

Groups can have both users and machines as members; They can also include other groups.

|                    |                                                                                                                                                           |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Security Group** | **Description**                                                                                                                                           |
| Domain Admins      | Users of this group have administrative privileges over the entire domain. By default, they can administer any computer on the domain, including the DCs. |
| Server Operators   | Users in this group can administer Domain Controllers. They cannot change any administrative group memberships.                                           |
| Backup Operators   | Users in this group are allowed to access any file, ignoring their permissions. They are used to perform backups of data on computers.                    |
| Account Operators  | Users in this group can create or modify other accounts in the domain.                                                                                    |
| Domain Users       | Includes all existing user accounts in the domain.                                                                                                        |
| Domain Computers   | Includes all existing computers in the domain.                                                                                                            |
| Domain Controllers | Includes all existing DCs on the domain.                                                                                                                  |

## Security groups vs OU

**OUs** are container objects that allow you to classify users and machines. these are mainly used to define set of users with similar policing requirements. Users can be member of a single OU at a time.

- OUs are handy for applying policies to users and computers, depending on ther role in the enterprise.
- Security Groups are used to grant permissions over resources.

## Computers in AD
By default all machines that join a domain (except for the DC) will be put in "Computers".

You'd probably want to separate them into categories according to their uses.

most common divisions are:

- Workstation
- Servers
- Domain Controllers

## Group Policies
Windows manages policies for OUs via Group Policy Objects(GPO).

You configure them via Group Policy Management.

Something to have in mind is that any GPO will apply to the linked OU and and any sub-OUs under it.

## Authentication methods
When using domains, all credentials are stored in the Domain Controllers. Whenever a user tries to authenticate to a service using domain credentials, the service will need to ask the Domain Controller to verify if they are correct. Two protocols can be used for network auth.

- Kerberos Used by any recent version of Windows . this is the default protocol in any recent domain.
- NetNTLM: Legay authentication protocol kept for compatibility
### Kerberos Auth
Users who log into a service using Kerberos will be assigned tickets. Users with tickets can present them to a service to demonstrate they have already authenticated into the network before and are therefore enabled to use it

The following process happens.

1. The user send username and timestamp encrypted using a key derived from their password to the **Key Distribution Center (KDC)**
   KDC will create and send back a **Ticket Granting Ticket (TGT)**, which will allow the user to request additional tickets to access specific services. it sounds weird but it allows user to request tickets wo passing their credentials every time they want to connect to a service. Along a **Session Key**  is given to the user they will need to generate following requests.

   GT is encrypted using krbtgt account's password hash, user cant access its contents. It is essential to know that the encrypted TGT includes a copy of the Session Key as part of its contents, and the KDC has no need to store the Session Key as it can recover a copy by decrypting the TGT if needed.


![[Pasted image 20260128202719.png]]

2. When a user want to connect to a service on the network like a share, website or database, they will use their TGT to ask the KDC for a **Ticket Granting Service (TGS)**. TGS are tickets that allow connection only to the specific service they were created for. To request a TGS, the user will send their username and a timestamp encrypted using the session key, along with the TGT and a **Service Principal Name (SPN)**, which indicates the service and server name we intend to access
   As a result the KDC will send us a TGS along with a Service Session Key, which we will need to authenticate to the service we want to access. The TGS is encrypted using a key derived from the **Service Owner Hash**. The Service Owner is the user or machine account that the service runs under. The THS contains a copy of the service session Key on its encrypted contents so that the service owner can access it by decrypting the TGS.

   ![[Pasted image 20260128203735.png]]
   3. The TGS can then be sent to the desired service to auth and establish a connection. The service will use its configured accounts password has to decrypt the TGS and validate the Service Session Key.
![[Pasted image 20260128203917.png]]
### NETLM Auth
It works using a challenge-response mechanism.
![[Pasted image 20260128204048.png]]   
1.  The client sends an authentication request to the server they want to access.
2. The server generates a random number and sends it as a challenge to the client.
3.  The client combines their NTLM password hash with the challenge (and other known data) to generate a response to the challenge and sends it back to the server for verification.
4. The server forwards the challenge and the response to the Domain Controller for verification.
5. The domain controller uses the challenge to recalculate the response and compares it to the original response sent by the client. If they both match, the client is authenticated; otherwise, access is denied. The authentication result is sent back to the server.
6. The server forwards the authentication result to the client
Note that the user's password (or hash) is never transmitted through the network for security.

## Trees, Forests and Trusts

Sometimes when companies grows you might need more than one domain

### Trees
Active Directory supports integrating multiple domains so that you can partition your network into units that can be managed independently. If you have two domains that share the same namespace (`thm.local` in our example), those domains can be joined into a **Tree**.

If our `thm.local` domain was split into two subdomains for UK and US branches, you could build a tree with a root domain of `thm.local` and two subdomains called `uk.thm.local` and `us.thm.local`, each with its AD, computers and users
![[Pasted image 20260130200647.png]]

### Forests
The union of trees with differents namespaces into the same network
![[Pasted image 20260130200855.png]]


### Trust relationship
having a trust relationship between domains allows you to authorise a user from domain `THM UK` to access resources from domain `MHT EU`.
![[Pasted image 20260130200851.png]]
These can be one way or two way.