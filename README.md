# nfl-player-contact-detection
[1st and Future - Player Contact Detection](https://www.kaggle.com/competitions/nfl-player-contact-detection)

## NOTES
1. STEP (0.1s 10Hz) - FRAME (step/10*59.95+5*59.95) - SAMPLE RATE (59.94Hz.)
    1. Tracking data is collected at 10Hz every 0.1 second should have a datapoint.
    2. Video data is collected at 59.94Hz.
    3. Submissions are at the tracking data 10Hz.
    4. Because of the differences in sample rate it's impossible to perfectly line up the two datasets. One approach is to use the metadata file which gives the approximate start_time of each video, then calculate the approximate timestamp of each frame to merge with the tracking data.
   
    Referring from [discussion](https://www.kaggle.com/competitions/nfl-player-contact-detection/discussion/371638) & [notebook](https://www.kaggle.com/code/robikscube/nfl-player-contact-detection-getting-started#NFL---Player-Contact-Detection-Challenge)

## TODO
### TABULAR
- [x] Split train-test dataset and upload to dataset (01/21)
nerate tabular features (01/21)
- [x] Write a notebook to train an XGBoost model (01/22)
- [x] Write a notebook to generate tabular features (01/21)
- [ ] Feature engineering for tabular data (01/27)
    1. FE on tracking data ('x_position_1',
       'y_position_1', 'speed_1', 'distance_1', 'direction_1', 'orientation_1',
       'acceleration_1', 'sa_1', 'x_position_2', 'y_position_2', 'speed_2',
       'distance_2', 'direction_2', 'orientation_2', 'acceleration_2', 'sa_2',
       )
    2. Get the feature importance of the model
    3. Use OpenFE to generate 64~256 features and save the dataset
- [x] Train seperate models for player-player and player-ground models to see if there's any improvements (01/22)
- [ ] Tune one hyperparams for XGBoost model (01/28)
- [ ] Try other GBDT models / AutoGluon if the tuned model has a competitive performance

### VIDEO/IMAGE
- [ ] Understand the helmet dataset (01/24)
- [ ] Visualize helmets bbox (01/25)
- [ ] Hands on CV models (01/28)
   
## Ideas & Experiments
|IDEA|Experiment|Before|After|
|----|----------|------|-----|
|Use OpenFE to generate tabular features|Use [XGBoost baseline](https://www.kaggle.com/code/columbia2131/nfl-player-contact-detection-simple-xgb-baseline) to train 64 openfe features|0.583|0.591|
|Train seperate models for player 2 player contact & player 2 ground model on tabular data|Use [XGBoost baseline](https://www.kaggle.com/code/columbia2131/nfl-player-contact-detection-simple-xgb-baseline) to train seperate models for p2p & p2g tabular data |0.583|0.505|
|Group k fold using game_id instead of game_play|se [XGBoost baseline](https://www.kaggle.com/code/columbia2131/nfl-player-contact-detection-simple-xgb-baseline) to train group k fold using game_id|0.583|0.586|

## Problems
1. Bad peformance for player2ground prediction 
    > p2g score: 0.29475; p2g threshold: 0.06826
    >
    > p2p score: 0.67806; p2p threshold: 0.31533
2. Bad performance training seperate models (might be because of the evaluating metrics)