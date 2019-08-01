# Overview
This is my attempt to reproduce and extend the results in the paper "An Introduction to Deep Learning for the Physical Layer" by Tim O'Shea and Jakob Hoydis. Available at https://doi.org/10.1109/TCCN.2017.2758370

There is also and attempt to use the autoencoder for simultaneous information and power transfer, based on the paper "A Learning Approach to Wireless Information and Power Transfer Signal And System Design" by Morteza Varasteh, Enrico Piovano, and Bruno Clerckx. Available at https://doi.org/10.1109/ICASSP.2019.8682485

Another very useful paper on this topic is "Deep Learning-Based Communication Over the Air" By Sebastian Dorner, Sebastian Cammerer, Jakob Hoydis, and Stephan ten Brink. It covers more complicated implementations for more realistic channels.

The implementation uses Keras with a Tensorflow backend on Jupyter Notebook. The paper from O'Shea and Hoydis covers multiple applications for using an autoencoder to replace the physical layer in a wireless communication system. I have searched and only found code for the most basic example, which implements a Gaussian Channel, but for the three more complex applications there is nothing. Therefore I am reproducing the results myself. Currently I have only reproduced the results for the Gaussian Channel. The end goal for this is to implement the trained encoder and decoder in real-time using GNU Radio and the gr-tflite module (which I am planning on writing).

# Autoencoder for Gaussian Channel
This creates an autoencoder which finds the optimal modulating technique for robust communication over a white gaussian noise channel (the simplest of channels). The Block Error Rate of the communication through varying Signal to Noise Ratios is analyzed by varying the magnitude of added noise. The trained autoencoder successfully transmits the signal with performance comparable to other 

# Autoencoder for Reyleigh Channel
This Attempts to implement an autencoder with similar structure the the previous Gaussian Channel to a Reyleigh Channel. Currently, only a single tap Reyleigh Channel has been implemented, and is currently not effective.

# Autoencoder for Reyleigh Channel with RTN
This is an improvement to the decoder portion of the autoencoder by including a RTN which predicts the channel taps and then performs a convolution using the recieved signal and predicted channel taps. In the paper "An Introduction to Deep Learning for the Physical Layer" this technique significantly improved the Block Error Rate of the system, but I have been unable to reproduce these results.

# SISO for Simultaneous Info and Power Transfer
This is another interesting application of autoencoders to the physical layer. This attempt only uses a Gaussian Channel, and I have run into problems because the loss function used in the paper incorporates a modified bessel function of the first kind and zero order. Incorporating only the bessel function causes the loss to return as NaN because the bessel function returns extremely large numbers. Currently the code implements the natural log of the bessel function to avoid this, but I must do more reading to understand the purpose of this bessel function, because currently my calculations of recieved power do not match the recieved power presented in the paper.

# License
This code is licensed under the MIT Open Source License.
