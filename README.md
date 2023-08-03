# Project_1_Video_Game_Sales_EDA

Our Data Set: https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings?resource=download

Our project looked at the top 16,000 video game sales. The CSV file provided:
  
  Name
  Genre
  Territory Sales
  Critic and User scores
  ESRB Ratings
  Publishers
  Platforms
  Developers
  Year of Release

Our team approached the CSV through these different aspects:

  Genres: 
    1) What was the market share per Genre in each territory?
    - I found a lot of common top genres between all the territories. Action, Shooters, Platforms, and Sports seemed the most shared.

    2) How do the Critic scores and the User scores compare to each other per genre? 
    - The r-squared value between both scores was .72597, which means that we can use either score to make a reasonably good guess on what the other would be. 
    - After the first four genres for both groups, the critics seem to give a higher normalized weighted score when compared to the Users' normalized score:
        1: Do critics have a more consistent framework they can apply better across all genres of games?
        
        2: When it comes to sports, puzzle, and misc genre games, their normalized User scores are very low- if there are a lot of games in the market under these genres, are Users more critical since they need to decide whether to purchase the game or not?
            - Under this train of thought: there are a lot of Shooters in the market, yet both groups give them high ratings- further implying a broad appeal.
            
        3: Since Critics, I assume, are given free access to the games, yet Users have to purchase them- does this factor weigh more when Users score a game?
        
        4: When did each group review the game, and does this affect the rating?
            - Critics tend to review games on release.
            - Users can review the games anytime, affecting their score based on nostalgia or aversion to old technology.
            
        5: Strategy has nearly identical normalized weighted User and critic scores. Does this imply that Users and Crtics have a similar slate of criteria with which they evaluate these games? Less affected by certain factors like time and technology?
         
    
    3) What is the distribution per genre among the ESRB ratings?

    This question was good when asking what genre does best if the primary goal is selling a game to a certain audience:
    -  For example, if we wanted to sell a game marketed toward a Mature audience, we would want to focus on 3 genres:
          - Shooter
          - Action
          - RPGs

    Interestingly enough, Sports does best when it is an E rating, as well as dominating the E rating for all genres; this makes us ask:
          - Are sports with less physical contact preferred over sports with more physical contact (less violent)? 
          - Wii Sports may skew this heavily
          
    - There is a smaller pool of genres under the M rating
    
    - Action consistently sells high in 3 out of the 4 ratings

    
    4) After running a statistical analysis on the top 5 genres (based on Global Sales):
    
Genre: Shooter
p = 3.2e-48
The null hypothesis can be rejected. Data is not normally distributed.


Genre: Platform
p = 8.4e-49
The null hypothesis can be rejected. Data is not normally distributed.


Genre: Role-Playing
p = 1.8e-45
The null hypothesis can be rejected. Data is not normally distributed.


Genre: Sports
p = 2e-129
The null hypothesis can be rejected. Data is not normally distributed.


Genre: Action
p = 8.2e-88
The null hypothesis can be rejected. Data is not normally distributed.


        
    5) What does an Anova test for each genre against regional sales tell us?
      - If the ANOVA test provides a p-value < .05, then I can say that genre may be a significant factor in influencing sales for a territory :
      - I found significance between genre as a factor in NA sales and JP sales, meaning genre is a factor for sales in these two territories 
      - But, since we are not working with normal distributions, this may make our ANOVA test less reliable
          NA ANOVA p-value: 0.001472309428194264
          JP ANOVA p-value: 1.6801260542630636e-56

      
  
  Publishers: 

  Platforms:

  Top-Ten Games:
    1) How large was NA's influence on Global Sales?
    2) How does NA's choice in the top ten games influence/compare to the other regions' top ten games?
    3) 


  
