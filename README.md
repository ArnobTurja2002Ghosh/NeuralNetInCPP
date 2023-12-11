# NeuralNetInCPP

The code is stolen from David Miller.

## Training a Neural Network

- Given input data and known outputs
  ~~~
        if (trainData.getNextInputs(inputVals) != topology[0]) {
            break;
        }
        showVectorVals(": Inputs:", inputVals);
  ~~~
- Running inputs through the network gives us a
calculated value 𝑦 = 𝑓( 𝑥, 𝑤, 𝑡 ) (feed forward)
~~~
myNet.feedForward(inputVals);
~~~
- Training a neural network involves tuning the
weights/thresholds until the values we get out of
the network match our training data
~~~
myNet.backProp(targetVals);
~~~
- A neural network is a function approximator
