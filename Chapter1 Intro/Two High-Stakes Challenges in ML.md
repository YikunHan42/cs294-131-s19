# Two High-Stakes Challenges in ML

Conference: ICML 2015

## Machine Learning in 2015

+ Increased ambitions
+ Challenges of a new kind
  + ML disrupts software engineering
    + Challenging our impact on real world applications
  + Our experimental paradigm is reaching its limits
    + Challenging the speed of our scientific progress

## Machine Learning disrupts software engineering

[Leaky Abstraction](https://en.wikipedia.org/wiki/Leaky_abstraction)

**The closer to logic, the more complex the artifacts**

###  Programming VS Learning

Programming

![image-20221228024104692](.\5.png)

Learning

![image-20221228024314277](.\6.png)



Image distribution matters

![image-20221228024547250](.\7.png)



### Examples

Click curves(Feedback loops):

![image-20221228024657410](.\8.png)
$$
P(click|context,item,pos)=F(pos)*G(context,item)
$$
Why separating position effect and item effect?

1. Sort items by clickability and allocate them greedily to the best positions(greedy placement algorithm)
2. Easy ways to estimate F and G

How bad things can go?

false click probability -> 0.7 0.3

Positive Feedback for C1:

![image-20221228030105503](.\9.png)

![image-20221228030822742](.\10.png)

Exploration Issue: 

New items eligible for context C1 may have a hard time competing with the current winner



Negative Feedback for C2:

![image-20221228031445548](.\11.png)

Expensive Oscillator:

+ Items alternate positions whenever retrain
+ Damping leads to the same problem as in C1



Team work(Game theory/Complex Systems/Interaction?):

![image-20221228031809726](.\12.png)

![image-20221228032037121](.\13.png)

All the exploration items are displayed with a very small font -> They receive less clicks



Red team in response:

![image-20221228032128315](.\14.png)

None of this is true!



All of them do their best job -> a bad outcome

![image-20221228032312472](.\15.png)

### Conclusion

+ Use trained models(example 1)
  + problematic because trained models offer weak contracts
+ Use learning algorithms as software modules(example 2)
  + problematic because the output of the learning algorithm depends on the training data which itself depends on every other module

## Our experimental paradigm is reaching its limits

ML as an exact science(like mathematics) or an empirical science(like physics)?

### Essential epistemology

![image-20221228193702056](.\16.png)

![image-20221228193804248](.\17.png)

![image-20221228193822522](.\18.png)

![image-20221228193843066](.\19.png)

Don't mix genres

![image-20221228193929312](.\20.png)





ML as an experimental science:

![image-20221228194015993](.\21.png)



Improve the performance of a ML application:

1. get better data
2. get better features
3. get better algorithm



**Training/testing on biased datasets gives unrealistic results**



Increased ambitions: Big Data

+ Too much data for manual curation
  + Exists because collection is automated
  + Nobody checks the data distribution matches the operational conditions of the system
  + All large scale datasets are biased

### Concepts Not Equals to Statistics

Put one's hands in pockets?

![image-20221228195009261](.\22.png)

**Discrepancy between the concept(recognizing the car) and the statistical reality**

![image-20221228195129245](.\23.png)



![image-20221228195250702](.\24.png)

![image-20221228195318288](.\25.png)

### Conclusion

+ Training/testing is an usually convenient experimental paradigm
  + it makes experimentation easier than in other sciences
  + it has played a role in the fast progress of ML
+ but may not fulfil our increased ambition(big data, AI.)
  + the end of an anomaly?



## Elements of a solution

### Process challenges

**Focus change: best performance -> reproducibility**



Scientific process

+ We cannot **solely** rely on training/testing experiments

+ We cannot understand more things with ad hoc experiments

A constructive proposition

+ ML learning papers rarely show the limits of their approach
+ Reviewers should instated demand that authors discuss their limits

### ML with stronger contracts

How to better resist distribution shifts?

+ Optimize measure of coverage instead of average accuracy

+ Very interesting properties when the data is [Zipf distributed](https://mathworld.wolfram.com/ZipfDistribution.html)

![image-20221228200715379](.\26.png)

![image-20221228201814803](.\27.png)

[Diminishing returns](https://en.wikipedia.org/wiki/Diminishing_returns)

### How to package the work of others

Digital computers: "software"

Learning machines:

+ Trained module as a software component?
  + × Trained components only offer "weak contracts"
+ Training software?
  + √ If you can get the training data and replicate the rig(AlexNet)
+ Task specific trained features
  + √ Nearly as good



![image-20221228202246237](.\28.png)

## Conclusion

Two process challenges:

 + Machine learning disrupts software engineering
   + Challenging our impact on real world applications
 + Our experimental paradigm is reaching its limits
   + Challenging the speed of our scientific progress