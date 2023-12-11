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

## Bias Neuron
- An extra neuron added to each layer
~~~
        // We have a new layer, now fill it with neurons, and
        // add a bias neuron in each layer.
        for (unsigned neuronNum = 0; neuronNum <= topology[layerNum]; ++neuronNum) {
            m_layers.back().push_back(Neuron(numOutputs, neuronNum));
            cout << "Made a Neuron!" << endl;
        }
~~~
- Has fixed output
value of 1.0
~~~
        // Force the bias node's output to 1.0 (it was the last neuron pushed in this layer):
        m_layers.back().back().setOutputVal(1.0);
~~~

## Smoothing the Activation

● Step function non-differentiable

● Apply a sigmoid function to smooth it out

~~~
double Neuron::transferFunction(double x)
{
    // tanh - output range [-1.0..1.0]

    return tanh(x);
}

double Neuron::transferFunctionDerivative(double x)
{
    // tanh derivative
    return 1.0 - x * x;
}
~~~
