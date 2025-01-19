# Windows Domain Controller setup with Active Directory

## Objective

Setting up a Windows Active Directory (AD) is essential for managing and organizing a network of computers and users within a centralized system. Its primary objective is to provide a streamlined and secure method for controlling access to resources, such as files, printers, and applications, while ensuring that policies and permissions are consistently applied across the entire organization. By implementing Active Directory, IT administrators can simplify user authentication and authorization processes, enforce security policies, and reduce administrative overhead. AD also enables the delegation of administrative tasks, facilitating scalability and better management of network resources. Additionally, it enhances security by allowing granular control over who has access to sensitive information and applications, making it a critical component for any enterprise's IT infrastructure.

### Skills Learned

User and Group Management - Creating, managing, and organizing user accounts and groups within Active Directory for secure and efficient access control.
Group Policy Administration - Configuring and managing Group Policies to enforce security settings, software installations, and other network-wide configurations.
DNS and DHCP Integration - Understanding and managing the integration of Active Directory with DNS (Domain Name System) and DHCP (Dynamic Host Configuration Protocol) for seamless network functionality.
Active Directory Replication - Managing and troubleshooting AD replication to ensure data consistency and availability across multiple domain controllers.
Security and Access Control - Implementing security best practices through role-based access controls, managing permissions, and auditing to ensure a secure network environment.


# Steps Taken

First, name the server to an appropriate name you wish to make since with your enviroment. Additionally, give the server a static IP address. You can also check to make sure the time settings are setup as well. 

