# Mice_ASD_Detection

Includes code file from several projects, aimed at detecting ASD symptoms in mice, using analysis of their squeaks
> October 2021: Starting move of files from google drive 'USV_Project_2021' to Github repository 'Mice_ASD_Detection'.


## drive + code info (by: Guy Lavi & Vered Wolfman):
### 1. E: + Recordings_Ella_Ayelet:  
   Recordings of the mice, along with the syllable classification in the excel files.  
    The recordings are filed by the mother's name, with sub-directories named by the cub's name. Inside are the recordings.  
    Some E: sub-directories have intermediate folders, such as 'day' or 'session'.  
    
### 2. Segmented syllables:  
   Two folders, ending with 'syllable', include segmented recordings of one syllable each, at length of 0.25 seconds, organized according to the excel files.  
    There are also .npy files, containing an array of the spectograms of the syllables, and an array of mathching tags.  
    
### 3. Codes:  
   The attached codes are made to create the data: segmentation of the recordings and saving in the folders, and creation of the .npy files.  
    Some code files contain classification models we implemented, or were implemented in previous projects.  
> April 2020: As of today, the codes are not organized and contain irrelevant fields, or ones meant to display for the user.  

   * data_creation -          uses the excel file /TODO: find name of file/ to trim syllables from full recording and save separate copy of the syllable only.  
   * spect_creation -         uses the trimmed syllables folder to create an array of spectograms (+ filtering) for the model training.  
   * statistics_generator -   performs the above code files, but the saved array contains and object for each full recording with its details and the model's classification of its syllables  
   * statistics test -      performs chi-squared tests and creates the graphs for the syllable distribution  
   * transfer_learning_2 -  creates and trains the syllable-classification model, and saves its trained weights in 'model_weights.h5'  
   
### 4. Data arrangement for statistics:  
   In order to create statistics, additional to the ones made by Guy \& Vered (2021), the wanted recordings' folders need to be ordered in a manner matching the attached .xls file (from Hava's lab or segmentation algorithm), and the code creating the statistics. The recordings must be ordered:
   - main folder containing all files and folders (can use E: or create new)
   - sub-folders named after the mother, matching the .xls file
   - sub-folders named after the cub, matching the .xls file
   - matching recordings according to each cub's files  
   (use these examples: 'total_data_recordings', 'data_united_recordings')
