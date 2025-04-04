### **👥 Team Members**

| Team Salicylic Acid | BTT_Salicylic_Acid | Equitable AI for Dermatology |
| Noely Guzman | @noelyguzman |
| Tiffany Widjaja | @tiffanywid |
| Essie Cheng | @essiecheng | 
| Cindy Nakhammouane | @cnakha |
| Ahmed Haj Ahmed | | @AhmedHajAhmed |
| Jalal-Abdul Yahaya | @905j |

---

## **🎯 Project Highlights**

* Built a SVM and CNN model to classif 16 different skin conditions across diverse skin tones
* Achieved the following metrics:
  - Accuracy: 0.5804195804195804
  - Weighted F1 Score: 0.576784625411958
  - Mean Absolute Error: 2.770979020979021
* Ranked 15 out of 74 teams in the final Kaggle Leaderboard
* Used sklearn to interpret model decisions
    from sklearn.metrics import accuracy_score, f1_score, mean_absolute_error, classification_report, confusion_matrix

🔗 [Equitable AI for Dermatology | Kaggle Competition Page](https://www.kaggle.com/competitions/bttai-ajl-2025/overview)

---

## **👩🏽‍💻 Setup & Execution**

  - Notion 
  - Google Collaboratory
  - Slack
  - Github
---

## **🏗️ Project Overview**

This project was created for the Kaggle Competitions Equitable Competition. This competition is part of the Break Through Tech AI Program as the Spring Semester Project. Our goal is to build an inclusive machine learning model for dermatology and use the datasets provided to train a model that can classify 16 different skin conditions across diverse skin tones. This impacts society by raising awareness on how AI systems can perpetuate racism, sexism, ableism, and other harmful forms of discrimination and we need to build better and more accurate systems that can work with all forms of skin types. 

---

## **📊 Data Exploration**

The dataset used was provided by the Kaggle Competition and included a train and test set with 21 different sorted skin conditions and about over 2800 images in total. For data exploration, we counted up the number of images found in each condition and the 7 stages of these conditions. We hot one encoded the skin condition labels and then extracted the prepared the metadata features by filling missing values with 0. 
  
![image](https://github.com/user-attachments/assets/cb795cfc-2851-4d2b-9956-b47052bf4af8)

![image](https://github.com/user-attachments/assets/8cffd126-73e8-4426-9fd6-473fadf09cd1)

For model's data prepartion, we flattened images, PCA to redice dimensions (200 -> 500), use StandardScaler() to scale metadata features, convert labels to ints, initialized GridSearchCV to determine best hyperparamters for SVM, {'C': 10, 'gamma': 'scale', 'kernel': 'rbf'}. For the SVM, flatenning images result in too many pixels which introduces a lot of noise and messes up SVM since it is sensitive to noise. PCA reduces these many pizels to a smaller number, keeping the most important information while getting rid of noise. This is necessary becuase when combining these metadata features with PCA-transformed image features, the scales of the features might be very different. Scaling eliminates biases.


---

## **🧠 Model Development**

The models that we used we the **Support Vector Machine (SVM)** and **EfficientNetB0** model. We used the SVM model since one of our team members has had experience with using it. SVMs perform well in high-dimensional spaces, making them suitable for image classification where each pixel can be considered a feature. SVMs can handle both linear and non-linear classification tasks effectively using different kernel functions such as linear, polynomial, radial basis function (RBF), etc. SVMs are advantageous for their simplicity, memory efficiency, and interpretability, but they may not match the performance of deep learning models. SVM performance heavily depends on its hyperparameters. GridSearchCV systematically tests various parameter combinations and gives you the best one. 

The conclusion is that the best parameters for the scale is C: 10, gamma: scale, and kernel: rbf. For the training, we used 500 images that were PCA-transformed and scaled them for training. For evaluation, we used accuracy_score and the f1 weighed score. 

For the EfficientNetb0 CNN model, we choose this since it is stated to be "a good choice for image classification due to its high accuracy, efficiency, and suitability for resource-constrained environments. It achieves state-of-the-art results while being smaller and faster than other CNNs" and "is a convolutional neural network that is trained on more than a million images from the ImageNet database [1]. The network can classify images into 1000 object categories, such as keyboard, mouse, pencil, and many animals. As a result, the network has learned rich feature representations for a wide range of images (Matlab)." 

We used .2 test size and a random state of 42 for training the model. Since this model takes 2 hours to run, we have to rerun the model for every hyperparamter change for tuning. Currently, the best parameters are a scheduler, 20 epochs, dropout rate to .3 and increased batch size to 32. For evaluation, we used accuracy_score and the f1 weighed score. 

---

## **📈 Results & Key Findings**

For SVM Model, the accuracy was .28193 and a f1 score of 30.24% for the CNN model the accuracy was .59443, and a f1 score of 57%. Our model performed overall 15th in the Kaggle Competition. The confusion matrix of our CNN model is shown below. 

![image](https://github.com/user-attachments/assets/7de4f8a1-3394-45a2-90fa-b4f57fc62e6a)


---

## **🖼️ Impact Narrative**

**AJL challenge:**

As Dr. Randi mentioned in her challenge overview, “Through poetry, art, and storytelling, you can reach others who might not know enough to understand what’s happening with the machine learning model or data visualizations, but might still be heavily impacted by this kind of work.”
As you answer the questions below, consider using not only text, but also illustrations, annotated visualizations, poetry, or other creative techniques to make your work accessible to a wider audience.
Check out [this guide](https://drive.google.com/file/d/1kYKaVNR\_l7Abx2kebs3AdDi6TlPviC3q/view) from the Algorithmic Justice League for inspiration!

1. What steps did you take to address [model fairness](https://haas.berkeley.edu/wp-content/uploads/What-is-fairness_-EGAL2.pdf)? (e.g., leveraging data augmentation techniques to account for training dataset imbalances; using a validation set to assess model performance across different skin tones)
   Using higher quality specific models that are known for high accuracy. 
3. What broader impact could your work have?
  It can aid with helping with discrimination in technology and improving technology for all users. 
---

## **🚀 Next Steps & Future Improvements**

* What are some of the limitations of your model?
  - EfficientNetb0 takes around 2 hours to run, making iteration and hyperparameter tuning slow
  - SVMs generally work better for small-medium sized datasets and don’t scale as well for large datasets as they can be computationally expensive
* What would you do differently with more time/resources?
  - We could experiment with techniques such as transfer learning and data augmentation to further improve model robustness and better address possible class imbalances (as some skin conditions have fewer training samples)
  - We could try more hyperparameter tuning strategies (e.g. different activation functions) with more time, or reduce model running time with more hardware resources
* What additional datasets or techniques would you explore?
  - Additional datasets include [ISIC Archive](https://www.isic-archive.com/) and [Stanford DDI](https://stanfordaimi.azurewebsites.net/datasets/35866158-8196-48d8-87bf-50dca81df965)

---

## **📄 References & Additional Resources**

**Articles/Books**
- *“What does ‘fairness’ mean for machine learning systems?”*
    by Mulligan, Deirdre, et al. 
    
    Haas School of Business, University of California Berkeley, 2021. [Link](https://haas.berkeley.edu/wp-content/uploads/What-is-fairness_-EGAL2.pdf)

- *Unmasking AI: My Mission to Protect What Is Human in a World of Machines.*
    by Buolamwini, Joy.
    
    Random House, 2023.

**Tools & Resources**
- ***TensorFlow and Keras*** for loading and preprocessing images, implementing the EfficientNetB0 architecture, and training the model with custom callbacks

-  ***Scikit-learn*** for scaling metadata features with StandardScaler, hyperparameter tuning using GridSearchCV for the SVM, and evaluating model performance

- ***Pandas*** for feading and preprocessing the training and test datasets and handling metadata columns.

- ***NumPy*** for storing and processing image data as arrays. Also for concatenating PCA-reduced image features with scaled metadata features.

- ***Matplotlib and Seaborn*** for visualizing the distribution of skin conditions using bar plots and generating confusion matrices and other evaluation visualizations.

- ***tqdm*** for providing real-time feedback on the progress of image loading and preprocessing tasks.



