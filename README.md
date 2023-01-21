# nfl-player-contact-detection
[1st and Future - Player Contact Detection](https://www.kaggle.com/competitions/nfl-player-contact-detection)

## TODO
### TABULAR
- [x] Split train-test dataset and upload to dataset (01/21)
- [ ] Write a notebook to generate tabular features (01/21)
- [ ] Write a notebook to train an XGBoost model (01/21)
- [ ] Feature engineering for tabular data
- [ ] Train seperate models for player-player and player-ground models to see if there's any improvements (01/22)

### VIDEO/IMAGE
1. Understand the helmet dataset
   
## Ideas & Experiments
|IDEA|Experiment|Before|After|
|----|----------|------|-----|
|Use OpenFE to generate tabular features|Use [XGBoost baseline](https://www.kaggle.com/code/columbia2131/nfl-player-contact-detection-simple-xgb-baseline) to train 64 openfe features|0.583|0.591|