
In this material, I will try to answer two questions (1) what is RNN, and (2) how it works, using examples in natural language processing (NLP) and computer vision (CV).  

Other key points will be covered:

* What is the difference between RNN and classic neural networks?
* Why should I care about RNN?
* What is LSTM and GRU?
* How to train an RNN?
* Are there ready-to-use codes to try out your ideas?
* Where to learn the theory of RNN?
* Where is the famous "seq-2-seq" learning?
* ...

(Note: All pictures are from the Internet)

<br>

# What is Recurrent Neural Network (RNN)?
====

##### NN:

![NN](https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcQ7RVVfhDTEx3J1j0dIfLmjh4qNwUccj0ox-sPq1npgXqu33nRg =200x)

##### Deep NN
![DNN](https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcRD_V8HuVHE9jl5lU4mdZjGRN56DHlJ34PSLsssn0mXlAqUitAaXA =400x)

##### RNN
![RNN](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQaDTWwr2bFz4tb18hQ-UZL0eJvhFU8RJ7e-wKp60QgvsAR-cOK =100x)

##### Unfolding RNN
![unfold](http://colah.github.io/posts/2015-08-Understanding-LSTMs/img/RNN-unrolled.png =400x)

##### Deep RNN
![DRNN](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSOUWtwtMTYJv3WFtLcaUQ73kfXlSH9zZbPFLY8grjNv_63boOUmw =300x)

<br>

In short, RNN 

* takes a sequence of input (length>=1) 

* keep applying the **_same_** set of operations on each of the input aloing the sequence

* carry the **_intenal state_** to represent or **_remember_** the underlying patterns/relations/states in the sequence 
 
* generates a sequene of outputs (length>=1)

**Key feature**: shared parameters 

<br>
<br>


# How RNN works?
====

## LSTM: the actual RNN in practice

Due to the vanishing gradient problem, we use long short term memory (LSTM) units as the actuall RNN layer. 

(Vanishing gradient problem is an issue may cause RNN hard to train. For details, check this awesome [video](https://www.youtube.com/watch?v=56TYLaQN4N8).)

Understanding LSTM can help us understand:

* How to capture long-term dependency (i.e. the result at time step T depends on the input at time step T-k)
* The core mechanism of RNN
* How to intreprate "RNN knows when to remember and when to forget" 

Let's move to [this awesome blog](http://colah.github.io/posts/2015-08-Understanding-LSTMs/)



## Training: back propagation through time (BPTT)

*In terms of hardware acceleration, it is important to understand BPTT.*

The computation is RNN consists of two parts: forward pass and backward pass. In the forward pass, the computation is mostly + - x or memory operations. The heavy part is in the backward pass. We need to compute the difference between the output and target, and propagate the gradient all the way back to the beginning. (New cudnn library (v5) from nvidia claims 6x speedup in LSTM.)

Let's enjoy this nice [blog](https://medium.com/@aidangomez/let-s-do-this-f9b699de31d9#.5njju6koo).

## Dealing with input and output with variable length
<br>

Three key RNN architectures:

* Variable length to fixed length (Video Classification)
* Fixed length to variable length (Image Caption, RCNN)
* Variable length to variable length, i.e. seq-2-seq (Translation)

See Figure 10.9, 10.10, 10.12 in [GoogleBrian's book](http://www.deeplearningbook.org/). 

<br>

## Extension: BD-RNN and Grid-RNN
<br>
Bi-directional RNN: exploring the context from two directions

![bdrnn](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRDKQgYhuYaoDHdFLmzjzoH0CwQqQttIfdSDqiHIW21SlA2q-A6Mw =450x)

Grid-LSTM: Extra connections are added in the LSTM in order to further explore the context. [paper](https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcRf4Oz6jdUntrvF3WKiGMeOu7II00MnN3zefviOLTkb8swLB2Xk)

<br>

# Applications
====

Learn more application? Check out this awesome [list](https://github.com/kjw0612/awesome-rnn).


##### Extra Materials 
* [Batch Normalization in RNN](https://github.com/iassael/torch-bnlstm) 
* [Seq-2-Seq Learning](http://papers.nips.cc/paper/5346-information-based-learning-by-agents-in-unbounded-state-spaces)
* [Learning materials of RNN and LSTM](http://handong1587.github.io/deep_learning/2015/10/09/rnn-and-lstm.html)
* [Another nice blog for LSTM](https://medium.com/@shiyan/understanding-lstm-and-its-diagrams-37e2f46f1714#.m52rcngew)
* [Torch RNN package with lots of examples](https://github.com/Element-Research/rnn)