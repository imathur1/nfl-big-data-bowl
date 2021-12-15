# NFL Big Data Bowl 2022

My submission for the [NFL Big Data Bowl 2022](https://www.kaggle.com/c/nfl-big-data-bowl-2022) competition. I built a model that
uses NFL kickoff data to predict the kick returner's expected return yards. A lot of inspiration was taken from the 
1st place [solution](https://www.kaggle.com/c/nfl-big-data-bowl-2020/discussion/119400) for the [NFL Big Data Bowl 2020](https://www.kaggle.com/c/nfl-big-data-bowl-2020)
competition which focused on the expected rushing yards a rusher would gain after handoff. My model trains on the kickoff plays which
don't end in a touchback, meaning the returner fields the ball and returns it for some amount of yards. I used a 2D CNN model that
takes in the X and Y positions of all players on the field at the moment the kick returner fields the ball, and uses relative features
such as speed and direction between the offense and defense to create meaningful and accurate predictions. Below are some metrics evaluating my model's performance after training.
With further hyperparameter tuning the results from the validation set could improve a fair amount as well.

|                  | Train Set     | Validation Set |
| ---------------  | ------------- | -------------- |
| [CRPS Loss](https://datascience.stackexchange.com/questions/63919/what-is-continuous-ranked-probability-score-crps/64320)        | 0.00246       | 0.01539        |
| Avg. Yards Error | 0.51312       | 3.37437        |
| R<sup>2</sup> score        | 0.99975       | 0.98614        |


All the data from the Kaggle competition is in this repository except for the `tracking2018.csv`, `tracking2019.csv`, and `tracking2020.csv` because
those files are too large. To run this code locally, those files would have to be downloaded from the Kaggle competition and moved into this repository.
