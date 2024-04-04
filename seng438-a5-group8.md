**SENG 438- Software Testing, Reliability, and Quality**

**Lab. Report \#5 – Software Reliability Assessment**

| Group  8  |
| :--------------:|
| **Student Names**      |
|       Stevan Beljic            |
|        Aaron Giang             |
|        Angelo Troncone             |
|        Rutvi Brahmbhatt             |

# Introduction
The goal of this assignment was to use reliability assessment tools such as C-SFRAT (the one we used), SRTAT, and a reliability demonstration chart (RDC) within Excel, to assess the the accuracy and predictability of failure reports. We are to use reliability growth testing software to measure failure rate, mean time between failures (MTTF), and familiarize ourselvs with the usage of such tools. We are then to use an RDC to determine adequacy of the computed MTTF of the SUT.
# 

# Assessment Using Reliability Growth Testing 

## Result of model comparison (selecting top two models)
We compared the following models in C-SFRAT to determine which trended most correspondingly with our input failure data from ```DATASET4.DAT``` within failure count reports:
- IFR Salvia & Bollinger
- IFR generalized Salvia & Bollinger
- S Distribution <- (one of the top two)
- Discrete Weibull Order 2
- Discrete Weibull Type III
- Geometric
- Negaive Binomial (Order 2) <- (one of top two)
- Truncated Logistic


Using the model comparison tab, we determined the two strongest/most accurate models were S distribution (S) and Negative Binomial Order 2 (NB2) because those two models have the highest Critic values (with values of 1.000), meaning they match up most accurately with the failure data provided. Purely from a visual perspective as well, the two plots of S and NB2 match the data set 4 failure data more accurately than any other model.<br>
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/79d9d5bb-7e80-4eb5-96f7-c3dfa116c9e9)
<br>
And the plots of the two most representative models (S and NB2), along with the original failure plot, are demonstrated below.<br>
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/fde201fc-fd6b-40ea-8e72-0e101b9ec4f7)

## Result of range analysis (an explanation of which part of data is good for proceeding with the analysis)
Stuff

## Plots for failure rate and reliability of the SUT for the test data provided
The failure data we used was ``DATASET4.DAT`` within the failure count reports. The original failure and model reliability plot is demonstrated in the chart below, plotting all 8 models atop our failure data.
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/feb198a3-9f28-4592-b20b-6a0582666951)

## A discussion on decision making given a target failure rate
Stuff

## A discussion on the advantages and disadvantages of reliability growth analysis
Stuff


# Assessment Using Reliability Demonstration Chart 

## 3 plots for MTTFmin, twice and half of it for your test data
MTTFmin = 2.85

MTTFmin
<br></br>
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/98921972/26205f3c-24ff-4389-9bbb-039b5e29544e)
<br></br>
2 x MTTFmin
<br></br>
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/98921972/019896f0-67e2-4c37-b9f5-81679d4786af)
<br></br>
0.5 x MTTFmin
<br></br>
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/98921972/2857860e-83ff-4e6d-a898-38df0862a260)

## Explain your evaluation and justification of how you decide the MTTFmin
We chose the value of MTTFmin to be 2.85 because that value is where the failure data is right on the boundary between the "Accept" and "Continue" regions. The MTTFmin value has to be at least 2.85 in order for the system to be considered as acceptable to be released and a lower value than that would indicate that the system would need more testing to make its MTTF greater.

## A discussion on the advantages and disadvantages of RDC
Stuff

# Comparison of Results
Stuff

# Discussion on Similarity and Differences of the Two Techniques
Stuff

# How the team work/effort was divided and managed
Stuff

# Difficulties encountered, challenges overcome, and lessons learned
Stuff

# Comments/feedback on the lab itself
Stevan Beljic:

Aaron Giang:

Angelo Troncone:

Rutvi Brahmbhatt:
