---
prev: false
next: false
tags:
  - bsmg
  - beat saber
  - wiki
  - lighting
  - custom lights
  - make custom lights
  - custom environment
  - environment enhancement
description: |
  Learn to utilize Chroma to its full extent
---

# Chroma Environment Enhancement
Learn to utilize Chroma to its full extent.  
Remove, add, modify, and duplicate parts of the environment.

::: warning
This is a stub page, content is a work in progress!
:::

## Chroma
All Chroma related features are implemented within [custom data](./map-format.md#custom-data).  
Custom data for Chroma can be found at the root of each difficulty file and inside each event.

::: warning
To use Chroma, the user must have the Chroma mod installed.  
Unsure how to add Chroma to your game? [PC Modding](/pc-modding.md) | [Quest Modding](/quest-modding.md)
:::

### Adding Chroma as a suggestion
To use Chroma, it must be added as a suggestion or requirement in the beatmap's info.dat section.  
Saving your beatmap with [Chromapper](/mapping.md#chromapper) will automatically add Chroma as a suggestion. If you are using another editor, or if you want to make Chroma a requirement, you will need to add it manually.  
- Chromapper's [Prop Edit](https://github.com/FallenCharlotte/ChroMapper-PropEdit) plugin allows for map suggestions and requirements to be edited manually.
- You can maunally add Chroma to each difficulties' customData by adding/modifying the "_suggestions" or "_requirements" field. You can see how [here](https://github.com/Kylemc1413/SongCore/#infodat-explanation) (suggestions and requirements are at the bottom of the example file!)

::: warning
Saving your beatmap with the [Official Editor](/mapping.md#official-editor) will remove ALL custom data from your map. Be careful and creat backups when using it with Chroma.
:::

## Removing Environemnt Objects
One of the most common uses of Chroma is to remove pieces of the environemnt, like the Logo on Timbaland or the Spectrogram on Fitbeat.

### Accessing Chroma Logs
Before attempting to access anything in the environment, you need to know what it is named. The Chroma logs contain every piece of the environment.  
There are multiple ways to access the full chroma logs: 
- UGEcko made a [repo](https://github.com/UGEcko/Chroodle/tree/main/ChromaLogs) with all the chroma logs for versions 1.29.1, 1.34 and 1.37. Logs are prone to changing over time (but rarely do), so be warned that not everything is guarenteed to be up to date!
- For PC users, add --verbose as a launch parameter to the game and enable chroma logging by going to your own BeatSaber directory and setting `"PrintEnvironmentEnhancementDebug": true` in `\Beat Saber\UserData\Chroma.json`. This will output the Chroma Logs to your console.

### Interpreting Chroma Logs

Finding out exactly what matches with what inside the chroma logs is largely trial and error, however naming conventions tend to be somewhat intuitive. Below are some environemnt pieces that are commonly removed.
<!-- markdownlint-disable MD013 -->
| **Object Name**                                                                         | **Description**                                             |
| --------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| `Spectrograms`                                                                          | The audio visualisers                                       |
| `MonstercatLogoL`<br>`MonstercatLogoR`                                                  | The logo of the Monstercat environment                      |
| `RocketCar`<br>`RocketCar (1)`                                                          | The cars in the Rocket League environment                   |
| `Logo`                                                                                  | The Green Day and center Linkin Park logo                   |
| `TimbalandLogo`<br> `TimbalandLogo (1)`<br> `TimbalandLogo (2)`<br> `TimbalandLogo (3)` | The logo of the Timbaland environment                       |
| `LinkinParkTextLogoL`<br> `LinkinParkTextLogoR`                                         | The Linkin Park logo on the walls                           |
| `LinkinParkSoldier`                                                                     | The soldier art on the floor of the Linkin Park environment |
<!-- markdownlint-enable MD013 -->

### Removing Environment Objects with Chromapper
After opening one of your maps in Chromapper into the info screen, click on the pickaxe symbol below the Environment Removal text. Then click the + icon to add a new removal.
Each removal takes text and will remove all pieces of the environment **containing** that text.  
For example, adding `MonstercatLogo` will remove `MonstercatLogoL` and `MonstercatLogoR` since they both contain `MostercatLogo`.

:::warning
Chromapper's editor will not reflect environment enhancement changes, open your map in game to see the changes. You can use the fpfc launch parameter to access your levels without VR.
:::
