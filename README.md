# OHD RushMode

A Battlefield-inspired Rush game mode implementation for OHD. In this mode, attackers must destroy objectives while defenders try to prevent them from doing so. Each completed tier / stage opens up new territory for the attackers to advance.

## Core Components

The game mode requires three essential actors to be placed in your map:

### 1. RushPoint Actor
- Represents the objective that attackers must destroy
- Defenders must protect these points
- Can be placed in multiple locations per tier

### 2. RushBlockingVolume Actor
- Creates team-specific boundaries
- Prevents defenders from accessing attacker spawn areas
- Prevents attackers from accessing defender spawn areas
- Can be customized per tier to control the battlefield flow

### 3. RushSpawnPoint Actor
- Defines team spawn locations
- Supports multiple spawn points per team
- Can be configured per tier

## Tier System

The game progresses through multiple "Tiers" (stages), starting from Tier 0:

- Each tier represents a new section of the map
- No limit to the number of tiers or objectives per tier
- Teams advance/retreat based on objective completion
- Minimum requirements per tier:
  - 1 RushPoint (objective)
  - 2 SpawnPoints (1 per team)
  - Appropriate RushBlockingVolumes

## Setup Instructions

### Map Configuration
1. Open your map in the Unreal Editor
2. Place the required actors (RushPoint, RushBlockingVolume, RushSpawnPoint)
3. Configure each actor's tier number in their Details panel as well as team specific attributes. 
4. Ensure proper tier progression (start from 0)

### Testing the Game Mode
1. Open the "RUSH-TestMap" from the main folder
2. Configure the following settings:
   - GameMode: `RushGameMode`
   - HUD Class: `BP_RushHUD`
   - Player Controller Class: `RushPlayerController`
   - Game State Class: `RushGameState`
3. Press Play to test
