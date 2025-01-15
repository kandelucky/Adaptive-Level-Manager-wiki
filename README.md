# Adaptive Level Manager

If you're looking for a flexible and efficient solution to manage the levels of your game, **Adaptive Level Manager** is exactly what you need. This unique system allows you to easily define when, where, and how new levels are unlocked, what criteria players must meet to progress, and how to evaluate their performance with stars, scores, or other metrics.

## Key Features of Adaptive Level Manager:

- **Flexible global level unlock logic**:
  Unlock levels based on stars, scores, or no criteria at all.
- **Customizable level-specific settings**:
  Override global parameters for individual levels.
- **Extendable parameters**:
  Add unique data points specific to each level.
- **Player progress control**:
  Manage stars, scores, errors, and time limits.
- **ScriptableObject architecture**:
  Simplifies data initialization and sharing across scenes.
- **Demo projects included**:
  Demonstrate the manager's features in action.

---

## Core Components:

The Adaptive Level Manager consists of the following:

1. **LevelManager**:  
   Provides the central mechanics for unlocking levels.
2. **LevelLoader**:  
   Handles the process of loading levels.
3. **LevelManagerData**:  
   Stores global criteria and parameters.
4. **LevelData**:  
   Assigns unique properties to each level.
5. **Storage**:  
   Saves player progress using Unity's `PlayerPrefs`.

---

# What You Can Do:

- **Define unlocking rules**:  
  Easily configure when, where, and how levels are unlocked or locked.
- **Monitor player progress**:  
  Track stars, scores, errors, and time.
- **Add unique parameters**:  
  Extend level data with custom settings.
- **Show progress in the UI**:  
  Reflect the game’s progress in real time.
- **Save player data**:  
  Persist player progress across sessions.

---

## Demo Projects

Explore the included demo projects to see how Adaptive Level Manager can elevate your game.

---

## Why Choose Adaptive Level Manager?

This solution helps you create games of any genre whether it's arcade, adventure, or puzzle. With **simple integration**, **flexible configurations**, and **extensible architecture**, you'll save time and easily deliver a high-quality gaming experience.

---

**Start building smarter games today with Adaptive Level Manager!**








---

<br/>

# About Manager

## LevelManager.cs


### Level Unlocking Logic

The unlocking status of levels is determined by **UnlockCriteria**, which can be one of the following:
- **None**: The level is always unlocked.
- **Stars**: The player must collect a specific number of stars in the previous level.
- **Score**: The player must achieve a certain score in the previous level.

---

### Unlocking the First Level

The first level is always unlocked, and players do not need to meet any criteria to access it.

---

### Unlocking Subsequent Levels

To unlock subsequent levels, players must satisfy the criteria (e.g., stars or score) of the previous level.

---

### Global vs. Individual Criteria

Levels have two types of unlock criteria:
1. **Global Criteria (LevelManagerData)**:  
   Shared criteria applied to all levels, e.g., collecting stars across the game.
2. **Individual Criteria (LevelData)**:  
   Specific criteria tailored to an individual level, overriding the global criteria.

This system allows you to set unique parameters for specific levels. For example:
- Globally, levels require stars to unlock.
- However, a particular level may require a specific score instead.

---

### Behavior of Individual Criteria

When a level is unlocked based on individual criteria:
- If the previous level has a criterion (e.g., stars or score), fulfilling that criterion unlocks the current level.
- If the previous level is automatically unlocked (e.g., `UnlockCriteria.None`), its status is ignored, and the unlocking is based on the last valid level's criteria.

---

### Displaying Messages to Players

When a new level is unlocked, players see a notification, such as:
- **"Level 2 - Unlocked!"**

If a level is still locked but the player attempts to access it, they see a message like:
- **"Level 3 - Locked!"**

  ------------------------------------
## LevelLoader.cs
------------------------------------

The **LevelLoader** script in Unity is responsible for loading levels and managing the associated data (`LevelData`).

It initializes all necessary parameters required for level management, whether based on individual or global needs, such as:
- **Stars**: Required and achievable numbers of stars.
- **Score**: Required and achievable scores.
- **Errors and Time Limits**: Constraints for the level.
- **Unlock Criteria**: Determines how the level can be unlocked.

---

### Key Features:

- Ensures smooth initialization of level-specific settings.
- Integrates with global and individual level requirements.

---

------------------------------------
## LevelManagerData.cs ScriptableObject
------------------------------------

The **LevelManagerData** is a `ScriptableObject` that manages global parameters and criteria for the game’s levels. Its primary purpose is to provide centralized access and initialization for level data.

### Main Features:

- Provides unified management for global criteria and parameters across all levels.
- Defines the requirements for unlocking and winning levels.

---

### Managing Star Icons:

The **LevelManagerData** also handles star icons, which visually represent the player's progress:
- **Gold**: Star collected by the player.
- **Grey**: Star not collected yet.
- **Empty**: Represents newly unlocked levels.

This system ensures clear communication of the player's progress and achievements.


------------------------------------
## LevelData.cs
------------------------------------

