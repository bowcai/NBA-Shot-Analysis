# NBA-Shot-Analysis

### R.I.P. Kobe Bryant (1978-2020)

![R.I.P. Kobe Bryant](https://media.nbclosangeles.com/2019/09/kobe-bryant-obit-lakers-image.jpg?resize=425%2C239)

#### A very simple NBA shot data analysis project based on "shotchartdetail" from NBA official stats API: https://stats.nba.com/

In this project, we use every single shot attempt during player's career to train a linear model.
From the coefficients of linear model, we try to figure out how different factors contribute to a successful shot.

By comparing different players' models, we may also preliminarily classify them into different types.


## Dependancy

Python3

Some basic data analysis packages such as numpy, pandas, matplotlib, scikit-learn

Collect data from NBA Stats with `nba_api`: https://github.com/swar/nba_api

# Introduction

## Preprocessing

Our original data is from a Kaggle competition "Kobe Bryant Shot Selection": https://www.kaggle.com/c/kobe-bryant-shot-selection

We first process Kobe's data in `Preprocessing/Preprocessing.ipynb`:

1. Clean the data and discard some redundant features.

2. Visualize Kobe's shot accuracy with different shot types, shot zones, seasons and periods.  
Meanwhile, we compare Kobe with Stephen Curry's shot data in `Preprocessing/Curry_Visualize.ipynb`, which was acquired from NBA Stats.

3. Shoose a model to fit the data for later analysis.

From preprocessing, we decide to analyze further data only with a linear model.

## Shot Analysis

In `Shot_Analysis` directory, we use different players' data to train their models,
and classify the players with coefficients of their linear models.  
**CAUTION: ONLY A FEW sample data is uploaded in `Shot_Analysis/shot_data` directory.**

`Shot_Analysis/NBA_GetData.ipynb`: Run to collect all active players' shot data from NBA Stats.

`Shot_Analysis/NBA_TrainModel.ipynb`: Clean different players' data and use them to train their models.

`Shot_Analysis/NBA_PlayerClassify.ipynb`: Use different players' models to classify them.

## Opponent Analysis

We use the same method to analyze shot data with same opponent team,
in order to figure out the defense behaviors of different teams.  
**CAUTION: ONLY A FEW sample data is uploaded in `Opponent_Analysis/shot_data` directory.**

`Opponent_Analysis/NBA_GetData.ipynb`: Transfer the files in `Shot_Analysis/shot_data`,
which are sorted by same PLAYER_ID, into files sorted by same OPPONENT_TEAM_ID.

`Opponent_Analysis/NBA_TrainModel.ipynb`: Clean different opponents' data and use them to train their models.

`Opponent_Analysis/NBA_PlayerClassify.ipynb`: Use the models to classify teams.
