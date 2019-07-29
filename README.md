# Model description:
**-Generator:**
<br>input(64,100)
<br>Dense(4*4*64*8,’linear’)
<br>Reshape((64,4,4,64*8))
<br>Conv2d_transpose(64*4, [4, 4], [2, 2])
<br>relu_batch_norm
<br>Conv2d_transpose(64*2, [4, 4], [2, 2])
<br>relu_batch_norm
<br>Conv2d_transpose(64, [4, 4], [2, 2])
<br>relu_batch_norm
<br>Conv2d_transpose(3, [4, 4], [2, 2])
<br>tanh

**Discriminator:***
<br>Conv2d(64, [4, 4], [2, 2])
<br>leaky_relu
<br>Conv2d(128, [4, 4], [2, 2])
<br>leaky_relu_batch_norm
<br>Conv2d(256, [4, 4], [2, 2])
<br>leaky_relu_batch_norm
<br>Conv2d(512, [4, 4], [2, 2])
<br>Dense(1,’linear’)

# Experiment setting and observation:
***Experiment setting:***
<br>batch_size = 64
<br>iteration: 50000
***Observation:***
<br>batch_size不適合太大,會學到比較模糊的images,並且train
<br>超過100000iteration之後多樣性會下降.

# Compare to original GAN
<img src="https://github.com/r06922085/WGAN-GP/blob/master/GAN%20vs%20WGAN-GP.png" width="50%" height="50%">

# Training tips for improvement
<br>Tip 1: Normalize the inputs
<br>Tip 2: Batch_Norm
<br>Tip 3: A modified loss function
