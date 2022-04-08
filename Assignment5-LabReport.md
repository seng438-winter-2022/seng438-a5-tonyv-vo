**SENG 438- Software Testing, Reliability, and Quality**

**Lab. Report \#5 – Software Reliability Assessment**

| Group \#:       | G38  |
|-----------------|---|
| Student Names:  | Tony Vo, Chace Nielson, Chad Holst, Olisehemeka Chukwuma |

- [1 Introduction](#introduction)

- [2 Assessment Using Reliability Growth Testing](#assessment-using-reliability-growth-testing)

- [3 Assessment Using Reliability Demonstration Chart](#assessment-using-reliability-demonstration-chart)

- [4 Comparison of Results](#comparison-of-results)

- [5 Discussion on Similarity and Differences of the Two Techniques](#discussion-on-similarity-and-differences-of-the-two-techniques)

- [6 How the team work/effort was divided and managed](#how-the-team-workeffort-was-divided-and-managed)

- [7 Difficulties encountered, challenges overcome, and lessons learned](#difficulties-encountered-challenges-overcome-and-lessons-learned)

- [8 Comments/feedback on the lab itself](#commentsfeedback-on-the-lab-itself)

# Introduction
In this assignment, we were given failure data of a theoretical software system under test. The failure data is given in a comma-separated value (CSV) format, with five columns pertaining to each failure event: the time interval of the failure, the failure count, the execution time of the system measured in hours, the failure identification work measured in person-hours, and the computer time failure identification measured in hours. The objective of this assignment is to use two methods: reliability growth testing and reliability assessment using a Reliability Demonstration Chart (RDC) to analyze integration test data. 

To do so, we were also instructed to use several tools to perform the analysis: Covariate Software Failure and Reliability Assessment Tool (C-SFRAT), Computer-Aided Software Reliability Estimation (CASRE) tool, RDC-11, and SRTAT (a tool created by Dr. Far and his team). From these tools, we manipulated the failure dataset to ensure that the data is valid for the tools that we chose to use. From there, we were able to produce output by selecting and entering parameters, and consequently, use the results to interpret the data.
 
Before this assignment, none of our group members had any experience with software reliability testing. As such, this lab provided our group with several tools to understand the reliability of a theoretical software system using reliability growth testing and a RDC.

# Assessment Using Reliability Growth Testing 

### Result of range analysis (an explanation of which part of data is good for proceeding with the analysis)

We used the LaPlace test manually in Excel to find the useful data range of the dataset that had been provided:

![image](https://user-images.githubusercontent.com/8889264/162533357-e9a146fa-067e-4365-9437-a958169ce0d3.png)
Our results show that the data in between intervals 1-12 is within the useful data range. We know that the data is considered useful because such intervals have a LaPlace factor of -2 to +2 inclusive.

### Tools for Testing Reliability from the provided data: SRTAT
#### Time-Between-Failures

The time between failures was calculated using the failure data provided. It was calculated simply by subtracting the failure time of one fail from the failure time of the failure before.

![image](https://user-images.githubusercontent.com/8889264/162533434-d054f084-3fae-47ab-a230-4afd8d1cb78d.png)

### Failure Intensity Graphs
Geometric Model

![image](https://user-images.githubusercontent.com/8889264/162533840-b5c84c7f-7380-44d7-8408-931bd058a5c7.png)

Littlewood and Varral’s Bayesian Reliability (using MTBNF prediction)

![image](https://user-images.githubusercontent.com/8889264/162533873-bf96bb0a-7363-46aa-a5b0-550b3fefce0c.png)

The SRTAT method didn't have any functionality to produce reliability graphs.

The top two models used in SRTAT for failure intensity were the Geometric Model and the Littlewood and Varral’s Bayesian Reliability Model.

The two models above were chosen because they were the best fit for the data set of time between failures. They had the required functionality and worked with the SRTAT application. They were able to handle the provided failure data and produce the appropriate information for failure intensity.

While these graphs and charts show all the failure points the useful data is taken from points 1-12 as calculated from the Laplace tests.

### Tools for Testing Reliability from the provided data: Excel Data Method
#### Time Between Failures Graph

![image](https://user-images.githubusercontent.com/8889264/162534111-4e52c075-f22d-469b-ac91-221c07db8ea3.png)

![image](https://user-images.githubusercontent.com/8889264/162534079-d46f9b37-be15-4000-ab7f-07c708ebd1f9.png)

#### Failure Intensity

![image](https://user-images.githubusercontent.com/8889264/162534475-a329e9db-2de2-42d5-8daf-32a8f5b221fa.png)

#### Reliability 

![image](https://user-images.githubusercontent.com/8889264/162534566-3f5367eb-354b-4914-a38f-961b96190f79.png)

### Tools for Testing Reliability from the provided data: C-SFRAT

![image](https://user-images.githubusercontent.com/8889264/162534658-a36772e3-a49e-4c74-9146-479e7366e0fc.png)

#### Result of model comparison (selecting top two models):
The model with the highest Log-Likelihood is DW3 (F) followed by IFRGSB (E,F) using C-SFRAT.

![image](https://user-images.githubusercontent.com/8889264/162534740-0b1c4297-bd42-481d-a172-336914838821.png)

![image](https://user-images.githubusercontent.com/8889264/162534761-796b72a5-da1d-47d2-a81d-46adfae6b60b.png)

#### Model comparison for DW3(F) and IFRGSB (E,F)

![image](https://user-images.githubusercontent.com/8889264/162534804-a9e92233-254e-4ab8-bcd2-0f6a980dd3ee.png)

## A discussion on decision making given a target failure rate
As evidenced from the failure intesity graph above, the failure intensity shoots up early on. It also dips down after some time has passed. As time progressed, the failure intensity rate increased drastically. In the middle section of the data, the failure per hour does remain relatively stable. It would be a good idea to keep this time frame to have the best ratio between the failures per hour and the time as possible. Based off the failure intensity graph, we can conclude that our target failure rate is approximately 0.5 failures per hour.

## A discussion on the advantages and disadvantages of reliability growth analysis
#### Advantages of reliability growth analysis
- Measuring improvements is noticeable and can guide the decision-making process
- Provides a good amount of information to help make decisions in regards to if the software is considered acceptable
- Determines how much a product can be trusted or how reliable it is
- Provides visualization of the data to assist in analysis

#### Disadvantages of reliability growth analysis
- Difficult to understand and required lots of time and effort to fully understand
- Can be hard to find specific failures
- Can be a complex process and not provide the exact information you need if done poorly
- Only some ranges of data are considered useful for testing
- Requires additional tests such as LaPlace to find such useful data before the analysis stage

# Assessment Using Reliability Demonstration Chart 
### Original MTTFmin RDC
![image](https://user-images.githubusercontent.com/8889264/162535223-cdc440de-48ef-4679-9904-93405619e6f4.png)
![image](https://user-images.githubusercontent.com/8889264/162535229-fd609625-be03-46b7-a312-30bd87165a83.png)

### Half MTTFmin RDC
![image](https://user-images.githubusercontent.com/8889264/162535252-dc34d38b-90f0-4324-99cd-d5c00a28d2ea.png)
![image](https://user-images.githubusercontent.com/8889264/162535259-9da455e3-cefa-40a1-80fe-d4fcfc73af24.png)

### Twice MTTFmin RDC
![image](https://user-images.githubusercontent.com/8889264/162535273-70c3a772-6698-4c22-ba50-2af3176dfba7.png)
![image](https://user-images.githubusercontent.com/8889264/162535280-dcf41649-6066-4460-b6e1-a3f195d6a367.png)

### Explanation of evaluation and how the MTTFmin was decided
Observing our **original MTTFmin RDC**, we see that our MTTFmin is approximately 2.7 normalized MTTF considering this is where our plot crosses the Accept line. 

Next, analyzing our **half MTTFmin RDC**, we notice that our MTTFmin is approximately 5.2 normalized MTTF since this is where our plot crosses the Accept line. 

Lastly, our **twice MTTFmin RDC** shows that our MTTFmin is approximately 2.4 normalized MTTF as our this is where our plot crosses the Accept line.

## A discussion on the advantages and disadvantages of reliability growth analysis
#### Advantages of RDC
- Ideal for a system with a small number of failures
- Easy to read if the software requires further testing or not
- Provides visualization of the data to assist in analysis
- Beneficial as a supplementary tool with other tools being used

#### Disadvantages of RDC
- Limited to a small number of failures 
- Difficult to determine which confidence intervals/parameters should be used
- Data can be misleading if the parameters are not set properly

# Comparison of Results
The results for both the Reliability Demonstration Charts (RDC) and the Reliability Growth Testing (RGT) shared similar observations and had some differences.

The Reliability Demonstration Charts (RDC) gave more information regarding MTTFs, and we used that information to produce the relevant output. This provided a useful data set that would help in the decision-making process. We could use all the data for the tests but the particular tool we used only allowed us to use the first 5 data points. This methodology uses multiple MTTFs to provide a larger range of data to consider. This can lead to more information regarding reliability being available. We noticed that RDC seemed to be meant for having a smaller number of failures so this is why we decided to used the first 5 data points from the dataset provided.

The Reliability Growth Testing (RGT) had a focus on failure intensity. This gave a particularly interesting look at the data with respect to time. The RGT only had a smaller useful data range that could be used by the method. This could be seen as limiting as some data isn’t used, but it could also be seen as a more accurate representation of the results. Since the Laplace testing was first used to get a useful data range to increase the accuracy of the results. It only used a single MTTF which has a limited range of results. We noticed that RGT allowed for a large amount of failures to be analyzed but only some of the data should be analyzed which resulted in only using 12 data points.

RDC and RGT are only benefcial when used within their constraints in regards to the data and the data range. We can conclude that RDC is beneficial for a small amount of failures with any range of useful data; however, RGT is useful for a large amount of failures but only within a certain range of useful data. 

# Discussion on Similarity and Differences of the Two Techniques
Both techniques are based on inter failure times. However, the difference is that RDC is always also based on a target failure rate. Reliability growth analysis can be based on failure count and failure rate instead of just inter failure times. We learned that inter failure times are quite useful when evaluating the reliability of a SUT. 

RDT is used more for demonstrating the reliability of a product and performs at the system level. It usually is set up as a success test. RGT is used more in data collection and for factors from the field. It is used in collection, modelling, analysis and interpretation of data.

# How the team work/effort was divided and managed
In this assignment, each member of the group started off by learning how the tools worked and the specifications of the lab. After that, we worked as a team to understand and accomplish the rest of the lab's tasks. Although this lab appeared to be shorter than the previous labs, we had trouble accomplishing the goals given in the assignment document. We had two team members working on Part I, and another two team members working on Part II. Occasionally, we would switch responsibilities and work on other parts of the lab since we frequently ran into trouble with understanding the tools, data, and specifications of this lab.

# Difficulties encountered, challenges overcome, and lessons learned
Our main difficulty was in understanding how this lab's tools worked. We found it difficult to find documentation, so we had to manually manipulate the given data. The tools the lab used were very new to each member of the group so it required a lot of effort and time to begin to understand the components of the assignment. The tools were very challenging to use and took a lot of time to understand. The group was eventually able to learn how to use the tools and implement the solutions to the assignment problems after a considerable amount of time.

# Comments/feedback on the lab itself
The lab was difficult to understand. We felt it gave the basics of the material and left us to learn and understand what to do on our own. It would have been helpful to have more documentation or at least links to the documentation of the tools. Furthermore, we found it difficult to do the Laplace test. Although we found formulas online and in the slides, there were not many tools available online that would allow us to check our results to know if our Excel formula was correct. Once we were able to understand what the lab was asking us to do and also how the tools worked we were able to make some progress. Additionally, the dataset provided was only meant for one tool and some of the column labelling was not clear.

The lab provided some insight into using data to determine the reliability of a software under test. In doing this assignment, we learned that the field of Software Testing, Reliability, and Quality can be complicated and may require a multitude of tools to interpret the data. We were able to gain some insight as to how things might work in a professional environment.
