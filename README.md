# NeuralNetWork2
Neural Networks Part 2

<h2>EQUATION TIME!</h2>
<br>
 






Here, we begin by obtaining the relevant derivatives in a backward fashion. In the neural network that we have constructed, we employ cross-entropy loss, aka log loss, to gauage the predictive performance of the neural network. The cross-entropy loss decreases as the predicted probability approaches the actual label/outcome. It is worth noting that for every case, it is exclusively the term for the correct class that influences the sum of the overall cost. The neural network designates a pseudo-probability to each potential category. Log loss captures the accuracy of the model by penalising incorrect classifications. Below, the log loss and softmax derivatives are evaluated.


<br>


![20220307_232408](https://user-images.githubusercontent.com/81494595/157572621-35831cbc-2fec-4aad-843e-40c0016f3819.jpg)

<br>

![20220224_105431](https://user-images.githubusercontent.com/81494595/157787880-90d50e9e-f89e-40e2-b7bc-6806425df7f5.jpg)


<br>


![20220226_225023](https://user-images.githubusercontent.com/81494595/158026624-7b3c577a-19d4-43ce-bb0f-fba8841c420d.jpg)




<br>

![20220227_214238](https://user-images.githubusercontent.com/81494595/158026455-81c7c168-77d0-478c-a21a-28561bf6871d.jpg)



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

![20220311_023322](https://user-images.githubusercontent.com/81494595/157794893-185a49da-f2db-416a-b540-50e72d5d69f8.jpg)

< br>

![image](https://user-images.githubusercontent.com/81494595/157795089-e6ad1fda-2883-4f69-8e82-a0583b1c7b15.png)

<br>

![image](https://user-images.githubusercontent.com/81494595/157795288-3f823ae6-ef9e-4354-90dd-05bc912bf1fc.png)

<br>

Here, C/W2 is evaluated:

<br>

![20220307_232819](https://user-images.githubusercontent.com/81494595/158026234-57b83e42-b2f4-46b1-a4f3-9c2e7653ad26.jpg)


<br>

![20220308_002645](https://user-images.githubusercontent.com/81494595/157570388-5c1da4e8-aa5d-4fd4-b48c-f7d9e464f3b0.jpg)

<br>

In the equations I have just formulated, I have derived the equations for the derivatives of a single input/example. It is a trifle to extend this to a batch of samples, the appropriate weight updates will translate as simply the average of the updates that are evaluated for each individual example. The other derivatives can be found in a similar fashion

