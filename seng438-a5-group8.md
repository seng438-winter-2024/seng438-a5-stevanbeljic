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
- Truncated Logistic<br><br>

The failure data we used was ```DATASET4.DAT``` within the failure count reports. The original failure and model reliability plot is demonstrated in the chart below, plotting all 8 models atop our failure data.
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/feb198a3-9f28-4592-b20b-6a0582666951)
<br>
<br>


Using the model comparison tab, we determined the two strongest/most accurate models were S distribution (S) and Negative Binomial Order 2 (NB2) because those two models have the highest Critic values (with values of 1.000), meaning they match up most accurately with the failure data provided. Purely from a visual perspective as well, the two plots of S and NB2 match the data set 4 failure data more accurately than any other model.<br>
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/79d9d5bb-7e80-4eb5-96f7-c3dfa116c9e9)
<br>
And the plots of the two most representative models (S and NB2), along with the original failure plot, are demonstrated below.<br>
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/fde201fc-fd6b-40ea-8e72-0e101b9ec4f7)

## Result of range analysis (an explanation of which part of data is good for proceeding with the analysis)
The range of useful data was selected visually, since SRTAT nor CASRE would work for us. Nontheless, we determined the subset of useable range for the data to be the entire data itself, since there were no significant outlying points and the failure growth rate seemed to follow a consistent trend of slowly tapering off with increasing time intervals. This is evidenced in the plot provided below.<br>
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/d430e306-fc89-4e6a-983f-fb056fa9f277)<br>
<br>
As can be seen here, the plots begin to even out at ~interval 45, which is 13 time intervals predicted. Since there are our two most accurate models and they follow a similar trendline, we deduced that including all time intervals (0-32) was an accurate range to proceed with.

## Plots for failure rate and reliability of the SUT for the test data provided

### Reliability Graph
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/4abd619c-559c-43a3-96b0-6c62fe81b9d7)<br>

### MVF Graph
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/ca3ffcdc-f355-40c9-841f-630442df474b)<br>

### Failure Intensity Graph
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/9a2cb6a2-269e-4b9b-bf13-b15c149a3e83)<br>


## A discussion on decision making given a target failure rate
A target failure rate is given by the formula MTTF (mean time to failure) = total operating time / total number of failures. Given we have 32 time intervals, and at time 32 we experience 211 failures, the MTTF can be deduced to be 32/211, or 0.152, meaning we should experience a failure every 0.152 time intervals, or 6.58 failures per time interval. This lines up fairly well with the failure intensity target used in the intensity graph of the previous section. 

## A discussion on the advantages and disadvantages of reliability growth analysis
Advantages:
- Helps bring logic to failure data by defining the amount randomness behind reported data, and if it can be modelled to follow any trends
- Informs decision making by allowing the predicition of future trends, both through model predictions and by analysis of past trends

Disadvantages:
- It is dependent on failure data being accurate, or even reported at all
- It is a very complex and difficult to understand process, so its results may not be fruitful without the necessary background knowledge to understand what the models are depicting

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
