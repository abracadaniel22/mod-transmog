# Transmog Module

- Latest Transmog build status with azerothcore: [![Build Status](https://github.com/azerothcore/mod-transmog/workflows/core-build/badge.svg?branch=master&event=push)](https://github.com/azerothcore/mod-transmog)

This is a module for [AzerothCore](http://www.azerothcore.org) that adds transmog feature, it's based on [Rochet2 Transmog Script](http://rochet2.github.io/Transmogrification.html) 

## Fork by Abracadaniel22

This fork adds a new `.transmog has [itemid]` command used by the [Transmog Collection](https://github.com/abracadaniel22/transmog-collection) addon to query if appearances have been collected. Additionally, it changes the appearance collected link colour to pink to match retail.

Example of command query and server response:

![02](https://github.com/user-attachments/assets/ec0525b4-eeec-454d-a5b0-3a144f778808)

Example of appearance collected link colour change:

![01](https://github.com/user-attachments/assets/b6659bb9-be72-4555-91a0-de8f1d11bb3b)

## Important notes

You have to use at least this AzerothCore commit:

<https://github.com/azerothcore/azerothcore-wotlk/commit/b6cb9247ba96a862ee274c0765004e6d2e66e9e4>

If using this module with an AzerothCore commit older than

<https://github.com/azerothcore/azerothcore-wotlk/commit/b34bc28e5b02514fca3519beac420c58faa89cad>

please delete the IDs 50000 and 50001 from npc_text before upgrading AzerothCore:
```sql
DELETE FROM `npc_text` WHERE `ID` IN (50000,50001);
```
Otherwise there will be conflicts for these IDs. The module will now use IDs 601083 and 601084 as default.

## Requirements

Transmogrification module currently requires:

AzerothCore v1.0.2+

## How to install

### 1) Simply place the module under the `modules` folder of your AzerothCore source folder.

You can do clone it via git under the azerothcore/modules directory:

```sh
cd path/to/azerothcore/modules
git clone https://github.com/abracadaniel22/mod-transmog.git
```

or you can manually [download the module](https://github.com/abracadaniel22/mod-transmog/archive/master.zip), unzip the Transmog folder and place it under the `azerothcore/modules` directory.

### 2) Import the SQL to the right Database (auth, world or characters)

Import the SQL manually to the right Database (auth, world or characters) or with the `db_assembler.sh` (if `include.sh` provided).

### 3) Re-run cmake and launch a clean build of AzerothCore

### 4) Place transmog npc

With a gm account goto the location you want to add the npc and use this command:

```
.npc add 190010
```

**That's it.**

### (Optional) Edit module configuration

If you need to change the module configuration, go to your server configuration folder (e.g. **etc**), copy `transmog.conf.dist` to `transmog.conf` and edit it as you prefer.


## License

This module is released under the [GNU AGPL license](https://github.com/azerothcore/mod-transmog/blob/master/LICENSE).





