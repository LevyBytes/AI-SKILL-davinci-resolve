# Blackmagic Cloud Project Server

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

## Overview

Covers: Blackmagic Cloud; Blackmagic Cloud Project Server.

## Blackmagic Cloud

### Blackmagic Cloud

## Blackmagic Cloud Project Server

### Blackmagic Cloud Project Server

This chapter walks through configuring and operating the Blackmagic Cloud Project Server, which lets you share projects and work jointly with fellow DaVinci Resolve users anywhere on the planet.

### Cloud Project Libraries

Blackmagic’s Project Library servers, reachable over the internet, are where cloud project libraries live, so that DaVinci Resolve users can join and work together on identical projects no matter where in the world they happen to be.

### Connecting to a Blackmagic Cloud Project Library in DaVinci Resolve

For a small monthly charge, users can reach the project library cloud servers that Blackmagic operates at numerous sites worldwide. To sign into to the Blackmagic cloud: 1 Register for a Blackmagic ID with your email address over at http://cloud.blackmagicdesign.com 2 Within the Project Manager window, pick Cloud among the Project Library icons at the top left. 3 From the Sign In dialog, select the Blackmagic Cloud option and enter your Blackmagic ID together with your password. 4 Should you belong to an Organization Profile, you're free to log into either that account or your own personal one.

### The Blackmagic Cloud login dialog box

Signing out of the Blackmagic cloud: 1 Inside the Project Manager window, choose Cloud from the Project Library icons at the upper left, then click your account icon over at the top right and pick Log Out. 2 Use the menu path File > Blackmagic Cloud Account > Log Out. 3 Alternatively, go Preferences > Internet Accounts Blackmagic Cloud > Log Out.

### Accessing the Cloud Project Library in DaVinci Resolve

After you've connected, you reach cloud project libraries by clicking the Show/Hide Project Libraries icon at the top left of the Project Manager. That brings out a sidebar listing every project library you're connected to. Click the Cloud icon to bring up the cloud project library. There are two parts to it: “My Cloud,” where every project library you've made is handled, and “Shared with me,” which lists project libraries that others built and then granted you shared access to.

Should your project library not appear right away, click the circular arrow refresh icon at the upper right of the Project Manager to force the servers to refresh.

### The Blackmagic cloud library

### Blackmagic Cloud Project Server on the Web

The best place to manage cloud project libraries is inside DaVinci Resolve, though a web interface exists too. Through it you can view which projects sit in each library, run searches and sorts, and set up fresh cloud project libraries.

### The Blackmagic Cloud Project Server web interface

On first launch, the Project Server displays every active project in whichever project library you used most recently. The left-hand pane lists all of your cloud project libraries, and you tack on new ones with the Add Project Library button down at the bottom. Pick a cloud project library and it reveals all its projects, which the matching controls along the right of the toolbar let you search, sort, and list. At the time of writing, the web interface only lets you view projects. Creating, deleting, copying, or otherwise handling any single project has to happen inside the DaVinci Resolve Project Manager instead Clicking the information icon over on the toolbar's right side opens the sharing settings for the libraries. From there you can add, enable, or disable the project library, or tack on a new presentation. Who currently has access to the project library shows up under the Sharing tab, and you bring in more users with the Share Project Library button underneath. Through the Backups tab you can make and restore backups of your project library onto the Blackmagic Cloud; for extra peace of mind you may switch on automatic daily backups.

### Optimization and Performance of a Cloud Project Library

Ahead of digging into how cloud project libraries get created and managed, it pays to talk about server lag and tuning. Every edit, clip metadata entry, visual effect, color correction, and audio engineering choice applied to your timeline lives in the project library, which is a database. As you work in DaVinci Resolve, that project library is being queried and updated nonstop. While the project library sits locally on, or on the same network as, your workstation, those updates land almost instantly. But once the project server is sitting halfway around the globe across the internet, the speed of light plus internet routing begin adding noticeable lag. Thankfully the DaVinci Resolve team has already handled most of the work needed to soften this. Over the course of several months they rewrote the project library's underlying code to tune it for internet performance, and most of the time the responsiveness feels no different from a local project library. Even so, these kinds of operations call for heavy, sustained project library activity, and a bit of lag will show up while:

- Changing cloud project libraries
- Loading a project from the cloud project library
- Backing up and restoring cloud project libraries

Bear in mind that, once a library is loaded, actually working away in DaVinci Resolve stays every bit as smooth and responsive as you're accustomed to with local libraries.

TIP: The biggest tuning lever available to the user for cloud library performance is choosing the server's physical home. You'll get top performance nearest the city where the team is based. Sometimes the team is spread across several cities and countries worldwide. When that's the case, put the server in the region of whoever leans on the project library most, and that person is the editor. Across the Edit and Cut pages, writes to the project library happen each time the user lets go of the mouse button, whereas on the Color page the project library only gets written when you pick a fresh clip. So to get the best performance, you want the server's location sitting as near to the editor as you can.

### Creating a New Cloud Project Library

