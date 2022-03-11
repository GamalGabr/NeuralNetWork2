# NeuralNetWork2
Neural Networks Part 2

<h2>EQUATION TIME!</h2>
<br>
 






Here, we begin by obtaining the relevant derivatives in a backward fashion. In the neural network that we have constructed, we employ cross-entropy loss, aka log loss, to gauage the predictive performance of the neural network. The cross-entropy loss decreases as the predicted probability approaches the actual label/outcome. It is worth noting that for every case, it is exclusively the term for the correct class that influences the sum of the overall cost. The neural network designates a pseudo-probability to each potential category. Log loss captures the accuracy of the model by penalising incorrect classifications. Below, the log loss and softmax derivatives are evaluated.


![20220307_232408](https://user-images.githubusercontent.com/81494595/157572621-35831cbc-2fec-4aad-843e-40c0016f3819.jpg)

<br>

![20220224_105431](https://user-images.githubusercontent.com/81494595/157787880-90d50e9e-f89e-40e2-b7bc-6806425df7f5.jpg)

<br>

Below the tanh derivative is obtained
<br>
![20220311_023558](https://user-images.githubusercontent.com/81494595/157793227-7c7bdf6e-da40-4778-b491-dac26101a5cc.jpg)




![20220311_023558](https://user-images.githubusercontent.com/81494595/157793016-c7a568bd-dd4c-445e-8b38-2066f1e8b68c.jpg)





![20220308_002645](https://user-images.githubusercontent.com/81494595/157570388-5c1da4e8-aa5d-4fd4-b48c-f7d9e464f3b0.jpg)
