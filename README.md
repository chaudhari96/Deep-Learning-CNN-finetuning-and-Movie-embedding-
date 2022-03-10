# Deep-Learning-CNN-finetuning-and-Movie-embedding-

1. **Download the CIFAR 10 dataset**. Use the pretrained Resnet18 model (from trochvision) to extract features. Use the features as inputs in a new multi-class     logistic regression model (use nn.Linear/ nn.Module to define your model)
   PART A : Describe any choices made and report test performance.
   PART B: Display the top 5 correct predictions and the top 5 incorrect predictions in each class (show the images and the prediction labels) compactly.
   PART C: Finetune the Resnet18 model's parameters suitably and repeat parts (a) and (b) from
           above. Compare the performance of finetuning versus using extracted features.

2. **Movie Embedding**.In particular, if we can embed movies,then similar movies will be close to each other and can be recommended. This line of reasoning is analogous to the distributional hypothesis of word meanings. For words, this roughly translates to words that appear in similar sentences should have similar vector representations. For movies, vectors for two movies should be similar if they are watched by similar people. Let the total number of movies be 𝑖. Let 𝑖𝑖,𝑖 be the number of users that liked both movies 𝑖 and 𝑖. We want to obtain vectors 𝑖1, . . . , 𝑖𝑖 , . . . , 𝑖𝑖 , . . . , 𝑖𝑖 for all movies such that we minimize the cost 𝑖(𝑖1 , . . . , 𝑖𝑖 𝑖 𝑖=1 𝑖 𝑖=1 1[𝑖≠𝑖] (𝑖𝑖 𝑖𝑖 − 𝑖𝑖, )2 . Here 1 [𝑖≠𝑖] is a function that is 0 when 𝑖 = 𝑖 and 1 otherwise.
   PART A: Compute data 𝑖𝑖,𝑖 from the movielens (small) dataset and description. Briefly describe
           your data prep workflow (you can use pandas if needed).
   PART B: Optimize function 𝑖(𝑖1, . . . , 𝑖𝑖 ) over 𝑖1, . . . , 𝑖𝑖 using gradient descent (using pytorch or tensorflow). Plot the loss as a function of iteration for various choices (learning rates, choice of optimizers etc).
   PART C: Recommend top 10 movies (not vectors or indices but movie names) given movies
           (a) Apollo 13,
           (b) Toy Story, and
           (c) Home Alone.
           Describe your recommendation strategy.Do the recommendations change when you change learning rates or optimizers? Why or why not?
