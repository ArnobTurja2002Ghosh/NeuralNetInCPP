# NeuralNetInCPP

## Training a Neural Network

<ul>
  <li>Given input data and known outputs</li>
  ~~~
  if (trainData.getNextInputs(inputVals) != topology[0]) {
            break;
        }
        showVectorVals(": Inputs:", inputVals);
  ~~~
  <li>Running inputs through the network gives us a
calculated value 𝑦 = 𝑓( 𝑥, 𝑤, 𝑡 ) (feed forward)</li>
  <li>Training a neural network involves tuning the
weights/thresholds until the values we get out of
the network match our training data</li>
  <li>A neural network is a function approximator</li>
</ul>
