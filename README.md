# Building a neural network from scratch



I wanted to set myself the challenge of building a neural network from scratch, depending solely on base R . I think the best way to fully get to grips with an algorithm is to code it from the ground up - one is left with little wiggle room for winging it. Moreover, I wanted to tackle the well-known MNIST (“Modified National Institute of Standards and Technology”) digit classification problem. The dataset is a collection of handwritten digits: with each row representing a single digit, and each column representing a 0-255 grey scale pixel. I kept asking myself the question, could I design a neural network algorithm to achieve an accuracy of at least 90% accuracy in the field of simple digit recognition? I am pleased to report that the algorithm worked wonders! After finally managing to get it fully operational, and subsequent training, the time came for it to be trialled on the validation set : it scored just shy of 90% in terms of overall accuracy. In terms of specificity metrics, the digit 5 proved to be the hardest to detect (sensitivity: 72.5%), whereas the 0 digit was detected over 97% of the time. In terms of the sensitivity metric, the classifier scored between 85-97% for the other digits. The specificity results showed that the most commonly incorrectly predicted digit was 8 (
specificity: 95.6% ) . I did not spend long experimenting with differing parameters. 

For the vast majority of the project, I found myself scribbling away with good old fashioned pen and paper - obtaining the key derivatives was by far the trickiest aspect of the process!  The project ended up as a two-part series on how to construct a neural network from scratch. Part 1 contains the bulk of the project, it is
rendered as an RMarkdown document and features all of the R code I used to build the neural network. If you would like to see the first part, click [here](https://rpubs.com/IsaacGabr/877855).  Below, I feature the second part of the project - in this part of the project, I detail the process of obtaining the key derivatives recruited by the neural network.



<h2>EQUATION TIME!</h2>
<br/>




<br/>
<h2/>Part 2 - How to obtain the correct derivatives</h2>
<br/>
Firstly, a reminder of the feedforward phase for a small neural that I introduced in part 1:

<br/>
<br/>

![20220307_233706](https://user-images.githubusercontent.com/81494595/158276088-a4db7337-0413-4ea4-b7c9-43738345989f.jpg)

<br/>



Below, the local gradients required for calculating the cost in relation to the first group of weights is displayed:

<br/>

![20220312_181349](https://user-images.githubusercontent.com/81494595/158041789-feaa74d8-0a9b-4684-a00b-cd53af4e6a1a.jpg)


Here, we begin by obtaining the relevant derivatives in a backward fashion. In the neural network that we have constructed, we employ cross-entropy loss, aka log loss, to gauge the predictive performance of the neural network. The cross-entropy loss decreases as the predicted probability approaches the actual label/outcome. It is worth noting that for every case, it is exclusively the term for the correct class that influences the sum of the overall cost. The neural network designates a pseudo-probability to each potential category. Log loss captures the accuracy of the model by penalising incorrect classifications. Below, the log loss and softmax derivatives are evaluated.



<br/>


![20220307_232408](https://user-images.githubusercontent.com/81494595/157572621-35831cbc-2fec-4aad-843e-40c0016f3819.jpg)

<br/>

![20220224_105431](https://user-images.githubusercontent.com/81494595/157787880-90d50e9e-f89e-40e2-b7bc-6806425df7f5.jpg)


<br/>


![20220312_181532](https://user-images.githubusercontent.com/81494595/158041887-982a243c-055a-4d43-8c2d-1cabb6e09332.jpg)



<br>


We are now in a position to calculate C/Z2


<br>


![20220312_174820](https://user-images.githubusercontent.com/81494595/158042022-a000b0fd-8a22-4f53-a220-9c2cf655dabe.jpg)



<br>




<br>



![20220312_170407](https://user-images.githubusercontent.com/81494595/158028310-6b19d665-b220-43e7-97fc-a6eb0d348c77.jpg)



<br>



After evaluation, the derivative collapses into this beautifully simplistic form - this derivation can be extended to a Softmax activation output with any number of classes.


<br>


![20220312_170535](https://user-images.githubusercontent.com/81494595/158028394-e2182fbc-ffe4-42ab-9e14-e4dab87e3b2b.jpg)


<br>



Here, C/W2 is evaluated:


<br>


![20220307_232819](https://user-images.githubusercontent.com/81494595/158026234-57b83e42-b2f4-46b1-a4f3-9c2e7653ad26.jpg)


<br>




![20220311_023456 (1)](https://user-images.githubusercontent.com/81494595/158026835-cc77f932-4cdb-4ce7-a13a-c950c448ad8f.jpg)






<br>




Below, the derivative of <span style ="color: green ; ">tanh</span> is evaluated



<br>



![20220301_104921](https://user-images.githubusercontent.com/81494595/157793955-e9401715-078d-4249-811e-58e914694541.jpg)



<br>



![20220311_023558](https://user-images.githubusercontent.com/81494595/157793227-7c7bdf6e-da40-4778-b491-dac26101a5cc.jpg)



<br>



We, can now find the A1/Z1 derivative.



<br>



![20220311_022758](https://user-images.githubusercontent.com/81494595/157794420-854d4f6b-b6c1-4c3d-84a7-84e33a5243e2.jpg)



<br>



<h3>Regularised Loss</h3>


<br>

The derivative of the sum of two terms is quite simply the sum of the derivatives of the two terms - hence, the derivative of the weight penalty is simply added to the main (log loss) error function.


<br>



![20220311_023322](https://user-images.githubusercontent.com/81494595/157794893-185a49da-f2db-416a-b540-50e72d5d69f8.jpg)



<br>

Below, I display the equations for the gradient descent update, firstly without regularization, and then with regularization.



<br>

![image](https://user-images.githubusercontent.com/81494595/157795089-e6ad1fda-2883-4f69-8e82-a0583b1c7b15.png)



<br>


![image](https://user-images.githubusercontent.com/81494595/157795288-3f823ae6-ef9e-4354-90dd-05bc912bf1fc.png)



<br>

In the equations I have just formulated, I have derived the equations for the derivatives of a single input/example. It is a trifle to extend this to a batch of samples, the appropriate weight updates will simply translate as the average of the updates that are evaluated for each individual example. The other derivatives can be found in a similar fashion.

