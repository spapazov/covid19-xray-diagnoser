# covid19-xray-diagnoser
This project leverages computer vision and convolutional neural networks to diagnose COVID-19 patients based on X-Ray scans of their lungs with the hope of providing alternative ways to achieve rapid widespread testing

While there have been massive developments in wealthier nations to provide cheap widespread testing- this has certainly not been a universal privilege around the world. For example, countries like Maynmar and Senegal have each performed under 10,000 COVID tests as of May 1st (~0.06% of population). This is miniscule in comparison the countries like the US who have the funding to conduct around 6 million tests leading up to that day (~1.8% of population).

With this in mind, I wanted to use this project as an opportunity to explore alternative testing methods, namely using X-ray scans to diagnose COIVD-19 carriers, in order to make testing more accessible in countries with smaller budgets and less developed infrastructures.

## Background

A convolutional neural network (CNN) is an adaptation of a regular neural network which adds a feature extraction layer. This feature extraction layer compromised of convolutional filters, which are learned from the training data set. In addition to the feature extraction, an activation function, pooling layer and normalization layer is applied before the final feature map of an input image is formed. Here is a visual representation of the above process:

![image](https://miro.medium.com/max/2000/1*vkQ0hXDaQv57sALXAJquxA.jpeg)

In order to compute the optimal weights of the convolutional and fully connected layers, the idea of gradient decent is applied wherein incremental steps are taken to minimize a loss function. Thus, given a loss function ![formula](https://render.githubusercontent.com/render/math?math=L(H[X],y)) where ![formula](https://render.githubusercontent.com/render/math?math=H[X]) is the output function of the final layer and ![formula](https://render.githubusercontent.com/render/math?math=y) is the true labels of the training data we can define the updates to the weights ![formula](https://render.githubusercontent.com/render/math?math=W_t) at layer ![formula](https://render.githubusercontent.com/render/math?math=t) as:

![formula](https://render.githubusercontent.com/render/math?math=\Large%20W_{t%2B1}=W_t-\alpha\frac{\partial{L(H[X],y)}}{\partial{W_t}},\alpha%20\in%20\mathbb{R})

Intuitively this essentially means that we are taking small incremental steps to minimizing the loss function, by updating each layer's weights. Updates to the weights stop when a local minima of the loss function is reached (ie. the weights converge).

## Results & Model

The model achieved an overall accuracy of 85% on the validation set which was very promising! In addition it had a precision of 87% and a recall of 98% when identifying X-Rays of COVID-19 carriers which supported the notion that the model yields valuable testing insights.

The main evaluation point was the notion that the model is only potent in identifying COVID-19 carriers when a patient starts exhibiting lung symptoms. This can greatly inhibit it from becoming a mainstream testing assistant as it will struggle to correctly identify carriers who are at an early stage of the virus' cycle.

For more information and analysis feel free to check out the Jypter notebook of the project- it includes all good, graphs, datasets, analysis and more!

# Next Steps

A great further sphere of investigation would be to use the said X-Ray scans to predict patients' likelihood to survive the virus. With this medical professionals can better direct their care to minimize deaths.
