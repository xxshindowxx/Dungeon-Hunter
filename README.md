# `Dungeon Hunter`

A content-rich single-player console RPG built with `C#` and `.NET Framework 4.7.2`.

## Overview

`Dungeon Hunter` is a progression-heavy dungeon crawler that expands into a broader fantasy world with kingdom politics, faction systems, player housing, dynamic wars, city conditions, and persistent world-state changes.

The codebase is structured as a self-contained `Visual Studio` game project with serialized save support, configurable data loading, and gameplay-first implementation in plain C#.

## Core Product Value

- playable dungeon-crawler loop with floor progression, combat, loot, bosses, crafting, and leveling
- surface-world expansion that turns the project into a hybrid dungeon crawler + world simulation
- persistent save data for player progression, map state, bestiary discovery, housing, politics, reputation, and world changes
- layered long-run systems that support replayability and future content expansion
- lightweight technical footprint with no engine dependency

## Main Gameplay Systems

### `Dungeon Progression`
- floor-based dungeon exploration
- themed floors, boss floors, and special floor events
- home-base floor and long-run progression pacing
- enemy scaling, encounter pacing, and floor rewards
- persistent floor resume state including explored rooms and current position

### `Combat and Character Growth`
- class and advanced class progression
- elemental abilities such as `Fire`, `Ice`, and `Dark`
- weapon upgrades, armor scaling, healing, and status effects
- durability, repair, and combat stat tracking
- glory-based meta progression through repeat runs

### `Inventory, Crafting, and Economy`
- inventory and item storage
- crafting recipes and repair flows
- general shops, crafting stations, and special trader encounters
- market-style shop behavior with per-floor special offers and elemental supply/demand shifts
- selling, buying, and upgrade progression tied to shop unlocks

### `Bestiary and Discovery`
- persistent bestiary entries that unlock through enemy kills
- tracked discovered and undiscovered enemies
- multi-page bestiary viewing designed for console play
- enemy weaknesses, elemental traits, and drop visibility

### `Housing and Home Progression`
- original dungeon home-base progression
- buyable kingdom homes in capital cities
- home upgrades, guards, traps, repairs, storage, and training spaces
- named staff, staff services, and kingdom-specific house bonuses
- fast travel between owned homes

### `Overworld and Story World`
- kingdoms, cities, rulers, and capital hubs
- kingdom reputation and faction learning
- guild systems, wizard training, soldier contracts, and war boards
- story progression beyond the dungeon after deeper floor milestones
- world conditions such as `Prospering`, `Recovering`, `Triumphant`, `Shaken`, `Occupied`, and `Under Watch`

### `Political Simulation`
- kingdom wars with multiple contract types
- war outcomes that change rulers and city conditions
- repeated war losses that can trigger occupations and takeovers
- liberation contracts that break occupation control
- ruler rewards and punishments based on player reputation

### `Local City Content`
- local city problem chains
- city-specific rewards and longer-term condition changes
- controller- and occupation-aware city behavior
- city bonuses for completing multi-stage local problems

## Save and Persistence Features

The current save system preserves more than base character stats. A resumed run can restore:

- player progression and inventory
- bestiary discovery state
- current dungeon floor
- current room position on the active floor
- explored map layout on the active floor
- pending room events on the active floor
- current floor event state
- encounter counter state
- shop market state and per-floor special store offers
- broader world-state changes such as housing, kingdom politics, city conditions, and reputation

The game currently supports multiple save triggers during normal play:

- quitting the game saves the current run
- leaving the store writes a checkpoint of the current run state
- manual save options are available from inventory, lakeside home menus, city and guild menus, kingdom-home menus, storage menus, house staff menus, the burned-home menu, and the war board

## Console UI Status

The game now uses a more structured console presentation layer than the original prototype version.

- full-page rendering is used across major menus and gameplay screens
- menu-heavy screens have been compacted to fit common terminal sizes more reliably
- the bestiary uses dedicated paged rendering to avoid host scrollback issues
- layout has been tuned around typical `Windows Terminal` / console sizes such as roughly `120x30`

Because this is still a console game running under different hosts, display behavior can still vary somewhat between `Visual Studio`, `Windows Terminal`, and classic `conhost`.

## Technical Highlights

- built as a traditional `Visual Studio` solution/project
- gameplay logic implemented directly in C# source without engine lock-in
- serialization-based persistence for player and world state
- centralized data access through `GameDataRepository.cs`
- modular gameplay files such as:
  - `Program.cs`
  - `Player.cs`
  - `StoryWorld.cs`
  - `Encounters.cs`
  - `Crafting.cs`
  - `Inventory.cs`
  - `HomeBase.cs`
  - `Store.cs`
  - `Map.cs`
  - `Bestinary.cs`

## Why This Project Has Buyer Potential

- already contains a large amount of implemented gameplay rather than only a prototype loop
- can be sold as:
  - a complete indie RPG starter project
  - a moddable console RPG framework
  - a foundation for porting into a larger UI or engine-backed product
- content breadth supports future expansion into:
  - UI modernization
  - balancing passes
  - more factions, kingdoms, quests, and endings
  - packaging, storefront presentation, and commercial polish

## Current Platform

- `C# 7.3`
- `.NET Framework 4.7.2`
- console application
- developed in `Visual Studio`

## Suggested Buyer Angles

- retro / text-based RPG audience
- solo indie developer looking for a feature-rich starting point
- studio prototype team seeking a deep progression sandbox
- reseller looking for a content-heavy C# RPG project with room for polish and commercialization

## Repository Notes

This codebase is gameplay-first. Its strongest selling points are content depth, layered progression, persistent world-state systems, and breadth of implemented mechanics rather than graphics or engine tooling.

## Build

Open `Dungeon Hunter.csproj` in `Visual Studio` and build normally for `.NET Framework 4.7.2`.