Setting up a fresh cloud library means you add it yourself, by hand, through the Blackmagic Cloud website. Building a new cloud project library: 1 Inside the Project Manager, tap the Cloud icon to log into the Blackmagic cloud server. 2 Tap the Show/Hide Project Libraries icon at the top left of the Project Manager to bring out the sidebar. 3 Tap the “Go to Blackmagic Cloud” button down at the foot of the sidebar, which sends you to the Web Project Server. 4 A web browser launches and routes you automatically to the Blackmagic Cloud web interface. 5 Tap the “Add Project Library” button at the bottom of the sidebar within your web browser 6 Type a fresh name for your cloud project library, then choose the worldwide region where you'd like the server hosted. Picking a server nearest the project's editor works best, followed by the Version of Davinci Resolve you want the library to match. 7 Press the Add button. From here you can build or bring in new projects straight into your fresh cloud project library.

### Deleting or Renaming a Cloud Project Library

Once you're done with a given cloud project library and would like to remove it or alter its name, the Project Libraries interface is where you do so. To delete a cloud project library: 1 Log into the Blackmagic cloud server inside the Project Manager. 2 Click the Show/Hide Project Libraries icon at the top left of the Project Manager to bring out the sidebar. 3 In the Project Libraries sidebar, right-click whichever library you'd like removed and pick Delete off the drop-down menu. 4 On the confirmation dialog box that appears, click the Delete button. Removing a cloud project library can't be undone and is permanent. Be certain you've pulled everything you need from this library before you hit delete. After it's gone, it's gone for good. To rename a cloud project library: 1 Log into the Blackmagic cloud server inside the Project Manager. 2 Click the Show/Hide Project Libraries icon at the top left of the Project Manager to bring out the sidebar. 3 In the Project Libraries sidebar, right-click the library you'd like renamed, then type the fresh name into the dialog box. 4 Click the OK button. TIP: You're unable to remove or rename the project library that's currently connected (marked by an orange highlight surrounding it). To do either, first pick and connect to a different project library, and then carry out the steps above.

### Upgrading a Cloud Project Library

Every so often, fresh releases of DaVinci Resolve alter how projects get built, which means project libraries made by older DaVinci Resolve versions must be upgraded before you can reach the projects inside them. Happily, it's a straightforward routine, but you can only run it within DaVinci Resolve, not via the web interface. To upgrade a cloud project library: 1 Log into the Blackmagic cloud server inside the Project Manager. 2 Click the Show/Hide Project Libraries icon at the top left of the Project Manager to bring out the sidebar. 3 In the Project Libraries sidebar, right-click whichever library you'd like upgraded and pick Upgrade off the drop-down menu. 4 On the confirmation dialog box that appears, click the upgrade button.

### Sharing a Cloud Project Library

A cloud project library can be shared with other users across the globe who hold a Blackmagic ID. To share a cloud project library: 1 Log into the Blackmagic cloud server inside the Project Manager. 2 Click the Show/Hide Project Libraries icon at the top left of the Project Manager to bring out the sidebar. 3 On the cloud project library you'd like to share, click the Details icon (the circled letter “i”) to open up the details settings. 4 A members list (or, in the web interface, a sharing tab) shows up, with your user name and email leading the list beside a small crown icon, signifying that you own this project library. 5 Click the Share button down at the foot of the sidebar. 6 Type in the Blackmagic ID (email address) belonging to whoever you'd like to share this project library with. 7 Press the Share button. That user gains access to the shared library at once, and an email lets them know about their access as well. IMPORTANT: Anyone you share your project library with can alter and delete any of the projects inside that shared library, so choose carefully who you grant access to.

### The Members section of the Blackmagic cloud library

### Removing a User from a Shared Cloud Project Library

As the owner of a shared cloud project library, you have the power to take away the access of any other shared user. Dropping a shared user from such a library: 1 Log into the Blackmagic cloud server inside the Project Manager. 2 Click the Show/Hide Project Libraries icon at the top left of the Project Manager to bring out the sidebar. 3 On the cloud project library you'd like to share, click the Details icon (the circled letter “i”) to open up the details settings. 4 A members list (or, in the web interface, a sharing tab) appears, listing every user who can reach this project library. 5 Right-click whichever user you'd like to drop and pick Remove Member off the drop-down list.

### Backing up and Restoring a Cloud Project Library

You can carry out backup and restore of a cloud project library right within the Blackmagic cloud. To back up a cloud project library: 1 Log into the Blackmagic cloud server inside the Project Manager. 2 Click the Show/Hide Project Libraries icon at the top left of the Project Manager to bring out the sidebar. 3 On the cloud project library you'd like to back up, click the Details icon (the circled letter “i”) to open up the details settings. 4 Click the Back Up button. 5 After a while, a dialog box pops up confirming the backup reached the cloud safely. To roll a cloud project library back to an earlier version: 1 Log into the Blackmagic cloud server inside the Project Manager. 2 Click the Show/Hide Project Libraries icon at the top left of the Project Manager to bring out the sidebar. 3 On the cloud project library you'd like rolled back to an earlier version, click the Details icon (the circled letter “i”) to open up the details settings. 4 Click the Restore button. 5 Within the Backups list, browse to whichever version you want to restore. 6 Give the restored library a new name. 7 Click the Restore button.

