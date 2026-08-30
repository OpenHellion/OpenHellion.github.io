---
title: Installation and setup
---

Since OpenHellion is still in early development, you cannot simply download the game and play it as is. You therefore have to compile it from source. This page will explain how to do so.

This guide is written for Windows. Compiling on Linux does not work because of Wwise. [This might be fixed in the future.](https://github.com/orgs/OpenHellion/projects/4/views/6)

## Minimum requirements
* 30 GB of disk space
* 6 GB of RAM
* 16 GB of RAM to build

Processor and graphics card shouldn't matter much, but it has to at least run Unity; Settings can be modified to increase performance.

## 1. Download source
Install [Git](https://git-scm.com/) or [GitHub Desktop](https://desktop.github.com/download/) to have a reliable way to download the source. This isn't neccecary, but highly recommended to do.

Download the source from [https://github.com/OpenHellion/Client](https://github.com/OpenHellion/Client) into a folder you choose.

Simplest is to use execute following command in the folder you with to install the client (needs [Git](https://git-scm.com/)).

```sh
git clone https://github.com/OpenHellion/Client
```

## 2. Setup Unity and Wwise
Download and install [Unity Hub](https://unity.com/) and the [Audiokinetic launcher](https://www.audiokinetic.com/en/wwise/overview/) from their official websites. Download the Unity version described on the [Client git repository](https://github.com/OpenHellion/Client) using Unity Hub. Do not use Unity Hub to open the Client first time as it does not download the correct files required for audio.

Create an Audiokinetic account and apply for a modding licence on [their website](https://www.audiokinetic.com/en/profile/school/6808/). This is free and you should get your licence within two working days.

Log in on the Audiokinetic launcher, and open the Unity tab. Locate the `Client` install you downloaded on the last step, and after some time it will appear in the list. Then download the Wwise SDK version required by the project in the `Wwise` tab. Open the Wwise project to test if the Wwise is installed.

![alt text](res/wwise-example.png)

After obtaining a lisence open the Audiokinetic launcher again and navigate to the `Projects` tab. After refreshing for some time, the project should pop up and you can set a licence.

![alt text](res/wwise-licence.png)

Open the project in Wwise, set your platform in the dropdown in the upper-left corner. Afterwards, navigate to SoundBanks in the Project Explorer window, right click `SoundBanks`, and click on `Generate Soundbanks` for current platform.

![alt text](res/generate-soundbanks.png)

Finally, open the Unity editor using the Audiokinetic launcher. This will take some time depending on the speed of your computer because this step imports all files and builds the project, something that will increase the size of you project dramatically.

## 3. Setting up servers (works on linux)
Hellion runs using two types of server: the [main server](clientserver-overview) and the [game server](server-overview). Both of these need to be running to enter the game.

### Main server
Download [Postgresql](https://www.postgresql.org/) and [Nakama](https://heroiclabs.com/nakama/) from their websites. Install Postgresql using its installer.

Download the main server from [https://github.com/OpenHellion/Nakama](https://github.com/OpenHellion/Nakama) using Git and extract the contents of the downloaded nakama binares into the folder of the Nakama server.

### Game server
Download the [latest version of dotnet 8](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) and install it.

Download the game server from [https://github.com/OpenHellion/Server/](https://github.com/OpenHellion/Server/) using Git.

Run the server using `dotnet run` in the server folder. Dependencies should be installed by itself, which will cause the first compile to be slow.

## 4. Troubleshooting
If these steps were followed correctly, OpenHellion should compile fine.

### Wwise is placed at a path that has a space in it
Simply reinstall Wwise in a directory that has no spaces in its path.

Please take contact on the Discord if you have issues: [https://discord.gg/9nGWgQ8Uyf](https://discord.gg/9nGWgQ8Uyf)
