# CAS_election_data
A comprehensive dataset of electoral results from Aruba, Curaçao, and Sint Maarten for research and educational purposes.


# About this repository
This repository contains electoral data from the three Caribbean autonomous states within the Kingdom of the Netherlands: Curaçao, Aruba, and Sint Maarten. The data spans multiple election cycles and provides a foundation for understanding political dynamics, voting patterns, and democratic processes in these Small Island Developing States (SIDS).

Maintained by: University of Aruba
Purpose: Educational resource for data science, political science, and Caribbean studies
Last updated: November 2025

# Dataset overview
The dataset includes election results from:

Aruba: 12 elections (1985-2024)
Curaçao: 6 elections (2010-2025)
Sint Maarten: 6 elections (2010-2024)

## Each record contains:

year: Election year
country: Territory name (Aruba, Curaçao, or Sint Maarten)
party: Political party abbreviation
votes: Number of votes received

# Data structure
The primary dataset (dutch_caribbean_elections.csv) is structured in tidy format with one row per party per election:
csvyear,country,party,votes
1985,Aruba,MEP,13786
1985,Aruba,AVP,11480
1985,Aruba,PPA,4499
This format makes the data easy to work with using common data analysis tools in R, Python, Excel, or any other software that reads CSV files.

# Data sources
Electoral data was compiled from Wikipedia articles:

Elections in Aruba
Elections in Curaçao
Elections in Sint Maarten

Wikipedia sources this information from official electoral authorities including:

Aruba: Departamento di Asuntonan Electoral (Electoral Affairs Department)
Curaçao: Kiesraad Curaçao (Electoral Council of Curaçao)
Sint Maarten: Main Voting Bureau of Sint Maarten

Important notes:

This dataset is compiled for educational purposes from publicly available sources
Students are encouraged to verify data with official electoral authorities for formal research
Understanding data provenance is an important part of data literacy

# How to use this data
## Loading the data in R
r# Load the data
elections <- read.csv("dutch_caribbean_elections.csv")

# View the first few rows
head(elections)

# Check the structure
str(elections)

# Get summary statistics
summary(elections)
Loading the data in Python
pythonimport pandas as pd

# Load the data
elections = pd.read_csv("dutch_caribbean_elections.csv")

# View the first few rows
print(elections.head())

# Check the structure
print(elections.info())

# Get summary statistics
print(elections.describe())
Basic analysis examples
Count elections by country:
rtable(elections$country)
Find the most successful party by votes in a specific year:
rlibrary(dplyr)

elections %>%
  filter(year == 2024, country == "Aruba") %>%
  arrange(desc(votes))
Calculate vote shares:
relections %>%
  group_by(year, country) %>%
  mutate(vote_share = votes / sum(votes) * 100) %>%
  arrange(year, country, desc(vote_share))


# Example scripts
This repository includes example scripts that demonstrate common analyses:

01_basic_exploration.R - Loading and exploring the data

02_visualization.R - Creating charts and graphs of election results

03_trends_analysis.R - Analyzing voting trends over time

04_comparative_analysis.R - Comparing patterns across territories

These scripts are designed for students learning data science and can be modified for your own research questions.
Educational use cases
This dataset is particularly useful for:

Introduction to data science courses - Practicing data loading, cleaning, and basic analysis
Data visualization courses - Creating meaningful charts about political trends
Statistical analysis - Exploring voting patterns, calculating vote shares, and identifying trends
Political science research - Understanding party systems and electoral behavior in SIDS
Caribbean studies - Analyzing democratic processes in the Dutch Caribbean

# Research questions you can explore

How has voter support for major parties changed over time?
What is the level of party fragmentation in each territory?
How do electoral systems affect political representation?
Are there patterns in coalition formation based on election results?
How does voter turnout compare across the three territories?
What role do new parties play in disrupting established political systems?

# Data limitations
Users should be aware of the following limitations:

Missing values: Some earlier elections lack registered voter and turnout data
Party continuity: Party names and abbreviations may change over time; some parties merge or split
Historical accuracy: Very early elections may have limited documentation
Scope: This dataset focuses on parliamentary elections only (not referenda or other votes)

# Contributing
This is a living dataset. If you identify errors or have additional verified election data to contribute, please:

Open an issue describing the correction or addition
Provide source documentation for verification
Submit a pull request with the proposed changes

All contributions will be reviewed for accuracy before incorporation.

# Citation
If you use this data in your research or educational materials, please cite:
University of Aruba (2025). CAS Election Data. 
Retrieved from [[https://github.com/University-of-Aruba/CAS_election_data]]

This dataset is provided under a Creative Commons Attribution 4.0 International License (CC BY 4.0). You are free to:

Share and adapt the data for any purpose
Use it for commercial or non-commercial purposes

Under the following terms:

Provide appropriate attribution
Indicate if changes were made

# Contact
For questions about this dataset or to report issues:
University of Aruba
Email: rendell.dekort@ua.aw
Website: www.ua.aw

# Acknowledgments
This dataset was compiled as part of educational initiatives at the University of Aruba to promote data literacy and support research on Caribbean political systems. Special thanks to the electoral authorities of Aruba, Curaçao, and Sint Maarten for making election results publicly available.
Last updated: November 2025
