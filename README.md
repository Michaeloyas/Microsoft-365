# Office (Microsoft) 365 Part 1: Active Users, Active Groups, OneDrive, Exchange, SharePoint, and Teams

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*wsy0Bg-IsK0GfvCfvtR6CQ.jpeg" width="600" alt="screenshot of interface"/>
<br />

---
## Introduction
Microsoft 365 (MS 365) is a comprehensive suite of productivity software, collaboration tools, and cloud-based services. In this guide, we'll explore some core features that IT Support Specialists frequently interact with.

## Prerequisite
To follow along and practice, check out the **92-day free trial** by signing up for the MS 365 Dev Center Developer Program. This will grant you access to basic features.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*I9JoDkqaCf7ilc3o9kwHZQ.png" width="600" alt="screenshot of interface"/>
<br />

---
## What you will learn:
* Creating and Managing Users
* Creating and Tracing Messages
* Creating Shared Mailboxes
* Creating Distribution Lists
* Creating Microsoft 365 Groups
* SharePoint basics
* Restoring Deleted Files on OneDrive

---
## Creating Users
Users and groups created in the **Microsoft 365 Admin Center** are replicated throughout the entire suite—Azure Active Directory, SharePoint, Exchange, and Teams.

### Create Users
1. Once you have set up an account, navigate to the **MS 365 Admin Center**.
2. Select **Active Users** > **Add a user**.
3. Fill in the details:
    * **Name**: Mat Fisher
    * **Username**: mfisher
    * **Domain**: <The domain you created while setting up your account>
4. Check the **Automatically generate a password** box.
5. Check **Require the user to change the password when they first sign in**.
6. **Licenses**: Check the **Microsoft 365 E5 Developer** box to allow the user to access apps.
7. **Role**: Check the option for **Admin center access** > **Next** > **Finish**.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*Vm8ik1TdD1gq3NHtsqc7hQ.png" width="600" alt="screenshot of interface"/>
<br />

Repeat the same steps to create two more users and assign the "**user (No access to admin center)**" role to them. Each user created can sign in to the MS 365 environment and access resources based on the roles assigned.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*heHNuZUYRiDm6fntIBuU-w.jpeg" width="600" alt="screenshot of interface"/>
<br />

### Manage Users
1. Click on a user to reveal the options for managing that specific user.
2. **Reset Password**: Allows you to reset a user’s password.
3. **Block sign-in**: Useful for denying access to disengaged employees.
4. **Delete user**: To delete a user. The deleted user can still be restored within thirty days from the "**Deleted users**" option.
5. **Devices**: All the user’s devices enrolled in Microsoft Intune will show here.
6. **Mail**: You can set up automatic replies and other functions.
7. **OneDrive**: The user’s files are located here. It allows you to generate and share links to files, as well as manage storage.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*BOpclcgvIlvHnDsnv6QLTw.jpeg" width="600" alt="screenshot of interface"/>
<br />

---
## Creating and Tracing Messages
We will create and send an email from one user to another and attempt to trace the mail to ascertain its status. This is useful in cases where a mail is reported missing or the intended recipient didn’t get the email.

### To Create a Mail:
1. At the top-left corner, click on the **menu button** to display apps and select **Outlook**.
2. Compose a new email:
    * **To**: mfisher@technocontent.onmicrosoft.com
    * **Subject**: Project Update
    * **Body**: <Craft whatever in the body>

Let’s assume that the email was sent, but Mat Fisher didn’t receive it. How do we trace it? Let’s see the steps below:

### Tracing Missing Mail
1. On the left-side menu of the **Exchange admin center**, under "**Mail Flow**," select "**Message trace**."
2. Select "**custom queries**" > click "**Start a trace**" > Paste the sender and recipient’s mail address.
3. Select the time range to search from, e.g., the last two days.
4. **Report type**: summary report > **Search**.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*rVINoiyXpI-E0Ydimi_Glg.png" width="600" alt="screenshot of interface"/>
<br />

The result of the search will display whether the email was received, processed, delivered, or not delivered.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*njzjsvdTX9zbfdFqEH9BKw.png" width="600" alt="screenshot of interface"/>
<br />

---
## Creating Shared Mailboxes
Shared Mailboxes enable individual members of a group to send and receive emails using a single mailbox, bypassing their user mailboxes. For instance, we can create a shared mailbox for the IT Support department and add each member to it. This allows the team to attend to customers regardless of who is on the shift.

### Steps for Creating a Shared Mailbox
1. On the left side of the **Exchange admin center**, > select "**Mailboxes**."
2. Click on "**+Add a shared mailbox**."
3. Fill in the details:
    * **Display Name**: IT Support
    * **Email address**: itsupport
    * **Domain**: technocontent.onmicrosoft.com <use yours>
4. Click on "**Create**."
   
<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*jJgxwwA-UdRrXItqULb9Og.png" width="600" alt="screenshot of interface"/>
<br />

### Steps for adding users and access delegation
1. Once the shared mailbox is created, click **mailboxes**.
2. Click on the mailbox you just created, and a new window should pop up that allows you to manage the mailbox.
3. Click on "**Delegation**."
4. **Send as**: Edit this part by adding users allowed to send an email from the mailbox.
5. **Read and Manage**: This permission gives the users full access to use the mailbox as the “owner.”

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*9CV-scrtKI5ByPnrj868-g.png" width="600" alt="screenshot of interface"/>
<br />

