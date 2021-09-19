# Election_Analysis

## Project Overview

A Colorado Board of Election employee has given me the following tasks to complete the election audit of recent local congressional election.

  1. Calculate the total number of votes cast
  2. Get a complete list of candidates who recieved votes
  3. Calculate the total number of votes each candidate recieved 
  3. Calculate the percentage of votes for each candidate recieved
  4. The voter turnout for each county 
  5. The percentage of votes from each county 
  6. The county with the highest number of votes
  7. Determine the winner of the election based on the popular vote

## Resources
- Data Source: election_results.csv
- Software: Python 3.6.1, Visual Studio Code, 1.38.1

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Election-Audit Results

- There were 369,711 votes were casted in the congressional election.

- **The candidate were** 
  ```
      1. Charles Casper Stockham
      2. Diana DeGette
      3. Raymon Anthony Doane
   ``` 
- **The candidate results were**
```
    1. Candidate **Charles Casper Stockham** recieved "23.0%" of the vote and "85,213" number of votes
    2. Candidate **Diana DeGette recieved** "73.8%" of the vote and "272,892" number of votes
    3. Candidate **Raymon Anthony Doane** recieved "3.1%" of the vote and "11,606" number of votes
```
- **The Counties and number of votes and percentage**
  ```
      1. Jefferson: 10.5% (38,855) 
      2. Denver: 82.8% (306,055) 
      3. Arapahoe: 6.7% (24,801) 
  ``` 
- **The county with the largest number of votes**    
  ```
      Denver: 82.8% (306,055)  
  ```   
- **The winner of the election**
- Candidate Diana DeGette recieved who recieved 73.8% of the vote and "272,892" number of votes.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------
![Electionresult](https://github.com/11nithin/Election_Analysis/blob/main/Resources/Election_result.PNG)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Election-Audit Summary

 The greatest advantage of the this code is with slight modification this can be used for any election. This script can be used in any election with dataset that consists of a number for the ballot ID, name for the county and candidate  to determine: total number of votes cast, a complete list of candidates who received votes, total number of votes each candidate received, percentage of votes each candidate won, the winner of the election based on popular vote, the voter turnout for each county, the percentage of votes from each county out of the total count, and the county with the highest turnout.
  One of the exapmple this script is very useful is the if there is federal election the county can be replaced by state.
   
  The second example is that the script is designed to iterate through specific rows see the code below. Just by changing the row index depending on the data we can get detailed report. 
```
for row in reader:

        # Add to the total vote count
        total_votes = total_votes + 1

        # Get the candidate name from each row.
        candidate_name = row[2]

        # 3: Extract the county name from each row.
        county_name = row[1]
```


		The third advantage of this script is since this saves all the candiates name and county in list. There is no limit if there is more than 3 county or 3 candidates
```
if candidate_name not in candidate_options:

            # Add the candidate name to the candidate list.
            candidate_options.append(candidate_name)

            # And begin tracking that candidate's voter count.
            candidate_votes[candidate_name] = 0

        # Add a vote to that candidate's count
        candidate_votes[candidate_name] += 1

        # 4a: Write an if statement that checks that the
        # county does not match any existing county in the county list.
        if county_name not in county_list:

            # 4b: Add the existing county to the list of counties.
            county_list.append(county_name)


            # 4c: Begin tracking the county's vote count.
            county_votes[county_name] = 0

        # 5: Add a vote to that county's vote count.
        county_votes[county_name] += 1

```