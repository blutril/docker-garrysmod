# What is Garry's Mod?

Garry's Mod is a physics sandbox. There aren't any predefined aims or goals. We give you the tools and leave you to play.

# Quick Start

## Basic

```
docker run -it \
    -p 27015:27015/tcp \
    -p 27015:27015/udp \
    hackebein/garrysmod
```

## Enable API

```
docker run -it \
    -p 27015:27015/tcp \
    -p 27015:27015/udp \
    -e "AUTHKEY=..." \
    hackebein/garrysmod
```
Get your [AUTHKEY](http://steamcommunity.com/dev/apikey)

## Public
If you have activated the API, this step happens automatically.

```
docker run -it \
    -p 27015:27015/tcp \
    -p 27015:27015/udp \
    -e "GLST=..." \
    hackebein/garrysmod
```

Get your [GLST](http://steamcommunity.com/dev/managegameservers) (`APPID: 4000`)

## Workshop Collection
Workshop access requires the API.

```
docker run -it \
    -p 27015:27015/tcp \
    -p 27015:27015/udp \
    -e "AUTHKEY=..." \
    -e "WORKSHOPCOLLECTIONID=..." \
    hackebein/garrysmod
```

## Config

```
docker run -it \
    -p 27015:27015/tcp \
    -p 27015:27015/udp \
    -v ./server.cfg:/opt/steam/garrysmod/cfg/server.cfg \
    hackebein/garrysmod
```

## Example for TTT
```
docker run -it \
    -p 27015:27015/tcp \
    -p 27015:27015/udp \
    -e "AUTHKEY=..." \
    -e "GAMEMODE=terrortown" \
    -e "MAP=ttt_minecraft_b5" \
    -e "WORKSHOP=843519054" \
    -e "WORKSHOPDL=843519054" \
    -v ./server.cfg:/opt/steam/garrysmod/cfg/server.cfg \
    hackebein/garrysmod
```

Go to [Workshopp Collection](https://steamcommunity.com/sharedfiles/filedetails/?id=843519054)

## Additional Environment

TICKRATE: Tickrate of server, **Attention:** Change not recommended
(`Default: 66`)

GAMEMODE:
(`Default: sandbox`)

MAP: Map on Server start
(`Default: gm_flatgrass`)

CONFIG: Server config, **Attention:** Change not recommended
(`Default: server.cfg`)

MAXPLAYERS: Max players
(`Default: 16`)

CUSTOMPARAMETERS: additional parameters
(`Default: `)

WORKSHOP: downloads workshop collection for server
(`Default: `)

WORKSHOPDL: downloads workshop collection for client before joining
(`Default: `)

## More Options

You can found more configuration options on the parent image page [hackebein/srcds](https://hub.docker.com/r/hackebein/srcds)
