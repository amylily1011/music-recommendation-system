# **Music Recommendation System**
**<h1>Executive summary</h1>**
Discovering new songs is a tedious task. Throughout history, music has been a significant part of human life and culture. With the advancement of technology, music from different parts of the world has become more accessible. However, the ever-growing database of music can make the **search and discover experience overwhelming, leading to content overload and straining our cognitive abilities.**

The rapid pace of technological evolution has influenced our lives to become more fast-paced and often distracted, driving the demand for solutions that improve efficiency. Music is intertwined with our daily routines, and many industries incorporate music into their business strategies.

To overcome content overload and save time, we need a system that provides people with access to personalized music, offering a variety of styles for them to explore. This reduces the burden of decision-making, helps users stay updated with new releases, and allows them to use their time more efficiently. Additionally, music discovery helps people connect with new communities and provides exposure to emerging artists and genres.

For these reasons, a music recommendation system serves as an **intelligent assistant** that helps users **discover, enjoy, and stay engaged with music in a way that feels personal, effortless, and exciting.** It allows users to focus on the joy of listening rather than the hassle of searching.

With the ever-increasing volume of songs becoming available on the Internet, **searching for songs of interest has become a tedious task in itself** .

### **The objective:**

Build a recommendation system to propose the top 10 songs for a user based on the likelihood of listening to those songs.


**The key questions:**
* How can we model user preferences for songs?
* How do we measure the similarity between songs and users?
* What factors influence a user's likelihood of listening to a song?
* How can we account for new or rarely listened-to songs in recommendations?
* How do we continuously improve recommendations as user preferences evolve?

### **The problem formulation**:

We need a way to predict **the top 10 songs that a user is most likely to listen to next, based on their past interactions and collaborative filtering approaches with the platform.** Using data science, we want to solve the problem of making personalized music recommendations by leveraging user data and song features.


In this case study we used 6 different algorithms to built the recommendation system, namely:

* Popularity-based recommendation system
* User-user similarity based collaborative filtering
* Item-item similarity based collaborative filtering
* Model Based Collaborative Filtering - Matrix Factorization
* Cluster-base recommendation system
* Content-base recommendation system

  **Consolidating all performance:**


---
| <h3>Technique</h3> | <h3>RMSE</h3> | <h3>Precision</h3> | <h3>Recall</h3> | <h3>F1 Score</h3> |
|---------|----|---------|------|---------|
|<h4>User-user similarity</h4>|<h4>1.0878|<h4>0.396|<h4>0.629|<h4>0.504|
|<h4>User-user Optimized</h4>|<h4>1.0328|<h4>0.408|<h4>0.665|<h4>0.506|
|<h4>Item-item similarity</h4>|<h4>1.0394| <h4>0.307|<h4>0.562|<h4>0.397|
|<h4>Item-item Optimized</h4>|<h4>1.0328| <h4>0.408|<h4>0.665|<h4>0.506|
|<h4>SVD similarity matrix</h4>|<h4>1.0252| <h4>0.41|<h4>0.633| <h4>0.498|
|-----------------------------------------------------------------------|--|--|--|--|--|
|<h4>SVD Optimized **</h4>|<h4>1.0141| <h4>0.415|<h4>0.635| <h4>0.502|
|-----------------------------------------------------------------------|--|--|--|--|--|
|<h4>Cluster-based recommendaiton</h4>|<h4>1.0487|<h4> 0.397|<h4>0.582| <h4>0.472|
|<h4>Cluster-based Optimized</h4>|<h4>1.0487| <h4>0.397|<h4>0.582| <h4>0.472|






Content-based with cosine similarity

```
[1., 0., 0., ..., 0., 0., 0.],
[0., 1., 0., ..., 0., 0., 0.],
[0., 0., 1., ..., 0., 0., 0.],
       ...,
[0., 0., 0., ..., 1., 0., 0.],
[0., 0., 0., ..., 0., 1., 0.],
[0., 0., 0., ..., 0., 0., 1.]]
```

**<h1>Problem and Solution Summary</h1>**

**Problem with the current solution:**
* The current solution relies on individual recommendation techniques, which even the best performing algorithm (Optimized SVD) **still has obtains a relatively low accurracy (RSME: 1.0141)**. Although the recall is acceptable (0.635), there are still 36.5% relevant songs that are not recommended to users. There is still a substantial portion of songs missing that are relevant and that users might enjoy.
* There is a **lack of diversity** in the current recommendation models, making the recommendation repetitive and lacks variety.
* SVD could face **computational challenges** in processing and updating recommendations in large-scale systems.



**What does the proposed solution bring?**

The **hybrid recommendation system** combining **SVD-based collaborative filtering** and **content-based filterin**g is proposed to improve 3 aspects of the recommendation system:

1. **Improve personalization**
 * **SVD** uses user interaction data (such as play counts) to predict which song a user will likely enjoy. It ensures that the recommendation are personalized based on collective behavior and similar users.

2. **Enhance Diversity:**
 * **Content-based filtering** analyzes song metadata such as genre, artist, year, and more, to recommend songs with similar features. This will help recommending new or rarely interacted songs, addressing the cold start problem where collaborative filtering along struggles to recommend content with our sufficient user interaction data.
3. **Balance between Relevance and Variety:**
 * The **hybrid system** aims to provide a balance between relevant suggestions based on past user behaviors and introducing new/diverse suggestions. This ensures that users are not stuck with repetive recommendations, enhancing the experience of listeners.  

**Business Impact**

1. **Increase User Engagement:**
 - By delivering more personalized and diverse recommendations, it encourages users to spend more time on the platform. This can increase user satisfaction and retention.  
2. **Potential Revenue Growth:**
 - Improved recommendations mean users are more likely to remain on the platform for longer periods, which can link to **increase in revenue via subscription and advertisements**. More listening hours can result in better monetizing opportunities.
3. **Enhanve Discovery of New Content:**
- The system helps user discover new songs and artists, which is crucial for long-term engagement, especially as the music library expands.
4. **Better Artist Exposure:**
 - Using content-based filtering to **expose less popular songs or new artists** to a wider audience can help the platform support emerging talent while catering to diverse music tastes.

 In summary, as the song library expands, the hybrid recommendation system will solve problem of **content overload** by enhancing relevance, diversity, and personalized recommendations. This leads to an improved user-engagement and business growth.