### Blackmagic Cloud Support for Importing ATEM Projects

When you're running ATEM switchers and follow the workflow of producing several ISO feeds plus the matching DaVinci Resolve project, you can now sign into a Blackmagic Cloud project library, pick an existing DaVinci Resolve cloud project, and rely on the Camera Uploads mechanism to bring recorded media across to DaVinci Resolve in sync. Fellow DaVinci Resolve collaborators will see the switcher's edit decisions show up as a fresh timeline within that project.

- For the uploaded media from the switcher to appear, the DaVinci Resolve project has to be configured to synchronize camera originals.
- Should the ATEM resolution or frame rate not match the project settings, new timelines may adopt custom settings.

### Setting up a Cloud-Based Collaboration Workflow

With internet bandwidth climbing over the years, collaborating on a project entirely online has lately become feasible. Where you once had to share a single building wired to a fast LAN and Network Attached Storage (NAS), you can now work together live from anywhere on earth by leaning on the internet and cloud storage instead. What follows are the steps for building an entirely cloud-based workflow with the tools and settings inside DaVinci Resolve 18 or higher. This example workflow features Editor A, Colorist B, and Audio Engineer C, each in a different corner of the world, all wanting to collaborate on one project simultaneously. The aim is to cut down on how much media management is required and to avoid passing individual project files to and fro.

Set up the Blackmagic Cloud and a Cloud Library

- Users A, B, and C register for the Blackmagic cloud service.
- Users A, B, and C sign into the cloud through the Project Manger within their own DaVinci Resolve installations.
- User A builds a fresh cloud library and invites Users B and C to share it. Because User A is the editor,

they'll situate the cloud library's server closest to themselves.

### Set up the Cloud Storage

- Users A, B, and C register with a cloud storage provider (Dropbox, iCloud, OneDrive, Google Drive, etc.)
- Users A, B, and C set their cloud storage up so they can all reach the same cloud-based folder together. That folder belongs at the top level of the cloud storage. They settle on naming the folder Episode 12.
- Within their shared Episode 12 folder, Users A, B, and C build a file hierarchy system, for instance fresh subfolders for Audio, Proxies, and Graphics.
- Users A, B, and C mount the shared storage folder onto their own machines. Editor A drops a few logos and still photos into the Graphics folder. Audio Engineer C drops some music and sound effects into the Audio folder. Uploading and distributing this from the cloud takes a while, but in time every user holds the same media locally on their own computer.

### Create the Proxy Media

- Colorist B keeps the RAW camera masters on a hard drive wired to their system. Given that they alone require the RAW camera files for color grading, they'll generate low bandwidth proxies for the Editor and Audio Engineer to use. Those files are compact enough to upload and keep in their cloud storage folder.
- Colorist B generates proxy files from the RAW media using the Blackmagic Proxy Generator application.

To learn more about working with the Blackmagic Proxy Generator, refer to Chapter 8, “Improving Performance, Proxies, and the Render Cache.”

- Colorist B sends the proxy files up to the Proxies folder within their cloud storage.

### Setup the DaVinci Resolve Project and Settings

- Colorist B builds the new project inside the cloud library and configures its resolution, frame rate, and so on.
- Colorist B switches on the File > Multiple User Collaboration setting.
- Users A, B, and C open the project and point their individual file paths at their cloud storage folder

“Episode 12” within the Path Mapping section of the Project Settings. To read more about Path Mapping, refer to Chapter 6, “Project Settings.”

- Colorist B brings the RAW media in from their local hard drive into their Media Pool, then links it to the proxies he sent up to the Episode12/Proxies folder. From this point, Editor A and Audio Engineer C have the proxy media available, while Colorist B can flip between RAW media and Proxies whenever needed. If it proves necessary, Colorist B may also choose to upload the RAW media into the shared folder where space and time permit. While the rest of the users wait on that media to finish uploading, if they've got the “Prefer Camera Originals” setting ticked under Playback

> Proxy Handling menu, they can keep editing with the proxies, and as the RAW media files arrive, those will swap in for the proxy files automatically as they come.

- Editor A brings their still photos into the Media Pool out of the Episode 12/Graphics folder. They become available straight away to Users B and C with no relinking.
- Audio Engineer C brings their music tracks into the Media Pool out of the Episode 12/Audio folder. They become available straight away to Users A and B with no relinking.
- As the users go on adding more media into the shared folder and pulling it into the Media Pool, there can be a delay while the media uploads to the cloud storage and then downloads to the other users. Throughout that window the clip shows as media offline, yet it relinks automatically the moment the file completes its download onto the local computer.

Continue working in DaVinci Resolve’s Collaborative Workflow From this point, the editor edits, the colorist grades, and the audio engineer takes care of the sound design, every one of them relying on the existing collaborative workflow tools in DaVinci Resolve. For more information on using these tools, see Chapter 197, “Collaborative Workflow.”
