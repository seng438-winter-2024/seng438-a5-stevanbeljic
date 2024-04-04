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

### MTTFmin (2.85 Failures per second)
<br></br>
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/2e2c5ac2-c3dc-4a90-91ea-4fa2db9bbe65)
<br></br>
### 2 x MTTFmin (5.70 Failues per second)
<br></br>
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/844f9feb-723b-4f36-a42c-be03831e3c5c)
<br></br>
### 0.5 x MTTFmin (1.425 Failures per second)
<br></br>
![image](https://github.com/seng438-winter-2024/seng438-a5-stevanbeljic/assets/60798649/5c48fc1d-772a-4dee-bc70-1228e28cf50e)

## Explain your evaluation and justification of how you decide the MTTFmin
We chose the value of MTTFmin to be 2.85 because that value is where the failure data is right on the boundary between the "Accept" and "Continue" regions. The MTTFmin value has to be at least 2.85 in order for the system to be considered as acceptable to be released and a lower value than that would indicate that the system would need more testing to make its MTTF greater.

## A discussion on the advantages and disadvantages of RDC
Advantages
- Very clear visual depcition of whether the SUT meets the failure targets or not
- Allows for the considerations of multiple risk factors, such as customer risk or developer risk

Disadvantages
- Similar to reliability growth testing, relies on accurate data to be reported or reported at all
- The test uses complex statistical formulas to formulate its acceptance and rejection rate, therefore may provide a sense of false security as a tester may not truly understand the statistics at play in the computation and determination of acceptance

# Comparison of Results
For the SUT, the computed MTTF for the reliability growth testing was 6.58 failures per second, while using RDC it was 2.85 failures per second.

Reliability growth testing plotted failure data across time intervals, providing a more dynamic view of the system's reliability over a given time period. It allowed for the observation of trends and models that can predict future trends, indicating improvement in reliability if the trend line flattened out.

RDC gives a static view of the relaibility using the MTTFmin value as a comparison benchmark. The RDC value showed visually if the SUT's failure data fell within the acceptable range with the MTTFmin value as the threshold.

# Discussion on Similarity and Differences of the Two Techniques
Similarities
- The same system was being tested using both methods.
- Failure times and target failure rate (MTTF) are the foundation of both methods.
- Both methods used the same failure dataset as their input.

Differences
- RDC solely employs inter-failure times, whereas the reliability growth analysis technique, uses failure count in addition to inter-failure times.
- In order to create distinct graphs on the system's reliability, the two approaches used different interpretations of the data.

# How the team work/effort was divided and managed
Everything was done togehter, both parts 1 and 2, and notes were taken by others as one person conducted the work while sharing their screen with the rest of us. Screenshots were also taken during this call, and notes of their importance were made so that they could be used in the report later. Afterwards, we all seperately worked on the report, each taking sections as we got to them.

# Difficulties encountered, challenges overcome, and lessons learned
A big difficulty was encountered in getting some of the software to even work, such as SFRAT or CASRE which simply would not run or install for any of us. Once we did get some working, the documentation for them (such as C-SFRAT) was somewhat lacking, and it was difficult to learn how to produce certain plots or prediction trends. Nontheless, through trial and error, we were eventually able to complete the lab by using alternative softwares, and then playing around in them to get more understanding as to how to generate models, predictions, and model comparison charts.

# Comments/feedback on the lab itself
Stevan Beljic: This lab was very confusing and difficult to execute. A lot of the outlined software simply did not work for me, and if it did it was difficult to use because documentation was so poor. Instructions were also quite unclear 

Aaron Giang:

Angelo Troncone: I think the intention of this lab was very good; trying to get us to think about failure data and allowing us to experiment with different ways of transforming it to make conclusions about the reliability of a system. I did find however, that the instructions were vague; it was not clear as to how certain things had to be done in the provided software, leading to confusion and experimenting around with the programs and the input data formats. I also found the ammount of folders and data files to be very overwhelming; I think only having around 10 files, each with a different trend that would fit models differently would have been less confusing, and would have allowed us to more easily play around with the models.

Rutvi Brahmbhatt:
