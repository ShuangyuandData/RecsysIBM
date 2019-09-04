# RecsysIBM
Perform recommendation skills to use on real data from the IBM Watson Studio platform.

### Libraries: 
None

### Summary:
The project analyzes the interactions that users have with articles on the IBM Watson Studio platform, and make recommendations to them with 1 Rank-based Recommendations, 2 User-user based Collaborative Filtering, 3 Content-based Recommendations, and 4 Matrix Factorization.

1. Rank-based Recommendations:recommend the top articles with most interactions.
2. User-user based Collaboractive Filtering: provide an orderd list of the most similar users to user A, finds articles user A hasn't seen before and provides A as recs (choose the users that have the most total article interactions before choosing those with fewer article interactions, when users who are all the same closeness to user A; choose articles with the articles with the most total interactions before choosing those with fewer total interactions)
