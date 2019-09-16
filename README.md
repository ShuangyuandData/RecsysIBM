# RecsysIBM
Perform recommendation skills to use on real data from the IBM Watson Studio platform.

### Libraries: 
ntlk

### Summary:
1. Analyze the interactions that users have with articles on the IBM Watson Studio platform, and make recommendations to them about new articles they will like.
2. Explore 5148 users, 1051 articles, and 45993 user-article interactions. 
3. Include 4 methods:(a) Rank-based Recommendations, (b) User-user based Collaborative Filtering, (c) Content-based Recommendations, and (d) Matrix Factorization (SVD: the accuracy on the test data reach over 96%).


![Image of result](https://github.com/ShuangyuandData/RecsysIBM/blob/master/IBMfigure.png)

(a). Rank-based Recommendations:recommend the top articles with most interactions.
(b). User-user based Collaboractive Filtering: provide an orderd list of the most similar users to user A, finds articles user A hasn't seen before and provides A as recs (choose the users that have the most total article interactions before choosing those with fewer article interactions, when users who are all the same closeness to user A; choose articles with the articles with the most total interactions before choosing those with fewer total interactions)
(c). Content-based Recommendations: apply the natural language processing (NLP) to the titles of the articles to classify them, define the preference of the user based on their readings, calculate the similarity between each article and the user preference and make recommendations
(d). Matrix Factorization: Build out a matrix decomposition (SVD) with the user-item interactions. Get an idea of how well the recommendation system can predict new articles an individual might interact with.

#### Description of Functions in main code file(Recommendations_with_IBMfinal.ipynb):
1. get_top_articles(n, df=df): top_articles - (list) A list of the top 'n' article titles 
2. get_top_article_ids(n, df=df): top_articles - (list) A list of the top 'n' article titles 
3. create_user_item_matrix(df): Return a matrix with user ids as rows and article ids on the columns with 1 values where a user interacted with an article and a 0 otherwise
4. find_similar_users(user_id, user_item=user_item): similar_users - (list) an ordered list where the closest users (largest dot product users) are listed first
5. get_article_names(article_ids, df=df): (list) a list of article names associated with the list of article ids (this is identified by the title column)
6. get_user_articles(user_id, user_item=user_item): (list) a list of article names associated with the list of article ids (this is identified by the doc_full_name column in df_content)
7. user_user_recs(user_id, m=10): recs - (list) a list of recommendations for the user
8. get_top_sorted_users(user_id, df=df, user_item=user_item): neighbors_df - (pandas dataframe) a dataframe with: neighbor_id - is a neighbor user_id, similarity - measure of the similarity of each user to the provided user_id, num_interactions - the number of articles viewed by the user - if a u
9. get_top_sorted_articles(article_list, df=df, user_item=user_item): final_list - a list with the articles with the most total interactions before those with fewer total interactions. 
10. user_user_recs_part2(user_id, m=10): recs - (list) a list of recommendations for the user by article id, rec_names - (list) a list of recommendations for the user by article title
11. tokenize(text): return the clean_tokens from 7text
12. create_a_pool(df=df, n=100): a list with top n words
13. userpreference(user, df=df): the weighted preference in genres
14. dfsimilarity(user,df=df): a list of article id with the better similarity ahead based on the content
15. make_content_recs(user, n, df=df): a list of artile id recommended

### Reference:
Udacity
