# Farmsmart_model_training_and_evaluation

data link: https://figshare.com/articles/dataset/Dataset_HydroFarm/28340516/1?file=52114643

Training instance	Optimizer used(Adam, RMSPoP)	Regularizer Used(L1 and L2)	Epochs	"Early Stopping
( Yes or No)"	Number of Layers	Learning Rate	Accuracy	F1 Score	Recall	 Precision
Instance 1	Adam	None	20	Yes	7	0.0005	0.9221	0.9286	1	0.8667
Instance 2	Adam	Dropout	15	Yes	8	0.001	0.9481	0.9512	1	0.907
Instance 3	Rmsprop	L2	20	Yes	7	0.0005	0.8701	0.875	0.8974	0.8537
Instance 4	Adam	L2	15	Yes	8	0.0001	0.9351	0.9398	1	0.8864
Instance 5 (VGG16 (feature extractor) + Logistic Regression)	N/A	None	N/A	No	1 (Logistic Regression only)	N/A	0.961	0.962	0.97	0.95
