# Data Sonification of University Network Traffic  

This project takes raw CSV data of university network traffic (downloads and uploads), processes and enriches it with Python and Pandas, and prepares it for sonification. The final output is a CSV file designed to be used with the [TwoTone MIDI Out Beta](https://twotone-midiout-beta.netlify.app/) web application to turn the data into a musical composition.

This repository contains the Jupyter Notebook used for the data transformation and is intended to document the process for the accompanying Medium article.

# Project Overview
The core idea is to represent data not visually, but audibly. By mapping data points to musical notes, we can create a "soundscape" of the data that allows us to perceive patterns and trends in a completely new way. This project uses over a year's worth of daily network traffic data and transforms it into a weekly musical sequence.  

```
your-project/  
├── Sonify_Weekly_Traffic_to_CSV.ipynb  
├── input/  
│   └── (Your raw .csv files go here)  
├── output/  
│   └── Processed_traffic.csv  
└── README.md  
```


# Requirements & Setup
To run this notebook yourself, you will need Python 3 and a few common data science libraries.

1. Clone the repository:

git clone [https://github.com/world-wide-nige/NetworkSonification.git](https://github.com/world-wide-nige/NetworkSonification.git)
cd your-repo-name

2. Install the required libraries. It's recommended to use a virtual environment. The required libraries are listed in requirements.txt.
3. pip install -r requirements.txt

4. bshgdhsdsdsds

# How to Run
1. Place your data files: Add the raw CSV files you downloaded from the Janet Netsight Portal into the /input directory.
2. Run the Jupyter Notebook: Launch Jupyter Lab or Jupyter Notebook:
jupyter lab

3. Open Sonify_Weekly_CSV_Out_002.ipynb and run the cells sequentially.
4. Find the output: The final, processed CSV file will be saved in the /output directory.

# The Data Processing Pipeline

1. The notebook performs several key steps to prepare the data for sonification:
Data Loading & Cleaning: Reads multiple CSV files from the /input folder, combines them into a single DataFrame, and renames columns for clarity (in for download, out for upload).

2. Feature Engineering: Creates a rich set of time-based features from the timestamp, such as Week_Start, Month_Start, Year_Start, and Workday. These are designed to be used as triggers for specific sounds or musical changes.

3. Weekly Aggregation: Aggregates the daily data into weekly averages to create a smoother, more melodic output.

4. Proportional Quantization: This is the core of the project. To preserve the true relationship between download and upload volumes (where downloads are much larger), the script scales the values proportionally before mapping them to a 48-step musical scale. This ensures the sonification is an honest representation of the data.

5. Trend Analysis: Creates separate data columns for when traffic is increasing (_up) versus decreasing (_down). This allows for more dynamic compositions in the sonification tool (e.g., using an ascending arpeggio for "up" and a descending one for "down").

# Using the Output for Sonification
Once you have the final CSV file from the /output directory:

1. Navigate to the [TwoTone MIDI Out Beta](https://twotone-midiout-beta.netlify.app/) website.
2. Upload the generated CSV file.
3. Map the data columns (in_quant, out_quant, in_up, in_down, etc.) to the musical controls in the app (e.g., Pitch, Instrument, Style).
4. Experiment and listen to your data!

# Recommended Settings:
Download Data (in_up, in_down): Instrument: Double Bass, Range: 2 Octaves
Upload Data (out_up, out_down): Instrument: Glockenspiel, Range: 2 Octaves

# License
This project is licensed under the MIT License. See the LICENSE file for details.
