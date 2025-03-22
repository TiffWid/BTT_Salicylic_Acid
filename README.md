### **👥 Team Members**

| Team Salicylic Acid | BTT_Salicylic_Acid | Equitable AI for Dermatology |
| Noely Guzman | @noelyguzman |
| Tiffany Widjaja | @tiffanywid |
| Essie Cheng | @essiecheng | 
| Cindy Nakhammouane | @cnakha |
| Ahmed Haj Ahmed | | @905j
| Jalal-Abdul Yahaya | @AhmedHajAhmed |

---

## **🎯 Project Highlights**

**Example:**

* Built a SVM and CNN model using \[techniques used\] to solve classifying 16 different skin conditions across diverse skin tones
* Achieved an F1 score of \[insert score\] and a ranking of 10th on the final Kaggle Leaderboard
* Used \[explainability tool\] to interpret model decisions
* Implemented \[data preprocessing method\] to optimize results within compute constraints

🔗 [Equitable AI for Dermatology | Kaggle Competition Page](https://www.kaggle.com/competitions/bttai-ajl-2025/overview)

---

## **👩🏽‍💻 Setup & Execution**

Clone into Repo using https or ssh
Open .pynb file and run 

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

**Describe (as applicable):**

* Model(s) used (e.g., CNN with transfer learning, regression models)
* Feature selection and Hyperparameter tuning strategies
* Training setup (e.g., % of data for training/validation, evaluation metric, baseline performance)

The models that we used we the Support Vector Machine (SVM) and EfficientNetB0 model. We used the SVM model since one of our team members has had experience with using it. SVMs perform well in high-dimensional spaces, making them suitable for image classification where each pixel can be considered a feature. SVMs can handle both linear and non-linear classification tasks effectively using different kernel functions such as linear, polynomial, radial basis function (RBF), etc. SVMs are advantageous for their simplicity, memory efficiency, and interpretability, but they may not match the performance of deep learning models. SVM performance heavily depends on its hyperparameters. GridSearchCV systematically tests various parameter combinations and gives you the best one. 

The conclusion is that the best parameters for the scale is C: 10, gamma: scale, and kernel: rbf. For the training, we used 500 images that were PCA-transformed and scaled them for training. For evaluation, we used accuracy_score and the f1 weighed score. 

For the EfficientNetb0 CNN model, we choose this since is stated to be "a good choice for image classification due to its high accuracy, efficiency, and suitability for resource-constrained environments. It achieves state-of-the-art results while being smaller and faster than other CNNs" and "is a convolutional neural network that is trained on more than a million images from the ImageNet database [1]. The network can classify images into 1000 object categories, such as keyboard, mouse, pencil, and many animals. As a result, the network has learned rich feature representations for a wide range of images (Matlab)." 

This model took two hours to train, but we used a 20% of the images

**Model 1: Support Vector Machine**

* Built a Support Vector Mechine Model using image classification and unsupervised learniing to build an inclusive machine learning model for dermatology. Our goal was to train a model that can classify 21 different skin conditions across diverse skin tones, using the datasets provided here in Kaggle.
* Achieved an F1 score of  0.2856 and a ranking of 14/73 on the final Kaggle Leaderboard
* Used sklearn.metrics and imported the classification_report to interpret model decisions
* Implemented the following to optimize results within compute constraints:
    1.  Numpy to flatten the images for SVM
    2.  Principal component analysis (PCA) to reduce excess noise
    3.  StandardScaler from sklearn.preprocessing to standradize features
    4.  GridSearchCV to systematically test various parameter combinations and get you the best ones

**Model 2: EfficientNetv0 Convolutional Neural Network**
* Built a EfficientNetv0 Convolutional Neural Network using image classification and unsupervised learniing to build an inclusive machine learning model for dermatology. Our goal was to train a model that can classify 21 different skin conditions across diverse skin tones, using the datasets provided here in Kaggle.
* Achieved an F1 score of 0.576784625411958 and a validation accuracy of 0.5804195804195804
* Used sklearn.metrics and imported the classification_report to interpret model decisions
* Implemented the following to optimize results within compute constraints:
    1.

**Hyperparamter Tunings and Results**

1. Changed nuerons for image batch to 512 and metadata batch to 64 and the combined batch to 256; changed dropout rate to 0.3 to avoid overfitting; increased batch_size to 32 and decreased epochs to 7
  - => accuracy: 0.5472028255462646

2. Added a scheduler; back to 10 epochs
  - => accuracy: Validation Accuracy: 0.5716783404350281

3. Increased epochs to 20
  - => accuracy: 0.58976
4. Increased epochs to 40
  - => accuracy: 0.59443


---

---

## **📈 Results & Key Findings**

**Describe (as applicable):**

* Performance metrics (e.g., Kaggle Leaderboard score, F1-score)
* How your model performed overall
* How your model performed across different skin tones (AJL)
* Insights from evaluating model fairness (AJL)

**Potential visualizations to include:**

* Confusion matrix, precision-recall curve, feature importance plot, prediction distribution, outputs from fairness or explainability tools

---

## **🖼️ Impact Narrative**

**AJL challenge:**

As Dr. Randi mentioned in her challenge overview, “Through poetry, art, and storytelling, you can reach others who might not know enough to understand what’s happening with the machine learning model or data visualizations, but might still be heavily impacted by this kind of work.”
As you answer the questions below, consider using not only text, but also illustrations, annotated visualizations, poetry, or other creative techniques to make your work accessible to a wider audience.
Check out [this guide](https://drive.google.com/file/d/1kYKaVNR\_l7Abx2kebs3AdDi6TlPviC3q/view) from the Algorithmic Justice League for inspiration!

1. What steps did you take to address [model fairness](https://haas.berkeley.edu/wp-content/uploads/What-is-fairness_-EGAL2.pdf)? (e.g., leveraging data augmentation techniques to account for training dataset imbalances; using a validation set to assess model performance across different skin tones)
2. What broader impact could your work have?

---

## **🚀 Next Steps & Future Improvements**

**Address the following:**

* What are some of the limitations of your model?
* - EfficientNetB0 takes around 2 hours to train, making iteration and hyperparameter tuning slow
* What would you do differently with more time/resources?
* What additional datasets or techniques would you explore?

---

## **📄 References & Additional Resources**

* Cite any relevant papers, articles, or tools used in your project

---



