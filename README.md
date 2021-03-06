# Human-memory
A repository for computational models of human memory

I'm a beginner! Anyone who is at the similar level who wants to learn about
models for human memory is welcome to participate in this repo.
The goal is ultimately to just learn about the dynamics of connected neurons,
their learning rules, and how our minds work!

I'm also trying to focus on biologically feasible systems.

Projects are implemented in Javascript and Python.

Theory:
Most models of human memory involve categorization and classification, and the equations that achieve this simple traverse an error or fitness surface to find the respective max and min.

#####Running all the JS files:
Basically just download the git repo, and run the respective index.html files.


###1) Self organizing map/ Kohonen net (implemented in Javascript):

I would like to explore how neurons could exhibit this kind of activity with
biological constraints. For example, the kohonen net is based on comparative
error, and I'm not sure if neurons would ever be able to do such precise
calculations by only summing dendrite inputs.
I wonder if it would be possible to create a robust classifier using SDR's.

Basically a SOM works by creating a field of several different classification populations through competive training. (Note: by populations I mean blobs of similar weight vectors). They're very interesting, and I'm going to try to think of ways in which you could chain a bunch of SOM's and feature extractors together to compute a complex classification problem.
I've read in several places that these are the "ideal model for human memory", but I seriously doubt these nets are the entire story. They might be a PART of human memory, but I think the remarkable type diversity of memory circuits in the brain will surprise us. These nets at best probably just loosely model the classification and categorization modules of our minds.

Just writing this one down... Not sure how this idea is connected to any of these ideas but are a bunch of simple graded "yes/no" responses enough to  match the accuracy of a single backpropagated ideal solution?

###2) Hopfield net:
Bug's fixed! I wrote the original net under the assumption that online training was possible: which I now see is simply not true. So I'm a bit disappointed in the hopfield net as a model for neural function. It does illustrate how local connectivity and correlation would allow for biologically feasible pattern matching, which I guess is something. Hop.py should work if you run it like a standard python program, although not necessarily beautifully.
To run the hopfield server (JS client, and python Flask backend):  
   Dependencies:  
   * Flask
   * Numpy
Download, move to server directory, and run the command 'python server.py'.  
Next, open http://127.0.0.1:5000/  
Next feel free to train and run all the mofocking patterns you want.

Theory behind Hopfield Nets:
Minimization of an energy function through activity-correlation to create content-adressable memory.

Recurrent Systems:
* http://www.scholarpedia.org/article/Hopfield_network
* http://www.cs.toronto.edu/~mackay/itprnn/ps/506.522.pdf
* https://www.youtube.com/watch?v=gfPUWwBkXZY

###3)Python Neural net:
Object oriented approach to implementing a neural net. (Python)
Shit is slooooow.


###4) Deep Belief Networks: Stacked RBMS
Includes the RBM:
Most of the credit for this code goes to Edwin Chen,
https://github.com/echen/restricted-boltzmann-machines
Where I took a sizeable amount of the training code from.


Generative models
Probabilistic inference networks: infer the relationship between the hidden units that could creates the visible effect.  

Related Concepts:

 * RBMS (restricted boltzmann machines)
 * Sigmoid Belief Networks
 * Bayesian Networks
 * Autoencoders

https://deeplearning.net/tutorial/DBN.html
https://www.youtube.com/watch?v=vkb6AWYXZ5I
https://www.cs.toronto.edu/~hinton/nipstutorial/nipstut3.pdf

###5) Convolutional Nets:

A folder full of broken shit! What's more to love.

Convolutional nets are crazy: they're closest thing we've gotten to a general solution for complex problems. Still, they're difficult to understand, slow to train, and aren't even close to perfect.
I'll keep developing this folder over the next couple years and see where it goes. 

I use nolearn (built with lasagne and theano) and Caffe (bvlc vision).

There are scripts for nolearn networks and ipython notebooks for Caffe.

"Style project": Is based on this paper.
* http://arxiv.org/pdf/1508.06576v2.pdf


####6) Other shit to learn:
   Auto-encoder, (standard, variational), Recurrent neural nets, Recurrent-CNNs, Sparse distributed Representations, Deep-belief nets, Hopfield nets.

   Projects:
   * Cifar-10
   * Deep-art, style and content mixing

#### Considerations in creating a biologically accurate neural system:
Basically, the question is how do you create models with learning rules and units that are constrained in the same ways as biological neurons, that can still compute information.
Tis a mystery.
But here are some constraints. (And I'm sure we'll find more constraints the better biological imaging and activity reading technology gets)

   * Spiking
   * Different neurotransmitters corresponding to neuron types
   * Dales law (Ratio of inhibitory to excitatory cells [20/80])
   * Sparse coding
   * Refractory periods (Leaky integrate and fire)
   * Connectome structures: biological make up of the brain (backwards feeding, layers, ect.)
   * Synaptic modification (Neuronal activity shapes circuits by strengthening synapses, stabilizing dendritic spines, and stimulating dendritic growth and branching. These effects are mediated through increases in intracellular calcium levels, activation of kinases, and downstream changes in gene transcription.)
   * LTP, LTD, Spike-timing dependent plasticity.
   * Limited connectivity/receptive fields
   * Neuron structures and types
   * Local Learning rules vs larger scale fine-tuning learning (check machine learning vs reasoning)


How we can cheat to find our answers:
   * Look at neuron differentiation during development, see what does what
   * Repeating structures in brain? Is the brain broken up into functional units? (Other organ systems do it, does the brain as well?)
   * Raphe nucleas, islets of langerhans? Small isolated systems that perform important functions
   * Connectome (all the connections between brain regions), Dynome (The way they interact)
   * Larger scale recordings of ensembles of neurons (There's nothing like observation when it comes to creating behavioral rules)
   * Find proof of the existence of a universal code/learning rule? If there was one, it would simplify the problem of discovering the computational rules of each brain region.
   * Analyze species with simpler brains, (some rules we would find MUST be conserved over the course of evolution)


###Links to models of biological systems:

MIT initial object recognition in the visual cortex: (full model and implementation details)
http://cbcl.mit.edu/projects/cbcl/publications/ai-publications/2005/AIM-2005-036.pdf

Machine Learning vs Machine reasoning:
http://research.microsoft.com/pubs/192773/tr-2011-02-08.pdf

MIT Texture + object recognition:
http://cbcl.mit.edu/cbcl/publications/ps/unifiedC2.pdf

Orientation maps of the visual cortex:
http://www.scholarpedia.org/article/Visual_map#Orientation_Maps

Lateral occipital cortex and its role in object recognition:
http://math.bu.edu/people/horacio/tutorials/jascha_2.pdf

Visual perception of texture: (Something that I think will be incredibly important in the future of effective object segregation and recognition)
http://www.cns.nyu.edu/~msl/papers/landygraham02.pdf

Large scale model of the functioning brain (only the abstract)
http://www.sciencemag.org/content/338/6111/1202.short