### Steps for Adding a New Folder/Mailboxes
The delegates in a shared mailbox will not automatically see emails sent to the mailbox. They have to manually add the mailbox folder (which contains the inbox, draft, sent items, and Junk …).
1. On the left-hand menu on the **Exchange admin center**, right-click "**Folders**."
2. Click on "**Add shared folder or mailbox**" > Supply the email address for the shared mailbox > Click "**Add**."
3. The shared mailbox name will pop in > click to expand it, and you will see the inbox and other options.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*0u4Fv-62otlL0pMOhu8YZA.png" width="600" alt="screenshot of interface"/>
<br />

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*c6Zpe6bGFXrWwlUcEyxPiA.png" width="600" alt="screenshot of interface"/>
<br />

---
## Creating Distribution List
As the name implies, a distribution list allows you to send a single email to individual users or groups that are part of that distribution.

### Steps for Creating a Distribution List
1. Click on **Groups** > **Distribution list** > **Add a group**.
2. Select **Distribution** > **Next**.
3. Fill in the details:
    * **Name**: IT Group
    * **Description**: Medium for disseminating general info to the IT team
    * **Owner**: <choose who owns the group>
    * **Members**: <Assign members to the group>
    * **Group email**: supportgroup@<choose the domain you created>
    * **Joining the group**: closed //Only the owner can add members
    * **Leaving the group**: closed //Only the group owner can remove members
4. **Finish**.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*5z0WHTjy-5boxbVCVRmZnA.png" width="600" alt="screenshot of interface"/>
<br />

---
## Creating Microsoft 365 Group
A Microsoft 365 group helps people collaborate. It includes a central email address for contacting everyone in the group and a SharePoint site for publishing information.

### Steps for Creating a Microsoft 365 Group
1. On the left side of the **MS 365 admin center**, > select "**Active Teams and Groups**."
2. Click on "**+Add a Microsoft 365 Group**."
3. Fill in the details:
    * **Display Name**: IT Department Group
    * **Email address**: itdptgroup
    * **Description**: Group dedicated to the general IT Department
    * **Owner**: <choose who owns the group>
    * **Members**: <Assign members to the group>
    * **Group email**: itdptgroup@<choose the domain you created>
4. **Finish**.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*fXm9tD5rx9-m-g6FdrzIUQ.jpeg" width="600" alt="screenshot of interface"/>
<br />

---
## SharePoint
SharePoint is a web-based collaborative platform that integrates natively with Microsoft 365. It allows you to build intranet sites and create pages, document libraries, and store and share files.

### Accessing SharePoint Sites
Every MS 365 group you create will show up under active sites. Use the steps below to view Sites:
1. On the left side of the **MS 365 Admin Center**, scroll down and click on **SharePoint**.
2. Click on **sites** > **Active Sites**.
3. Click on the **IT Department Group** we created from the previous step > **view site**.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*w3LETSQUScWwGj2eYTFLkA.jpeg" width="600" alt="screenshot of interface"/>
<br />

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*HcF6DhM-hlK5RJbbyrx0Yw.jpeg" width="600" alt="screenshot of interface"/>
<br />


More on SharePoint sites will be covered in the second part of the Microsoft 365 tutorial.

---
## Restoring Deleted Files on OneDrive
If a user deleted an important document and for some reason also emptied the recycle bin—maybe to free up space in their OneDrive—how can we go about restoring that file to the user? Follow the steps below to restore deleted files.

### Viewing a User’s Files
1. From the **MS 365 admin center**, click **active users** > select the user whose files you want to view.
2. Click on **OneDrive** > click on "**Create a link to file**."
3. Click on the link to take you to the user’s file on OneDrive.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*uidO0JIovqmaLSobCJr4dA.jpeg" width="600" alt="screenshot of interface"/>
<br />


On OneDrive, click on "**My files**" to see the user's files.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*uidO0JIovqmaLSobCJr4dA.jpeg" width="600" alt="screenshot of interface"/>
<br />

Let’s delete “Important\_internal\_memo” and also empty the recycle bin.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*cgy5Tjir7zxrEfw5zPV9Gw.jpeg" width="600" alt="screenshot of interface"/>
<br />

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*d3BGaYmI_YM1nJ0S-ONCyw.jpeg" width="600" alt="screenshot of interface"/>
<br />

### Restore Deleted Files
1. Click on the **Recycle bin** > scroll down and locate "**Second stage recycle bin**."
2. From the second stage recycle bin, click on the file you want to restore > Click on the "**restore**" option.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*y95bPbpcjO24gbfote2VaQ.jpeg" width="600" alt="screenshot of interface"/>
<br />

That restores the file to its original folder.

<br />
<img src="https://cdn-images-1.medium.com/max/1200/1*j8FGHlgOnFsqa2MugrS3Qw.jpeg" width="600" alt="screenshot of interface"/>
<br />

---
## Conclusion
In this first part, we created users and groups, shared mailboxes, traced missing messages, and restored deleted files. In the second part, we will go in-depth into Teams and SharePoint. See you there!
