# Project_1_Video_Game_Sales_EDA

Slide Show: https://onedrive.live.com/edit.aspx?action=editnew&resid=198B13F643BD0361!237&ithint=file%2cpptx&action=editnew&ct=1691026191386&wdNewAndOpenCt=1691026191130&wdPreviousSession=cdb33e36-b5f4-4242-b1c2-a9c03dfe8e70&wdOrigin=OFFICECOM-WEB.START.NEW&wdPreviousSessionSrc=HarmonyWeb&wdo=2

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
    
    - I ran a linear regression test between critic and user scores and received an R-squared value of about 0.72597. This means that approximately 72.6% of the variability in one group's score can be explained by the other group's score in our model. So, we can use either group's score to reasonably predict the other group's score, bearing in mind that there's still around 27.4% of the variability our model doesn't account for.
 
    - After the first four genres for both groups, the critics seem to give a higher normalized weighted score when compared to the Users' normalized score:
        1: Do critics have a more consistent framework they can apply better across all genres of games?
        
        2: When it comes to sports, puzzle, and misc genre games, their normalized User scores are very low- if there are a lot of games in the market under these genres, are Users more critical since they need to decide whether to purchase the game or not?
            - Under this train of thought: there are a lot of Shooters in the market, yet both groups give them high ratings- further implying a broad appeal.
            
        3: Since Critics, I assume, are given free access to the games, yet Users have to purchase them- does this factor weigh more when Users score a game?
        
        4: When did each group review the game, and does this affect the rating?
            - Critics tend to review games on release.
            - Users can review the games anytime, affecting their score based on nostalgia or aversion to old technology.
            
        5: Strategy has nearly identical normalized weighted User and critic scores. Does this imply that Users and Crtics have similar criteria for evaluating these games? Less affected by certain factors like time and technology?
         
    
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


4)

Lastly, I ran a statistical analysis on the top 5 Genres, which I determined based on their market share within the Global Sales

	- These were:
		○ Shooters
		○ Platforms
		○ RPGs
		○ Sports
		○ Action
		
	- First, I ran a normal test and found the p values for each to be smaller than .05, meaning we can reject the null and that the data was not normally distributed. 

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

	- Since it is not normally distributed, we would use the median as the center of our data.
	
	- I also calculated the Upper and lower quartiles, upper and lower bound, and the IQR

	- We can use the IQR as a method to quantify dispersion around the median

- The data is quite varied based on the medians and IQRs for each of these genres' sales. 

- Couple this with many outliers performing particularly well, and we can infer that some outside factors push some sales above others.

  - Proof of this is Wii Sports, the best-selling sports game sold, giving it the largest outlier; this could be due to the fact that its sales were coupled with the sales of the Wii console. Would the sales of this game be the same if it were not coupled with the Wii?

  - Another factor that could offset is that a game considered one genre is purchased for another reason.

    - Example: people purchased an RPG based on its Action, so maybe it sold surprisingly well as an RPG but may have sold not as well as an Action game
  
  - Brand recognition: Something like Mario always does well as a platform because of its IP and the marketing dollars behind it. This could skew the data and drown out other Platforms, as well as contribute to the genre of Platforms being so popular since there are so many Mario games, and a lot are considered Platforms

I was still curious about other distributions, so instead of running a normality test against just the
the distribution of all global sales for the top 5 genres.

I did a normality test of the distribution of total Regional  sales for each genre. Doing this gave me p values above .05 for NA and EU, meaning they may be normally distributed.

When running an ANOVA test, I did at least receive a P-value of .00147 for NA (below .05); therefore, we would be able to reject the null hypothesis of the ANOVA test, which states that there are no differences between the means of the groups being compared.
This tells us that NA sales and the genre may have a statistical significance. 

Meaning that genre may be associated with differences in game sales within North America, yet I cannot say that is a specific factor or influence when purchasing a game in NA.

Other factors may have a larger influence, like certain genres are more heavily marketed and have bigger development budgets.

  Platforms:
  # Calculate the total sales for each platform by summing sales from all regions

  Group the data by 'Platform' and calculate the total sales for each                      
  platforme
  Create a DataFrame for best performing platforms

  Find the platforms with the highest total sales

  Create a bar chart for best performing platforms


# Find the top platform by year of release
  Create a bar chart to visualize the top platform by year of release

# Group the data by Platform and calculate the number of game releases for   
  Each platform
  
  Display the number of game releases for each platform
  
  Create a bar chart to visualize the number of game releases by platform

# Group the data by 'Platform' and calculate the number of game releases for     
  each platform

  Display the number of game releases for each platform
  
  Create a bar chart to visualize the number of game releases by platform in  
   escending order



  Top-Ten Games:
    1) How large was NA's influence on Global Sales?
    2) How does NA's choice in the top ten games influence/compare to the other regions' top ten games?
    3) 

#Publishers: 
  Here is a list of sales in descending order grouped by publisher. In the top left, we can see the other sales. What’s interesting to see here is that in every other region, Nintendo is number 1. Here, Electronic arts outperformed to hold the number one spot.
moving over to Japan sales in the top right, you can see that 61.3% of all sales are held by Nintendo, showcasing its dominance in the Japanese market. What’s also interesting to know is that of the top 10 publishers, the only one not a Japanese company is coming in 10th place; Electronic Arts
moving to the bottom left corner is the EU sales data. You can see once again Nintendo has significantly higher sales than EA. The EU is a significantly larger market than the previous two regions we've covered.
When looking at North American sales in the bottom right, we see that there is a higher volume of sales compared to the other three regions. The EU and NA have the same top 4 publishers, and 5 out of the next 6 spots are the same, just placed differently. 
This graph collectively shows how much Nintendo outsold its competition. 
in the same lay, we can look at sales grouped by Genre. As Luis alluded to with his statistical analysis, Action is the favored genre. in the other region, the competition is much closer.
#generas:
Japan is the only region where Action doesn’t hold the number one spot; it was bumped to the 3rd spot.
The EU looks more evenly distributed. NA favors action and shooters.
On this graph, we can see all the previous slide data displayed. what is interesting to see here is how Japan almost outplays North America in the role-playing genre. This also allows us to see how large the NA market is and how this region's sales dwarf the other regions we looked at.

