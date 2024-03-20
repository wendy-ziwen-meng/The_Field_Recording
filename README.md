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

<p align="center">
  <img src="https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/e9e5ee50-0041-4248-bef0-d614f8b2d57c" alt="MaxUI" style="width: 45%;"/>
  <img src="https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/3a879b6b-c12e-41b5-af66-786e35759522" alt="TDUI" style="width: 45%;"/>
</p>

On the left-hand side is the MaxMSP interface. At its top, a toggle acts as the primary control for starting and stopping the recording of the whale-like voices crafted by users. Beside this toggle, a dedicated "bang" button provides the functionality to save these unique audio creations under personalized names. Below these controls, a trio of windows offers a detailed view into the audio transformation process: the left window displays the waveform of the user's voice, the right window illustrates the selected whale call sample, and the central window merges these two worlds, showcasing the synthesized audio. This layout is designed for intuitive use.

On the right-hand side, the TouchDesigner interface presents itself, dedicated to visualizing the stylized audio spectrum of the whale sounds generated and saved by the user. In the lower section of this interface, an array of spectrograms is accentuated, each aligning with specific samples activated by the user’s voice. While this demonstration showcases all triggered samples simultaneously for illustrative purposes, the installation itself selectively presents one at any given time. This strategic design choice not only serves an educational function, revealing the vast spectrum of whale sounds, but also aims to enhance participants' comprehension of these intricate marine vocalizations. It’s a considerate arrangement, crafted to not just elevate the user interaction but to foster a deeper appreciation for the rich acoustic diversity beneath the ocean’s surface.

## Technology Pipeline

![Pipeline](https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/5c6ecca9-66c8-45f1-8051-9fe112e1336b)

The overarching technology pipeline of this project is illustrated above. Every three seconds, audio input from the microphone undergoes analysis and comparison against six distinct whale call samples. The sample demonstrating the closest resemblance is then seamlessly integrated with the human voice via a vocoder. This three-second interval was strategically chosen, acknowledging that the duration of the longest whale call is approximately two seconds, thus ensuring each individual call is fully represented in the final composition. Consequently, the output is a harmonious sequence of complete whale calls, forming phrases that serve as the foundational elements of a whale song.

Upon identifying the whale call that most closely matches the human voice, the MaxMSP patch transmits the index of the selected sample (ranging from 0 to 5) to TouchDesigner through OSC protocol. TouchDesigner, in response, highlights the corresponding spectrogram on the display. Following the user's completion and saving of the phrase, TouchDesigner updates its background visual to reflect the audio spectrum of the newly recorded sequence, creating a dynamic and interactive visual experience that complements the auditory creation.

## MaxMSP
Here shows an overview of the main patch. Inside the patch, the sub-patch SampleSelect and vocoder are the key functions.
<img width="1105" alt="Patch_Overview" src="https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/1befa972-a19e-4663-ae92-85062bf01cfc">

Below on the left-hand side is the SampleSelect patch used for comparing the pitch of the microphone input and the samples. The sub-patch, PitchCheck, compares the fundamental frequency of the voice with the sample frequency by taking the absolute difference.

On the right-hand side is the vocoder patch. At its core, the patch utilizes the principle of vocoding, which involves mapping the dynamic volume contours of audio bands from the exciter onto the corresponding bands of the carrier signal. Here, the human voice from the microphone serves as the exciter, injecting speach or singing rhythm into the whale call sample that acts as the carrier. To achieve this, the patch employs two instances of the mc.bands~ abstraction for dissecting both the human voice and the whale soud into separate frequency bands. This separation allows for precise manipulation of each band's volume envelope, captured through squaring and smoothing processes, to mirror the intensity of the voice rhythmic patterns onto the whale call's tonal landscape.

<p align="center">
  <img src="https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/228daa61-150d-40cf-81b4-87a9f8ef07a2" alt="pSampleSelect" style="width: 45%;"/>
  <img src="https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/d8d493cb-19f1-4d63-af50-8faaf4b9c3c2" alt="pVocoder" style="width: 45%;"/>
</p>


## TouchDesigner
The overview provided here offers a glimpse into the TouchDesigner project, a platform that, akin to Max, utilizes a node-based programming approach. The final visual of the installation emerges from a meticulous process of iterating through various visualization techniques and fine-tuning parameters to achieve the desired outcome. Below is the finalized structure, showcasing the culmination of this creative exploration.
![TDOverview](https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/22f2a696-31f8-4d68-9ead-f8e60612c508)

The project uses two key elements to create an ocean-like atmosphere. The first involves using noise, blur, and displace effects to create visuals that resemble bubbles, capturing the feeling of sunlight filtering through ocean water. The second uses a ramp to adjust the color of the spectrogram, giving it a peaceful blue color that reflects the ocean's depth. In addition, a select function is used to highlight different whale call spectrograms, dynamically selecting the right sample based on the osc protocol. This careful use of visual effects and color themes enhances the overall experience, immersing users further into the marine environment that the project aims to replicate.
![TDramp](https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/9968e9e4-dc03-4953-8f6d-aa8e19b3c070)
![TDRandom](https://github.com/wendy-ziwen-meng/The_Field_Recording/assets/84087309/77ec1291-cf97-4dc8-9fd1-6db7caa4f1e4)


# Conclusions
The event was an excellent opportunity for people to learn more about these remarkable creatures while enjoying an interactive experience. The feedback from the installation day was predominantly positive, with attendees praising both the beauty of the concept and its educational value. Despite the positive feedback, there are a few areas we could look into for future improvements. While many attendees enjoyed vocalizing and interacting with the installation, some seemed to prefer speaking random sentences over singing. This could suggest a slight unease about performing musical elements in public - a small issue, but one that could enhance future experiences if addressed.

# Potential future works 
Based on observations and participant feedback, several opportunities for future enhancements have been identified:

* Guidance for Vocalization: To encourage more musical interaction, introducing guided activities, such as reading a poem or singing a well-known song, could make participants feel more comfortable and engaged. This would not only enhance the user experience but also potentially create a richer variety of sounds for the installation.

* Improved Pitch Mapping: The challenge of triggering specific whale samples due to background noise and the inherent spectral differences between human and whale vocalizations suggests a need for refined pitch mapping. Future iterations could explore linear or nonlinear mapping strategies to more accurately mirror the range and nuance of whale vocalizations. Adjusting the sensitivity for triggering higher-pitched whale sounds was a start, but a more sophisticated approach could offer a truer representation of the natural interactions between different pitches.

* Enriching the Dataset: Expanding the library of whale call samples would add depth and variety to the project, making the acoustic environment even more vibrant and authentic. This would also allow for a more complex and nuanced exploration of the marine soundscape.

* Smoothing Transitions: To further mimic the natural flow of whale songs, future work could focus on smoothing the transitions between calls. This adjustment aims to create a more seamless and song-like auditory experience, enhancing the illusion of diving into the ocean's acoustic layers.

* Inclusion of Other Species: Broadening the scope to include sounds from other marine species would enrich the project's educational value and immersive quality. Integrating calls from a wider range of ocean inhabitants could offer a more comprehensive view of the marine ecosystem's acoustic diversity.

These potential enhancements are driven by a desire not only to refine the technical aspects of the installation but also to deepen the emotional and educational impact on participants. By addressing these areas, the project can evolve into an even more engaging and enlightening experience, fostering a greater appreciation for the complexity and beauty of marine life's acoustic landscapes.
