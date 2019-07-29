# autoencoder_for_physical_layer
This is my attempt to reproduce the results in the paper "An Introduction to Deep Learning for the PHysical Layer" by Tim O'Shea and Jakob Hoydis. Available at https://doi.org/10.1109/TCCN.2017.2758370

The implementation uses Keras with a Tensorflow backend on Jupyter Notebook. The paper covers multiple applications for using an autoencoder to replace the physical layer in a wireless communication system. I have looked around and only been able to find code for the most basic example, which implements a Gaussian Channel, but for the three more complex applications there is nothing. Therefore I decided to try to reproduce it myself. Currently I have only reproduced the results for the Gaussian Channel, but I am planning on continuing my work when time permits. The end goal for this is to implement the trained encoder and decoder in real-time using GNU Radio and the gr-tflite module.

# License
This code is licensed under the MIT Open Source License.
