# Sign-Alphabet-Classifier
In this repo,I'm going to show my few works on custom architectures instead of using already existing architectures like resnet or alexnet and build and train them from scratch.
.
The dataset i'm using is ALS(American Sign Language)-2019.

American Sign Language is the Language used by the Deaf Community,though its not universal but its used almost everywhere

![NIDCD-ASL-hands-2019](https://user-images.githubusercontent.com/47039231/75981172-f2bc6a00-5f09-11ea-94d6-15aa50f56980.jpg)


In the notebook you can see Two Approaches

1.Custom CNN

2.Seperable CNN

Custom CNN has :

![image](https://user-images.githubusercontent.com/47039231/75982682-277df080-5f0d-11ea-8e33-17d1d537964a.png)
 
 Fairly Simple Architecture But the Results it produced are Amazing!
 
 Results On Training Set
 ![image](https://user-images.githubusercontent.com/47039231/75982778-572cf880-5f0d-11ea-9274-b88884869d18.png)
 
 Evaluation Accuracy on Seperate Test Set : 99.33%
 
 Prediciton on Seperate Test Set
 ![image](https://user-images.githubusercontent.com/47039231/75981677-00262400-5f0b-11ea-9001-9be000f9119e.png)
 
 Accuracy and Loss vs Epoch Plot
 
 ![image](https://user-images.githubusercontent.com/47039231/75981536-b76e6b00-5f0a-11ea-868b-3fd57a753949.png)
 
 2.Seperable CNN
 Architecture:
 ![image](https://user-images.githubusercontent.com/47039231/75981941-90fcff80-5f0b-11ea-8299-79b68da05ee3.png)
 ![image](https://user-images.githubusercontent.com/47039231/75982010-ad993780-5f0b-11ea-9419-277c46becdc1.png)
 Perhaps a bit deep(no pun intended),also notice it has identity connection similar to resnet this is to not loose much features due to downsampling and also it is equipped with Seperable Convolution layer which makes the computations less memory intensive an added benefit of Seperable Convolutions
 ![image](https://user-images.githubusercontent.com/47039231/75982564-f0a7da80-5f0c-11ea-8a7c-84636d92422f.png)
 
 I did try few modifications in Seperable CNN Some of them gave terrible results(Overfitting)
 <img width="916" alt="overfit" src="https://user-images.githubusercontent.com/47039231/75983162-01a51b80-5f0e-11ea-8b63-e9ee2095f047.PNG">

Conclusion we can draw here is sometimes simpler CNN can prouce similar results infact better(sometimes) compared to a complex deeper model,also it depends on the dataset you are working,there are datasets and problems where features are of more importance in which second architecture might perform better,but in the current problem **Custom CNN** performs a bit better. 
 
 You can through the code and play with it 
 https://colab.research.google.com/drive/1N2NVX3UU1QD06KB29cgTnvb7Ye8sEq0Z
 
**Downloaing Kaggle Dataset into Colab**

Copy this code into Colab Notebook

import os

os.environ['KAGGLE_USERNAME'] = "xxxxxx" # username from the json file

os.environ['KAGGLE_KEY'] = "xxxxxxxxxxxxxxxxxxxxxxxxxxxx" # key from the json file

!kaggle datasets download -d iarunava/happy-house-dataset(url of your dataset) # api copied from kaggle


API File will be available inside Account settings 

 ***Links***
 
 1.Introuction to Seperable Convolutions https://towardsdatascience.com/a-basic-introduction-to-separable-convolutions-b99ec3102728
 
 2.Google Colab https://colab.research.google.com/
