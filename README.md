# Model description:
**-Generator:**
<>input(64,100)
Dense(4*4*64*8,’linear’)
Reshape((64,4,4,64*8))
Conv2d_transpose(64*4, [4, 4], [2, 2])
relu_batch_norm
Conv2d_transpose(64*2, [4, 4], [2, 2])
relu_batch_norm
Conv2d_transpose(64, [4, 4], [2, 2])
relu_batch_norm
Conv2d_transpose(3, [4, 4], [2, 2])
tanh'''

**Discriminator:***
'''Conv2d(64, [4, 4], [2, 2])
leaky_relu
Conv2d(128, [4, 4], [2, 2])
leaky_relu_batch_norm
Conv2d(256, [4, 4], [2, 2])
leaky_relu_batch_norm
Conv2d(512, [4, 4], [2, 2])
Dense(1,’linear’)'''

# Experiment setting and observation:

# Compare to original GAN

# Training tips for improvement
