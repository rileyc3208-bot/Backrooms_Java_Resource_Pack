# BackroomsPort Java Resource Pack

Public distribution repository for the **optional Java Edition client resource pack** used by BackroomsPort.

BackroomsPort itself is developed in a separate private repository. This repository exists so a Java client can fetch a resource-pack ZIP over normal public HTTPS without exposing the plugin source or development history.

## Current status

**Bootstrap / not currently required in production.**

The live project is Bedrock/Geyser-first and currently has no Java players. The canonical production client pack is therefore the Bedrock resource pack shipped with BackroomsPort.

This Java pack repository is being kept ready in case Java-client support is enabled later. Do not assume that Bedrock pack assets can be copied here one-for-one: Java block models, item models, paths, and rendering rules are different and should be ported deliberately.

## Target

- Minecraft Java Edition: **26.1.x**
- Resource-pack format: **84**
- BackroomsPort namespace: `backroomsport`

## Repository layout

`pack.mcmeta` is the pack root. Future assets belong under standard Java resource-pack paths such as:

```text
assets/
  backroomsport/
    items/
    models/
    textures/
  minecraft/
    blockstates/
    models/
    textures/
```

The packaging workflow validates that `pack.mcmeta` is at the root of the distributable ZIP. That matters for Minecraft's server resource-pack downloader.

## Releasing

Push a version tag matching `v*` (for example `v0.2.19.2-debug`) to build a public GitHub Release containing:

- `BackroomsPort-Java-Resource-Pack-<version>.zip`
- SHA-1 checksum for Minecraft server configuration
- SHA-256 checksum for ordinary integrity verification

The release ZIP is the URL that should eventually be used as the Java server resource-pack URL. The SHA-1 emitted alongside it is the value intended for the server's resource-pack hash setting.

## Important boundary

This repository contains **client assets only**. Plugin Java source, server configuration, secrets, Discord integration, world data, recovery fixtures, and other private project material do not belong here.