The **LevelData** is one of the most critical components of the Adaptive Level Manager, as it stores and manages all essential data for a specific level. This object allows developers to customize parameters for each level, enhancing the manager’s flexibility and enabling game personalization.

---

### Key Features:

- **Level-Specific Data Storage**:  
  Stores unique information for each level, such as scores, stars, and more.
- **Level Statuses**:  
  Each level can have one of the following statuses:  
  - **Locked**  
  - **Unlocked**  
  - **Win**  
  - **Lose**  
  - **Done**

---

### Overriding Global Parameters

If `overrideGlobalCriteria` is enabled, the level uses its specific criteria instead of global parameters.  
- Each level can have its own `UnlockCriteria`, star requirements, scores, and other parameters.

---

### Custom Parameters for Unique Levels

Developers can add their custom parameters to tailor levels to specific game mechanics. For example:
- **Number of enemies** per level.
- **Special elements** unique to a specific level.
- **Visual effect settings** for enhanced customization.

---

### Real-Time Progress Management

- Player data, such as **stars** and **scores**, is stored and can be utilized to update the game’s UI dynamically.

---

### Why Use LevelData?

The **LevelData** component ensures every level is fully customizable, from its unlocking conditions to unique mechanics and visual elements. It enables developers to create highly personalized gameplay experiences for players while maintaining a structured and scalable system.

------------------------------------
## Storage.cs
------------------------------------

The **Storage** class is a utility class designed to simplify saving and loading game data using Unity's `PlayerPrefs` API. It offers extensive functionality, allowing developers to store and retrieve various types of data, including:
- **int**
- **float**
- **bool**
- **string**
- **enum**

---

### Key Features:

- **Easy Integration**:  
  Quickly save and load data without dealing directly with `PlayerPrefs`.
- **Supports Multiple Data Types**:  
  Store and retrieve common data types with ease.
- **Reliable Data Management**:  
  Ensures efficient and straightforward handling of persistent game data.

====================================
## DemoGameManager.cs

When transitioning to each level, the player enters a demo game scene controlled by the **Demo Game Manager**, which operates based on the `LevelData` loaded for that level.

---

### Logic Implemented in the Game Manager:

#### Star Control:
- Tracks and updates the stars collected by the player.
- The number of stars collected determines whether the level is completed and how successfully it was completed.

#### Score Control:
- Each added score is compared with the maximum score (high score), and progress is updated accordingly.

#### Error Control:
- If the player reaches the error limit, the game ends with the appropriate status (Done/Lose).

#### Time Control:
- The manager tracks how much time remains or has elapsed.  
  If the time runs out, the game ends with the appropriate status (Done/Lose).

---

### UI Updates:
All changes (time, stars, score, errors) are reflected in the UI in real-time, helping the player keep track of their progress.

---

### Progress Saving:
Player achievements (stars, scores, level status) are saved using the **Storage** class.

---

### Managing Level Completion Scenarios:

#### Winning:
- If the player meets all criteria (e.g., required stars or scores), the level ends with a "Win" status.

#### Losing:
- If the player fails to meet the criteria or exceeds the allowed number of errors, the level ends with a "Lose" status.

#### Done:
- The level ends upon meeting the minimum criteria but is not considered a full "win."

---

### Pop-Up Windows:
For each scenario (**Win, Lose, Done**), the manager displays an appropriate pop-up window to help the player understand the result clearly.

====================================
## Demo Scenes

The manager provides functional demo scenes for testing various configurations.

---

### Demo 1: Single Shared Scene
- **Setup**: A single scene (Menu + one shared gameplay scene for all levels).  
  - Different data is passed to the same gameplay scene using the `LevelData` ScriptableObject.  
- **Menu Representation**: The menu is displayed as a list.

### Demo 2: Unique Scenes for Each Level
- **Setup**: Unique scenes for different levels (Menu + 10 unique gameplay scenes).  
  - Each level-specific scene receives unique data using the `LevelData` ScriptableObject.  
- **Menu Representation**: The menu is displayed as a map.

---

### Testing Configurations

Both demo projects provide five testing configurations based on `ScriptableObject`, stored in the `Demos/Level Manager Data examples` folder:

1. **ALL UNLOCKED**:  
   All levels are open with no restrictions.
2. **Score - ALL UNLOCKED**:  
   All levels are open and display scores.
3. **Score**:  
   Levels unlock based on score progress.
4. **Stars - ALL UNLOCKED**:  
   All levels are open and display stars.
5. **Stars**:  
   Levels unlock based on the number of stars.

---

### Total Possible Combinations

- **Stars or Scores**: 2 options (Stars or Scores).
- **Time**: 2 options (Time condition enabled or not).
- **Errors**: 2 options (Error condition enabled or not).
- **Locking**: 2 options (Unlocking condition enabled or not).  

**Total Combinations**: 16

---

### Why Use This System?

This system is ideal for managing levels of any type of game, whether it’s arcade, adventure, or puzzle. Its flexibility and ease of use make level management simple and deliver a unique experience for players.

