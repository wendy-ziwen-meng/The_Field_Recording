![TD](https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/d58f25c4-7bae-4d99-bdf8-f2ed4a244b58)
# The Field Recording
An audio installation that transforms participants' voices into the sounds of humpback whales. 
A short video of installation experience can be found [here](https://youtu.be/J8NOpTYu4O0). 
One example recording from the instllation can be found [here](https://youtu.be/zZELFYo-IZE).

The Field Recording is an installation that transforms participants' voices into the sounds of humpback whales. By integrating sound processing and sound visualization technologies through MaxMSP and TouchDesigner, this piece offers an immersive dive into the oceanic realm, modulating human vocal expressions into the mysterious songs of humpback whales. Participants are invited to interact with the installation by speaking or singing into a specially designed interface, which then transform their voices to mimic the signature calls of humpback whales. This project is designed to amplify our empathy towards the ocean's giants through sound. It aims to forge a connection between humanity and the natural world but also serves as a reminder of the need to protect these beautiful creatures and their habitats. 

# Installation Overview
![Overview](https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/50b2018d-99e0-466f-ac5c-c2b5c63dc365)
The installation features a MaxMSP user interface alongside a display that presents interactive visuals created with TouchDesigner. Communication between the two software applications is facilitated through the OSC protocol.

![User_1](https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/84ad93da-51e9-4701-9119-f5bc2270e669)
![User_2](https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/fb5c2a36-5b74-48b7-af66-fc96b548fe01)
Participants are invited to speak or sing into a microphone, where their voices are transformed into the captivating sounds of humpback whales. They have the opportunity to record their unique whale calls using the MaxMSP interface. Further away from them is the display screen, at the bottom part of the screen, a real-time spectrogram reveals which whale call sample was utilized to craft their personalized call, enhancing the interactive and educational aspect of the experience.

# Background and Inspiration
This installation draws inspiration from Cosmo Sheldrake's album "[Wild Wet World](https://www.cosmosheldrake.com/music/wildwetworld)," a collection of music composed entirely of oceanic animal sounds, including the singing of humpback whales and the clicking of sperm whales, among others. This revelation opened my eyes to the profound understanding that aquatic animals are not so different from humans; they too have their unique songs, mirroring our own capacity for musical expression.
The song of the humpback whale particularly captivated me. Humpback whales exhibit highly variable vocalizations, which they arrange into phrases and themes to create songs. These songs evolve over time as whales incorporate new sounds or rearrange phrases. Interestingly, many humpback populations sing different songs, suggesting cultural phenomena within the species. I plan to create an installation that can convert human voices into sequences of various whale calls. This will not only provide an immersive experience but also serve an educational purpose.

## Whale Songs Research
![image](https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/caa9d695-b5d8-4d97-8632-cc174c7f73a4)
During the Cold War, the military's network of underwater microphones inadvertently recorded whale songs. These recordings were given to whale scientist Roger Payne and researcher Scott McVay, who, with the help of McVay's mathematician wife Hella, used a sonogram-printing device to visually represent the songs. They discovered that the songs had a repeating structure, and they developed a notation system to organize the patterns they found. 

The cornerstone of the installation leverages this fascinating discovery, activating various whale sound samples in response to the participant's pitch. These samples are then intricately blended with the input human voice using a vocoder, creating a harmonious fusion that bridges the auditory worlds of humans and whales.

To learn more about the history of whale song discovery, and the song structure, check:
* https://medium.com/@dealville/whales-synchronize-their-songs-across-oceans-and-theres-sheet-music-to-prove-it-b1667f603844
* https://whaletrust.org/song-structure-composition/
[Pattern Radio](https://medium.com/@alexanderchen/pattern-radio-whale-songs-242c692fff60) is also an inspiring project that worth checking, it utilizes AI to let people explore thousands of hours of whale songs.

## Whale Calls Sample

The whale call audio samples featured in the installation are sourced from the Marine Bioacoustics and Behavior Lab (“Sea BABEL”) at the University of New Hampshire, captured during the summer of 2012. You can find them [here](https://michellefournet.wordpress.com/sounds/).

# Design and Build
## Interface Design
## Technology Pipeline
## MaxMSP
## TouchDesigner

# Conclusions and potential future works 
