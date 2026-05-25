---
title: Installation and setup
---

Since OpenHellion is still in early development, you cannot simply download the game and play it as is. You therefore have to compile it from source. This page will explain how to do so.

This guide is written on Windows. Compiling on Linux does not because of Wwise. This might be fixed in the future by changing audio middleware.

## 1. Download source
Install [Git](https://git-scm.com/) or [GitHub Desktop](https://desktop.github.com/download/) to have a reliable way to download the source. This isn't neccecary, but highly recommended to do.

In your Git application, download the source from https://github.com/OpenHellion/Client into a folder you choose.

Simplest is to use execute following command in the folder you with to install the client.

```sh
git clone https://github.com/OpenHellion/Client
```

## 2. Setup Unity and Wwise
Download and install [Unity Hub](https://unity.com/) and [Wwise](https://www.audiokinetic.com/en/wwise/overview/) from their official websites.

Make sure you always download the version described on the [Client git repository](https://github.com/OpenHellion/Client).

To use Wwise, you need to apply for a free community licence. This is done quite easily on [their website](https://www.audiokinetic.com/en/wwise/overview/).

After this is done, open the client through the Wwise launcher. Do not use Unity Hub to open first time as it does not download the correct files required for audio.

After the Unity project is loaded through Wwise, enter the Wwise project and compile soundpacks. Afterwards you should have a fully functioning client.

## 3. Setting up servers
Hellion runs using two types of server: the [main server](clientserver-overview) and the [game server](server-overview). Both of these need to be running to enter the game.

### Main server
Download [Postgresql](https://www.postgresql.org/) and [Nakama](https://heroiclabs.com/nakama/) from their websites. Install Postgresql using its installer.

Download the main server from https://github.com/OpenHellion/Nakama using Git and extract the contents of the downloaded nakama binares into the folder of the Nakama server.

### Game server (works on linux)
Download the [latest version of dotnet 8](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) and install it.

Download the game server from https://github.com/OpenHellion/Server/ using Git.

Run the server using `dotnet run` in the server folder. Dependencies should be installed by itself, which will cause the first compile to be slow.

## 4. Troubleshooting
If these steps were followed correctly, OpenHellion should compile fine.

Common issues will be posted here.

Please take contact on the Discord if you have issues: https://discord.gg/9nGWgQ8Uyf
