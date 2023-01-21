# nfl-player-contact-detection
[1st and Future - Player Contact Detection](https://www.kaggle.com/competitions/nfl-player-contact-detection)

## TODO
### TABULAR
- [x] Split train-test dataset and upload to dataset (01/21)
nerate tabular features (01/21)
- [ ] Write a notebook to train an XGBoost model (01/21)
- [ ] Feature engineering for tabular data

- [x] Write a notebook to generate tabular features (01/21)
- [ ] Write a notebook to train an XGBoost model (01/21)
- [ ] Feature engineering for tabular data
    1. FE on tracking data ('x_position_1',
       'y_position_1', 'speed_1', 'distance_1', 'direction_1', 'orientation_1',
       'acceleration_1', 'sa_1', 'x_position_2', 'y_position_2', 'speed_2',
       'distance_2', 'direction_2', 'orientation_2', 'acceleration_2', 'sa_2',
       )
=======
- [ ] Train seperate models for player-player and player-ground models to see if there's any improvements (01/22)

### VIDEO/IMAGE
1. Understand the helmet dataset
   
## Ideas & Experiments
|IDEA|Experiment|Before|After|
|----|----------|------|-----|
|Use OpenFE to generate tabular features|Use [XGBoost baseline](https://www.kaggle.com/code/columbia2131/nfl-player-contact-detection-simple-xgb-baseline) to train 64 openfe features|0.583|0.591|
|Train seperate models for player 2 player contact & player 2 ground model on tabular data|Use [XGBoost baseline](https://www.kaggle.com/code/columbia2131/nfl-player-contact-detection-simple-xgb-baseline) to train seperate models for p2p & p2g tabular data (G_flag feature is dropped)|0.583|?|
