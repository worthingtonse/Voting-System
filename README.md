# Voting-System
How the RAIDAX technology can be used to allow people to vote. 

## Standard Election Standards: 
* Each Voter needs to have a voter ID.
* There needs to be a way to know who voted.But we do not want to know who each voter voted for.
* The number of people who voted must match the number of ballots that were returned.
* Voters must be able to check a list of people who voted to make sure they are on it.
  
## Hardware Requirements:
* Requires 25 different and independent “Voter Registrars” who each have a desktop computer that will be left on all the time and run the RAIDAX software. The number can be reduced with some tweaks to the client software.
* Each voter needs desktop computer running the voter client software.

## Election Workflow
1. Voters register to vote by posting documents (such as a png of their driver’s license) on the RAIDA using the ultra secure document transmission and storage technology which stripes the data over 16 servers. 
2. There is a backdoor that allows the 25 Registrars of Voters to access the voter’s documents and issue Voter Register ID token on their RAIDAX. Each ID token has a unique serial number and is linked to the voter in the voter database. Each RAIDAX admin (Voter Registrar) has an independent database of voters.
3. The Registrar of Voters places the Voter ID Token into the voter’s folder on that Registrar’s RAIDAX. 
4. The Voter’s ID Token is automatically downloaded by the voter’s desktop software and the Voter’s ID Token’s passwords are changed so that only that voter can use the voter the token. 
5. Voter Registrar creates a voter database that is available to the public. Each of the 25 voter databases can be compared to see if they all contain the same voters.
6. At the time of election, Each Voter Registrar puts a ballot in each voter’s RAIDA ballot folder on the RAIDX. 
7. The ballot consists of:
  * A list of races and the candidates running for each race. Each candidate has a candidate ID.
  * A voting token for each race. Each token has a unique serial number that can only be used once. 
  * A voter guide that explains how it works and has candidate statements
8. Voter can see the candidates on their desktop software’s graphical interface and can check the candidates they want to vote for. 
9. The Voter connects to the RAIDA using their voter ID as the encryption key and requests a Kerberos ticket from every RAIDA using the voting tokens for each race. These tickets prove that the user’s voter tokens are authentic on that RAIDA sever. The voter ID and the Voter's IP address are recorded in each of the 25 RAIDAX's databases so that it can be shown who voted and at what IP address. 
10. The Voter encrypts their ballot 25 times using each RAIDA’s ticket.
11. The Voter sends each of the 25 RAIDA (minus one) their ballot that has been encrypted by the other RAIDAs tickets.
12. Each RAIDA contact each of the other RAIDA and presents it with the ticket. The other RAIDA return the ballot unencrypted. (The transmission is encrypted for quantum safe communication)
13. Each RAIDA compares the 24 different responses and makes sure that all of the responses contained the same ballot with the same candidates getting the same votes. Now each RAIDA has the vote count.  
14. All voters can see the vote count on all the RAIDA and compare them to see that they are all have the same results.
15. The number of voters who authenticated to get tickets should be the same as the number of ballots submitted. All people who voted should be on the voter rolls. 
16. Now we can prove who received a ballot and voted. We can also see the ballots but not know who cast them. Since the process is done redundantly on 25 servers controlled by independent registrars who should be from different factions, cheating will be obvious because the results will be different on each RAIDAX. 
## Weaknesses
* There should be many different versions of the server and client software created by different factions but using the same protocol. This ensures that software tampering can be detected in the election results. 
* The users have to talk to the 25 servers and that means the client software must know the IP addresses of each of the servers. If users are given fake addresses, they may think that they are voting when they are not. This can be found if voters check the public list of who voted and they don’t see their name there. Therefor, users must be encouraged to go to their faction's website and look at a role of who voted for confirmation. 
