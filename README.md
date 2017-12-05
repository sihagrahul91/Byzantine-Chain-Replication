# Byzantine-Chain-Replication
DistAlgo(Python) Implementation of Byzantine Chain Replication as described in - Robbert van Renesse, Chi Ho, and Nicolas Schiper.  Byzantine Chain Replication.  Proceedings of the 16th International Conference on Principles of Distributed Systems (OPODIS 2012), pages 345-359. Springer Verlag, December 2012.
URL: http://www.cs.cornell.edu/~ns672/publications/2012OPODIS.pdf

PLATFORM:
---------
1. Software Platform(s): DistAlgo Version 1.0.9, Python 3.6.2
DistAlgo References:
http://distalgo.cs.stonybrook.edu
https://github.com/DistAlgo/distalgo
http://www3.cs.stonybrook.edu/~liu/distalgo/language.pdf

2. Operating System: macOS Sierra Version 10.12.6

INSTRUCTIONS:
------------
To run the program, use below command

python -m da main.da <TestCaseFile>

PSEUDO-RANDOM WORKLOAD GENERATION:
-------------------
Randomizer function takes a seed and generate a sequence of numbers equal to number of requests provided as second argument.
pseudorandom(233,12) - generate 12 requests with seed value as 233

All generated numbers are in range 0-3 with following meanings:
0 - PUT
1 - APPEND
2 - SLICE
4 - GET

And if (number of requests * number of clients) is a multiple of 4, then all operations have same count. Otherwise also it make sure probability is almost same.
After generating these sequence of number, algorithm generates number of key - value pairs (combination of ascii lower + upper + digits) and generation is based on seed value given.
For a fixed value, request generated are same, so helps in reproducibility.

CONTRIBUTIONS:
-------------
Complete code is written and tested by Rahul Sihag.


MAIN FILES:
----------
API's for all three Clients, Replicas and Olympus is present in the following files.
1. replica.da - contains Server's code
2. olympus.da - contains Olympus code
3. client.da - contains Client's code
4. main.da - main function and parser api's
5. header.da - file containing utility api's

Log Files: All the logs generated go to logs folder.
