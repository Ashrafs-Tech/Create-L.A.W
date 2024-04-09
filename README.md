# Creating the Central Log Repository and the SIEM

![image](https://github.com/Ashrafs-Tech/Create-L.A.W/assets/166546026/3148b4f1-1e86-4483-82b7-d1a4c048c90d)

## Intro - Create Log Analytics Workspace

Now I will focus on creating a central log repository. In Microsoft Azure, it is called the Log Analtyics Workspace. This of it like a database combined with an excel spreadsheet that has a lot of records of events that took place in the environment.

To begin, I will put in a watchlist which is a long list of network blocks. They contain information such as latitude, longitude, city name, country name, and etc.  This will be used to plot spots on the map that I will use later on in the lab to visualize where the attacks are coming from. 

In order to do this:
- I downloaded the watchlist
- Went to the Azure portal and searched "Log Analytics Workspace"
- Clicked Create
- I put it in the same resource group as the virtual machines "RG-Cyber-Lab"
- Named it LAW-Cyber-Lab-Ver1
- Placed it in the same reigon

![image](https://github.com/Ashrafs-Tech/Create-L.A.W/assets/166546026/e1e28f78-52a7-45c9-ba83-89709dc7733e)
![image](https://github.com/Ashrafs-Tech/Create-L.A.W/assets/166546026/388d158b-5935-462a-9b93-b38a3b94f164)

## Create the SIEM and its connection.

Now I will focus on creating the SIEM which stands for Security Information and Event Management.

The SIEM I will be using is Microsoft Sentinel and I will connect it to the Log Analytics Workspace.

To do this:
- I went to the Azure portal
- Searched for Microsoft Sentinel
- Clicked Create
- Add the Log Analytics Workspace I just made

This has connected the central repository and Microsoft Sentinel.

## Now I will have the watchlist injested into Sentinel

- Go to Sentinel
- Scrolldown to "Watchlist" and create a new one.
- I gave the name of the watchlist and alias "geoip"
- I uploaded the file I downloaded earlier

![image](https://github.com/Ashrafs-Tech/Create-L.A.W/assets/166546026/c75d272d-bea0-4b20-9a9d-ec20ebe73c97)
![image](https://github.com/Ashrafs-Tech/Create-L.A.W/assets/166546026/a78120b0-6ccd-46d3-b85a-4bedc30996aa)

- A file preview will appear on the right.
- I will select "network" for the search key
  * The "network" is what will be used to match the attackers IP address to different blocks

![image](https://github.com/Ashrafs-Tech/Create-L.A.W/assets/166546026/2390645a-5dc6-4b36-9dd4-5fa658c35e0f)

- The screen will look like this if done properly:

![image](https://github.com/Ashrafs-Tech/Create-L.A.W/assets/166546026/428e1b69-79ad-484b-a70c-7bf2e87a1e6e)

- When a watchlist has been ingested into Sentinel, Sentinel will store it in the Log Analytics Workspace.
- Go to Log Analytics Workspace.
- Scrolldown to Logs
- Using KQL, I am able to run quieres and examine the records stored

![image](https://github.com/Ashrafs-Tech/Create-L.A.W/assets/166546026/b9dc057b-a9dd-447f-9f32-1c792b399a5b)


## Step 3 is done.
- The Central Log Repository has been created
- Sentinel has been created
- Both of them are linked
- Data has been uploaded into Sentinel which stored it in the Log Analytics Workspace

![image](https://github.com/Ashrafs-Tech/Create-L.A.W/assets/166546026/7bcdedf3-6ba4-4404-ba47-cfd9d532ba0a)








