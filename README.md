# Mice_ASD_Detection

Includes code file from several consecutive projects, aimed at detecting ASD symptoms in mice, using analysis of their squeaks
> January 2022: Final improvements - after performing L1 + L2 regularization and further tuning of hyper-parameters, we achieved a final accuracy of 88%.

> December 2021: Further Improvements - after syllable classification, we extracted additional features and developed an XGBoost model to predict genotype of each mouse, succeeding with accuracy of 81%.

> October 2021: Starting move of files from google drive 'USV_Project_2021' to Github repository 'Mice_ASD_Detection'.  
> All files written previous to our project are zipped and saved as "Project_Freeze_Sep2021_code_files.zip"
  
<img src="https://github.com/etgins/Mice_ASD_Detection/blob/main/project_description.png">

## File Descriptions


|File name | Description | Archive/Version | Notes
|-|-|-|----------------|
|`Project_Freeze_Sep2021_code_files.zip`|Archive of all previous projects before our own. Includes data and code files for segmentation and classification of syllables. | Archive|
|`Statistics_generator.ipynb`|Generates statistics over data (previous projects)| Archive |
|`Transfer_learning_2nd.ipynb`|Used to classify the syllables in each segmented recording (previous projects)| Archive |
|`audio_feature_extraction.ipynb`| feature extraction from total_data UPDATED EM 020821.xlsx. | Archive |In this file, all samples from each mouse are reduced to a single sample with mean features.
|`audio_feature_extraction_REDUCTION_BY_RECORDING.ipynb`| feature extraction from total_data UPDATED EM 020821.xlsx| Version: Final |In this file, all samples from each mouse are reduced to a single sample PER RECORDING NUMBER with mean features.
|`final_classification.ipynb`| XGBoost model - training and testing on processed_data_for_final_classification.csv. Predicts genotype of each mouse (WT / HT).| Version: Final |
|`processed_data_for_final_classification.csv`| Data AFTER feature extraction, ready to be input to final_classification.ipynb | ??? |
|`total_data UPDATED EM 020821.xlsx`| Tagged data of each syllable recording after segmentation and classification (done in previous projects). Used as input for feature_extraction. | ??? |

## Project Result regeneration:
#### - Syllable Classification (previous projects): 
   * run transfer_learning_2nd.ipynb
#### - Final Classification: 
   * run audio_feature_extraction_REDUCTION_BY_RECORDING.ipynb 
      * extracts features from total_data UPDATED EM 020821.xlsx
   * then run final_classification.ipynb.

## Google Drive + Code files info (by: Guy Lavi & Vered Wolfman):
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
