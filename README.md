# RecsysIBM
Perform recommendation skills to use on real data from the IBM Watson Studio platform.

### Libraries: 
ntlk

### Summary:
The project analyzes the interactions that users have with articles on the IBM Watson Studio platform, and make recommendations to them with 1 Rank-based Recommendations, 2 User-user based Collaborative Filtering, 3 Content-based Recommendations, and 4 Matrix Factorization.

1. Rank-based Recommendations:recommend the top articles with most interactions.
2. User-user based Collaboractive Filtering: provide an orderd list of the most similar users to user A, finds articles user A hasn't seen before and provides A as recs (choose the users that have the most total article interactions before choosing those with fewer article interactions, when users who are all the same closeness to user A; choose articles with the articles with the most total interactions before choosing those with fewer total interactions)
3. Content-based Recommendations: apply the natural language processing (NLP) to the titles of the articles to classify them, define the preference of the user based on their readings, calculate the similarity between each article and the user preference and make recommendations

#### functions:
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
