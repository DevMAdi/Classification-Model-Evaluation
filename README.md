### 	False positive & False negative
False positive- an outcome where the model incorrectly predicts the positive class. When a data point is classified as a negative example(say class 0) but it is actually a positive example(belongs to class 1). 

    Type 1 error

False negative- an outcome where the model incorrectly predicts the negative class. When a data point is classified as a positive example(say class 1) but it is actually a negative example(belongs to class 0).

> Type 2 error

"False negative is **dangerous**/ slight more imp. then false positive"
example In medical testing:
> false positive- indicates presence of a disease as result is positive, when in reality it is not present, 
> false negative- indicates no presence of a condition as result is negative, when in reality it is present. 

# 	Confusion Matrix
Confusion matrix - table to describe the performance of a classification model / classifier on a set of test data for which the true values are known. It allows the visualization of the performance of an algorithm.
![enter image description here](https://github.com/DevMAdi/Classkification-Model-Evaluation/blob/master/Screenshot%20%282664%29.png?raw=true)
			
			  true 		|	false
			negative	|  positive
		-----------------------------
			  false		|	true
			negative	|  positive

in above example
tn= 35, fp= 5, fn= 10, tp= 50
> from here we calculate 2 rates
	
	Accuracy Rate 	= correct/total 	= (50+35)/199= 85%
	Error Rate 		= wrong/total 		= (5+10)/100= 15%

# 	Accuracy Paradox
Paradoxical finding that accuracy is not a good metric for predictive models when classifying in predictive analytics. This is because a simple model may have a high level of accuracy but be too crude to be useful. Precision and recall are better measures in such cases.
eg. 
let tn= 9700, fp= 150, fn= 50, tp= 100

    Accuracy Rate= 9800/10000= 98%

now let's say that from now on our prediction will always be zero
in that case= tn= 9850, fp= 0, fn= 150, tp= 0

    Accuracy Rate= 9850/10000= 98.5%

Even Though accuracy increase, this is not good logic.

# 	CAP Curve
**check this out later:**
https://www.geeksforgeeks.org/python-cap-cumulative-accuracy-profile-analysis/
https://analyticsindiamag.com/cumulative-accuracy-profile-cap-curve-analysis-classification-prediction/

**Cumulative accuracy profile (CAP)** in data science use to visualize discriminative power of a model. The CAP of a model represents the cumulative number of positive outcomes along the y-axis versus the corresponding cumulative number of a classifying parameter along the x-axis.
![enter image description here](https://github.com/DevMAdi/Classkification-Model-Evaluation/blob/master/Screenshot%20%282665%29.png?raw=true)
blue line- sending emails to random peoples
red line- targeting specific cust. using param. like age, gender, geographics etc & then sending them emails & plotting who buy product.
green line- like red line but inefficient
crystal ball- ideal case(we know exact who will buy & send only them)

more the area between blue line & new modal line- better the CAP

**Note:**
Cumulative accuracy profile (CAP) not equal to Reciever Operating characteristic(ROC)

# 	CAP Curve analysis
close to crystal ball- better
close to blue line- worse

    							area btn ideal line & blue line
    Accuracy Ratio(AR)= 	  ------------------------------------
    							 area btn red line & blue line

close AR to one, the better

finding area is hard, visual way:
![enter image description here](https://github.com/DevMAdi/Classkification-Model-Evaluation/blob/master/Screenshot%20%282666%29.png?raw=true)
if 90% < X < 100% 
	could be **over fitting**
	one of independent. var is **post factum var**.- i.e it should not be in data as it's looking into future.
	Client who gave this data forget to take it out.
	Thus check for post factum or forward looking var. & over fitting

> Overfitting- models the training data too well. 
> Overfitting happens when a model learns the detail and noise in the training data to the extent that it negatively impacts the performance of the model on new data.