![image](https://github.com/user-attachments/assets/52f0a6ad-2319-481f-abe4-e1447f65cee5)


Next, you want to navigate to the Manage tab at the top right and select "Add roles and features" 

![image](https://github.com/user-attachments/assets/3f67c824-129b-49b8-a1fa-25db197b7a50)


Click on the next button 

![image](https://github.com/user-attachments/assets/726d8f7c-6956-47f7-bb41-6d13f8619fd8)


Make sure the Role-based or feature-based installaion is selected and then click next. 

![image](https://github.com/user-attachments/assets/21fe0086-ba62-45cc-b00e-45c17313bfbe)

Make sure you have the "Select a server from the server pool" is selectd and your sever name is shown in the server pool. If it is, then click on next. 

![image](https://github.com/user-attachments/assets/6a81f64c-86e2-4897-b988-2096523c203e)


We are going to install Active Directory and DNS so make sure to select the two boxes that correlate with the roles. 

![image](https://github.com/user-attachments/assets/62bae36c-a906-4bc7-b321-cbf34fda6e6a)

Just click next on this page as everything is setup correctly

![image](https://github.com/user-attachments/assets/c77709fd-118d-474e-9396-c751bbe551fb)

Click next to contuine on this page as well 

![image](https://github.com/user-attachments/assets/9b341b00-6e09-40d3-b83a-f2b4803d852d)

Click next on the DNS server tab as well 

![image](https://github.com/user-attachments/assets/d98e06b3-da28-43ca-9312-1ff5adfe7ff8)

Review everything that you just selected to confirm if the information is correct. Since we know this is correct, lets hit install now. 

![image](https://github.com/user-attachments/assets/1867f048-8303-47b6-b219-55e529f4464e)

Once everythings gets installed, you should see the bar fully complete and the option to promote the server to a domain controller. Click on "Promote this server to a domain controller"

![image](https://github.com/user-attachments/assets/17b2451a-749c-4100-9a96-7e1403ca6b0d)

Next, click on "Add a new forest" and then for the root domain put your domain you wish to have here. For example, it could be yourdomain.com 

![image](https://github.com/user-attachments/assets/2b5f237b-fb82-45b2-a7dc-3fbbb0245754)

Make sure these boxes are set to Windows server 2016 as this is the higest level at this time. Then set a DSRM password. 

![image](https://github.com/user-attachments/assets/b6c14545-7f8a-4bc8-931d-f108b923343d)

Once you get to the DNS option, click on next and ignore the warning sign on the top 

![image](https://github.com/user-attachments/assets/aae47ee2-2949-4bbf-ae87-6f87d3b525ec)

Review the netbios name to make sure its the same name as you put in the beginning

![image](https://github.com/user-attachments/assets/6e16eeac-fc9c-45e2-93c6-1a032ecfa4a1)

Click next on this page 

![image](https://github.com/user-attachments/assets/9160db9e-bde3-4883-9675-11930be0615b)

Review everything that you just setup and if its all checks out, then click on next. 

![image](https://github.com/user-attachments/assets/257fca2f-c8fa-4685-a741-ee64cb939078)

Once you click on next, a prerequisite check will run. Once its done, you should see where it passed successfully. Once you see that, click on install. 

![image](https://github.com/user-attachments/assets/0d9f70d7-fba8-4733-b62c-a2c0e31313fd)

The installation process will take some time and the server will reboot. Just let the process run its course.

![image](https://github.com/user-attachments/assets/e638eb81-9235-4766-8ec5-ef42c81a7b7a)

Once the server reboots, sign back in and server manager will open automatically. Let that finish its boot process. Once everything is green, navigate to the tool's tab at the top right and select Active Directory Users and Computers to check to see AD. 

![image](https://github.com/user-attachments/assets/4504f4c8-5a0d-4dca-b7d9-d1a4c2277154)

Everything looks good on the AD side, now lets move over to DNS. 

![image](https://github.com/user-attachments/assets/016d0555-40ef-41ab-8496-a9640dcfb7ba)

Next, we need to create a reverse lookup zone on our local DNS server. 

![image](https://github.com/user-attachments/assets/07d37156-3354-44de-9b90-d57d74138737)

Right click the reverse lookup zone and select new zone. 

![image](https://github.com/user-attachments/assets/8c798bea-955a-47d5-8f26-3bb08e45283d)

Click next 

![image](https://github.com/user-attachments/assets/9fad3c5d-1a29-4404-a058-34cc495a1206)

Make sure primary zone is selected and then click next. 

![image](https://github.com/user-attachments/assets/7685c5c6-2c58-428d-a4ca-3e4597889b34)

Make sure the second option is selected and then click next 

![image](https://github.com/user-attachments/assets/23edf87d-ea6a-4082-a187-34614a4ba6e6)

Make sure IPv4 lookup zone is selected then click on next 

![image](https://github.com/user-attachments/assets/22fbb126-b76e-496f-b50c-1297d91d4440)

Next, type in the first 3 octets of the IP address of the server then click on next 

![image](https://github.com/user-attachments/assets/8f80130b-8970-471c-a29c-55ec14801d26)

Make sure only Dynamic updates are enabled and then click on next 

![image](https://github.com/user-attachments/assets/b76730e5-01b2-4113-b636-fc734a755ce9)

Make sure everything looks right. If so, then click on finish 

![image](https://github.com/user-attachments/assets/bb8a6714-9aae-49bc-8f3c-45828a555a59)

Now the reverse lookup zone was created. Now we need to create a pointer for it. So just right click inside of the reverse lookup zone and click on New pointer 

![image](https://github.com/user-attachments/assets/fd20ebdc-1ebf-49c1-9d48-6f81043c4f54)

Click on Browse 

![image](https://github.com/user-attachments/assets/c0aa39d8-cc5e-4856-81be-74a25f4d79d4)

Double click on your server name 

![image](https://github.com/user-attachments/assets/458926c8-dd2d-4cec-a84e-3d6a991ace2f)

Double click on forward lookup zone 

![image](https://github.com/user-attachments/assets/143cf57e-bfa2-4be6-a3f1-db4a542fe234)

Select your domain name that you created 

![image](https://github.com/user-attachments/assets/696b7be4-0fe9-45e2-8102-22a211a440b8)


