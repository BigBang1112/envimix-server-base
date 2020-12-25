# Envimix Server Base

The goal of Envimix Server Base (ESB in short) is to make the most flexible car mixing gameplay possible. It is a form of server controller that includes stardard yet improved gamemodes with adjusts for car mixing environment.

The project has been released open-source in an unfinished state on 25 December due to lack of time caused by other projects and studies. All the scripts are in public domain.

The only, currently stable, gamemode is **Envimix Team Attack** (EnvimixTeamAttack.Script.txt).

## How to install ESB

### Locally

1. Click on the big green Code button, click Download ZIP
2. Open the ZIP file
3. Extract the content of the folder `envimix-server-base-main` to your ManiaPlanet user data folder (usually Documents/ManiaPlanet)
   - You have to only include folders Items, Maps, Media and Scripts. Other files are unnecessary.

### On a dedicated server

1. Click on the big green Code button, click Download ZIP
2. Open the ZIP file
3. Extract the content of the folder `envimix-server-base-main` to your ManiaPlanet dedicated server user data folder (usually \[YourServer\]/UserData)
   - You have to only include folders Items, Maps, Media and Scripts. Other files are unnecessary.
   - Fresh dedicated server download is recommended

## How to start ESB

Before the explanations: The game can't currently recognize vehicle files in your user data folder - official title support is limited.

### In official Stadium game title

- Locally
  - Currently impossible.
- On a dedicated server
  - Not tested, maybe possible when `S_EnableStadiumEnvimix` set to `True` and with provided vehicle files.

### In other official game titles

1. If you want to play locally, choose LAN or Online play and create a new server
2. Use the [ESB_Nadeo.txt](Maps/MatchSettings/ESB_Nadeo.txt) match settings, or create a new match settings with a gamemode of your wish (only Envimix Team Attack currently working), and you can set these settings:
   - S_EnableUnitedCars: **True** (allow United cars, but they will appear as ValleyCars)

### In Dommy's TM² ALL title pack

1. If you want to play locally, choose LAN or Online play and create a new server
2. Create a match settings with a gamemode of your wish (only Envimix Team Attack currently working) and with this title pack, you can additionally set these settings:
   - S_EnableStadiumEnvimix: **True** (make it possible to load Stadium maps)
   - S_UseUnitedModels: **True** (change the United car models from ValleyCars to the models in the title pack)

### In TM² Island title pack

1. If you want to play locally, with OpenPlanet, choose LAN or Online play and create a new server
2. Use the [ESB_TM2Island.txt](Maps/MatchSettings/ESB_TM2Island.txt) match settings, or create a new match settings with a gamemode of your wish (only Envimix Team Attack currently working), and you **have to** set these settings:
   - S_EnableStadiumEnvimix: **True** (the title pack runs on Stadium environment)
   - S_VehicleFolder: **\[empty text\]** (the title pack has vehicles immediately in Items folder)
3. Additionally, you can set these settings:
   - S_SkinsFile: **Skins_Island.json** (use the skin set provided by the title pack)
   - S_UseUnitedModels: **True** (change the United car models from ValleyCars to the models in the title pack)

### In Nadeo Envimix title pack

Possible, but currently issue with 'Script not allowed for this title', and through Local Play, it doesn't allow to change the gamemode. Anyone's help will be appreciated.

## Script settings

More explanations soon.

- **UniverseModeBase.Script.txt**
  - S_WarmUpNb
  - S_WarmUpDuration
  - S_ForceLapsNb
  - S_ChatTime
  - S_EnableMapIntro
  - **Envimix.Script.txt**
    - S_EnableTM2Cars
    - S_EnableUnitedCars
    - S_EnableDefaultCar
    - S_EnableCustomCars
    - S_EnableStadiumEnvimix
    - S_UseUnitedModels
    - S_VehicleFolder
    - S_VehicleFileFormat
    - S_CarsFile
    - S_SkinsFile (Skins.json file providing a set of skins taken from the title pack)
    - S_UseSkillpoints (unused)
    - S_UseLadder
    - S_AllowRespawn (unused)
    - **EnvimixTeamAttack.Script.txt**
      - S_TimeLimit
      - S_CarSelectTime (at the start of each map, how long is the time for selecting your first car)

## Skins.json

Basically a JSON file that defines a name of each car and its possible selection of skin ZIPs, including icons (as ManiaScript can't read skin icons directly from ZIP).

Structure:

- Name of the car
  - Visual name of the skin (any, and can have spaces)
    - File path to the ZIP relative to `Skins/Models/`
    - Icon of the skin relative to `Media` folder

Example of the contents:

```json
{
   "CanyonCar": {
      "Ace": {
         "File": "CanyonCar/Ace.zip",
         "Icon": "Images/Skins/CanyonCar/Ace.dds"
      },
      "Defrag": {
         "File": "CanyonCar/Defrag.zip",
         "Icon": "Images/Skins/CanyonCar/Defrag.dds"
      },
      "Duke": {
         "File": "CanyonCar/Duke.zip",
         "Icon": "Images/Skins/CanyonCar/Duke.dds"
      }
   },
   "StadiumCar": {},
   "ValleyCar": {
      "AzurSwift": {
         "File": "ValleyCar/AzurSwift.zip",
         "Icon": "Images/Skins/ValleyCar/AzurSwift.dds"
      }
   }
}
```