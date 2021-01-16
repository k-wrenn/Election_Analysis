# Election_Analysis
## Project Overview
A Colorado Board of Elections employee has given the following tasks to complete the election audit of a recent local congressional election.

1. Calculate the total number of votes cast
2. Get a complete list of candidates who received votes
3. Calculate the total number of votes each candidate received
4. Calculate the percentage of votes each candidate won
5. Determine the winner of the election based on popular vote
6. Voter turnout by county
7. Percentage fo votes from each county out of total count
8. The county with the highest turnout

## Resources
Data source: election_results.csv

Software: Python 3.6.7, Visual Studio Code 1.52.1

## Election-Audit Results
The analysis of the election shows that:
* 369,711 total votes were cast in the election
* There were 3 candidates:
    1. Charles Casper Stockham
    2. Diana DeGette
    3. Raymon Anthony Doane
* Vote breakdown by candidate:
    * Charles Casper Stockham: 23.0% (85,213)
    * Diana DeGette: 73.8% (272,892)
    * Raymon Anthony Doan: 3.1% (11,606)
* Vote breakdown by county:
    * Jefferson: 10.5% (38.855)
    * Denver: 82.8% (306,055)
    * Arapahoe: 6.7% (24,801)

The winner of the election, based on popular vote, was Diana DeGette, who received 73.8%, or 272,892, of the 369,711 total votes. The county with the highest number of votes was Denver, with 82.8% (306,055) of total votes cast. 

## Code Walk-through
To begin the analysis, I first needed to be able access the data set provided by the Board of Elections. This was done by importing the csv and os dependencies. Then, variables were created fo the files that needed to be open to retrieve the data and save to record the results. This was done via the following code:

         file_to_load= os.path.join(...)
         file_to_save= os.path.join(...)
Then, lists and dictionaries were created to hold the information requested by the board.

         candidate_options[] and county_list[] held the names of candidates and counties
         candidate_votes{} and county_votes{} held the total votes cast for each candidate and in each county

Next, multiple variables were initialized and set to zero to reflect the total number of votes cast and percentage of votes cast. These variables included:

         total_votes= 0
         winning_count = 0
         winning_county_count= 0

The **with open()** function was used to access the election data and loop through the rows to obtain the total number of votes, candidate names, and county names.

Next, using conditional statements, such as **if candidate_name not in candidate_options** or **if county_name not in county_list**, each of the unique candidate and county names were added to their respective lists utilizing .append. Then using **candidate_votes[candidate_name] += 1** and **county_votes[county_name]+=1**, 1 vote was added each time the name appeared in the data set.

Using **txt_file.write**, results were recorded in the text file, as requested by the Board of Elections. **print()** was used to print results into the terminal.

Format of the output was done through the use of f-strings (f""). To format percentages, **:.1f** was used and **:,** was used to format the various total vote counts.


## Election-Audit Summary
This script can easily be used in other elections because of the use of variables and indexes. If the data set provided held more information (i.e voter demographics such as race or gender or districts within a county), it would be fairly easy to add additional variables to futher break down the data by the new information.

For a more accurate voter turnout, it may be beneficial to know how many registered voters there are within the counties then compare the number of votes cast to the number of registered voters. Given the data we were provided, it appears as though Denver County had the best voter turnout, when in reality it was just the county with the largest number of overall votes. If the population in Arapahoe or Jefferson county are considerably smaller than that of Denver, it is logical to assume that Denver cast more votes, as they have more individuals to do so.
