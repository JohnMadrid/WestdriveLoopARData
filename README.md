# WestdriveLoopAR - Analysis 

## 1. Data extraction
Using `preprocessing.ipynb`:

- Data was extracted from .txt format to .csv format for easy analysis.
- The original 5 .txt files for each participant in the “EyeTracking” folder containing the eye data and the hitObjectNames were merged into a single .csv file containing all data. 
- During data extraction, we calculated the 5 HitObjectNames closest to the player. For this, we calculated the distance between the player’s position (HmdPosiiton) x,y,z vector3, and the HitObjectName position x,y,z.
- In cases where the same objectName was hit multiple times at the same time point, we chose the one with the shortest distance to the player. This was done to avoid having the same objectName multiple times within the final 5 and ending up rejecting other objects
- When one UID did not have all 5 .txt files, we assumed the drive was incomplete and therefore did not extract the data. 
- Similarly, when one of the .txt files was empty (possibly due to faulty recording), we did not process the UID.
- **OUTPUT:** The extraction code runs for all UID, extracts the information of the completed drives with data, and saves all information per participant in a single .csv file.
- An extra .csv contains all rejected UIDs and the reason for the rejection
Additionally, all information of the hit objects for each UID was saved in a separate folder (just in case we may want to look into them)

## 2. Data preprocessing
Using `analysis.ipynb`: 

- A .csv dataset was loaded, and an extra column containing the converted time to seconds, using' UnixTimeStamp' as a reference, was added to the .csv file for a user.
- The first and second closest objects to the player were visualized using a count plot to see the most ‘seen’ object names for the loaded UID. Countplots are grouped by the ‘city_section’ (e.g, training, mountainRoad, Autobahn, etc.,) 




