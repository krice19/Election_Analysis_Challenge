# Election_Analysis_Challenge

## Projeect Overview

This project involves helping an employee from the Colorado Board of Elections complete the following tasks in a local election:

1. The total number of votes cast
2. Complete list of candidates who recieved votes
3. Percentage of votes each  candidate won
4. The total number of votes each candidate won
5. Winner of the election based on popular vote


## Resources

My resources used are:
1. Data Source: election_results.csv
2. Software: Python 3.8.2, Visual Studio Code 1.55.2


## Summary

The analysis of this election will show:

- The x amount of votes casted in the election
- The candidates in the election who received votes: Candidate 1, Candidate 2, and Candidate 3
- The candidate results:
  - the total number of votes candidate 1, 2, and 3 recieved
  - the percentage of the total vote candidate 1, 2, and 3 recieved
- The winner of the election:
  - Candidate 1, 2, or 3, who recieved Y amount of votes and X% of the total vote


## Challenge Overview

The challenge involves adding additional information to the results:

1. The voter turnout for each county
2. The percentage of votes from each county out of the total count
3. The county with the highest turnout

This analysis deepens our insight into the local election by gaining insight on county information of the election.  

## Challenge Results

From the analysis, I determined the following Results:

- A total of 369,711 votes were casted
- The counties recieved the following number of votes and percentage of total votes:
  - Jefferson county casted 10.5% of the votes, at 38,855
  - Denver county casted 82.8% of the votes, at 306,055
  - Arapahoe county casted 6.7%. of the votes, at 24,801
-  Denver county has the largest number of votes, at 306, 055

Below is an example of the code I used to gather the above information: 
    
    # 6a: Write a for loop to get the county from the county dictionary.

    for county_name in county_options:

        # 6b: Retrieve the county vote count.

        county_vote_count = county_votes.get(county_name)

        # 6c: Calculate the percentage of votes for the county.

        county_vote_percentage = float(county_vote_count) / float(total_votes) * 100

         # 6d: Print the county results to the terminal.

        county_results = (
            f"{county_name}: {county_vote_percentage:.1f}% ({county_vote_count:,})\n")

        print(county_results)

         # 6e: Save the county votes to a text file.

        txt_file.write(county_results)

         # 6f: Write an if statement to determine the winning county and get its vote count.
        if (county_vote_count > largest_votes):
            largest_votes = county_vote_count
            largest_county = county_name
            

-  The candidates recieved the following number of votes and percentage of the total votes:
  - Charles Casper Stockham: 23.0% (85,213)
  - Diana DeGette: 73.8% (272,892)
  - Raymon Anthony Doane: 3.1% (11,606)

Below is an example of the code I used to gather the above information:

    # Save the final candidate vote count to the text file.
    for candidate_name in candidate_votes:

        # Retrieve vote count and percentage
        votes = candidate_votes.get(candidate_name)
        vote_percentage = float(votes) / float(total_votes) * 100
        candidate_results = (
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")

        # Print each candidate's voter count and percentage to the
        # terminal.
        print(candidate_results)
        #  Save the candidate results to our text file.
        txt_file.write(candidate_results)

        # Determine winning vote count, winning percentage, and candidate.
        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage

 
- Diana DeGette won the election with a vote count of 272,892 which is 73.8% of the vote

Below is the code I used to determine the winning stats:

       # Determine winning vote count, winning percentage, and candidate.
        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage

## Challenge Summary
- change variables into states or city
- change index to match row the info is in
