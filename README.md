


<h1>Network File Shares and Permissions </h1>
This tutorial outlines the implementation of file shares over a network, and their ability to allow and modify file permissions for users.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
  

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)


<h2>Deployment and Configuration Steps</h2>

This lab is another continuation of the Active Directory Lab, and should be done only if you have completed that one. In this lab, we will explore file permissions and see what happens with different users and file share permissions. We can alter file permissions to allow different users different permissions. 

<img width="381" alt="File Sharing1" src="https://github.com/CGLuissi/Network-File-Shares-And-Permissions/assets/143234913/0d76c15e-1709-4dcc-b415-e6854e185ac7">

<img width="559" alt="File Sharing2" src="https://github.com/CGLuissi/Network-File-Shares-And-Permissions/assets/143234913/48f872d1-0f5c-4f3d-b7fb-5542f92d2538">




1.) Connect to DC-1 as an admin, then connect to Client-1 as a regular user from your created domain users. In DC-1, open up active directory users and computers and go to your created "_EMPLOYEES" OU. Go to the C:\ drive and create 4 folders. Make the folders "read-access" ,"write-access", "no-access" , and "accounting". Go to each folder, right-click and set these permsissions for each group:


<img width="412" alt="File sharing 3" src="https://github.com/CGLuissi/Network-File-Shares-And-Permissions/assets/143234913/282cda65-fea4-466f-b435-f72c6fe96066">


Read-access: Sharing ->click share ->type "domain users" ->add ->make sure read permissions are enabled -> share
Write-access: Sharing -> then "domain users" -> then "read/write" -> click on write-access then copy link
No-access: Sharing, then "domain admins" then read/write.

Skip the accounting folder for now. 

<img width="587" alt="File sharing 4" src="https://github.com/CGLuissi/Network-File-Shares-And-Permissions/assets/143234913/10a81a19-6346-4402-97a6-dc8f139da9d3">


2.) We can now attempt to access these file shares as a non-admin user to see what has changed. On Client-1, open command prompt and file explorer. In file explorer, type in "\\dc-1" in the quick access bar. Look at the file folders and see what you can access. Attempt to create new folders, or files in each folder. See what you are able to do in each one. In the "read-access" folder, create a text document called "you can only read me". Type whatever you want in this file. In DC-1, attempt to modify the text file; you can see that you can only have read access.  




