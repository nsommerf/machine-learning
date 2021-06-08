# machine-learning
HW 21

Background
Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system.
To help process this data, you will create machine learning models capable of classifying candidate exoplanets from the raw dataset.
In this homework assignment, you will need to:

Preprocess the raw data
Tune the models
Compare two or more models



Instructions

Preprocess the Data

Preprocess the dataset prior to fitting the model.
Perform feature selection and remove unnecessary features.
Use MinMaxScaler to scale the numerical data.
Separate the data into training and testing data.


Tune Model Parameters

Use GridSearch to tune model parameters.
Tune and compare at least two different classifiers.


Reporting

Create a README that reports a comparison of each model's performance as well as a summary about your findings and any assumptions you can make based on your model (is your model good enough to predict new exoplanets? Why or why not? What would make your model be better at predicting new exoplanets?).

#This project had a few attempts to get a model over 85%.  Model 3 and Model 4 were the best attempts.  Model 4 was the saved model.

#Model 1 has selected features that I picked based on data descriptions.  Then did MinMax scaler on that dataframe and built model off of that. SVM with grid.  

#model 2  has selected features that I picked based on data descriptions.  Only 10 features.  Then did MinMax scaler on that dataframe and built model off of that. SVM with grid.  77% was best.

#mdoel 3  Even though I ran selected features from model 1, I ended up using X and y based on the entire features in the end to see if percent went up.  It did go up a few percentage points to 88.  Then did MinMax scaler on that dataframe and built model off of that with Random Forest and n_estimators = 200.  I tried a few other parameter changes.  I did looks at the feature importance and it was interesting:
Parameter	Rank	Order	Rank order
koi_fpflag_co	0.10299467	3	1
koi_fpflag_nt	0.09892699	1	2
koi_fpflag_ss	0.06457147	2	3
koi_model_snr	0.05366791	27	4
koi_prad	0.04913764	20	5
koi_fpflag_ec	0.03764511	4	6
koi_steff_err1	0.03659002	30	7
koi_duration_err2	0.03477321	16	8
koi_prad_err1	0.03414754	21	9
koi_duration_err1	0.03374459	15	10
koi_prad_err2	0.03083586	22	11
koi_steff_err2	0.0300786	31	12
koi_time0bk_err2	0.02497026	10	13
koi_time0bk_err1	0.02377891	9	14
koi_duration	0.0224978	14	15
koi_period	0.02166467	5	16
koi_period_err1	0.01893682	6	17
koi_teq	0.01876141	23	18
koi_impact	0.01819337	11	19
koi_depth	0.0174576	17	20
koi_period_err2	0.01649239	7	21
koi_insol_err1	0.01648695	25	22
koi_depth_err1	0.01474057	18	23
koi_insol	0.01459884	24	24
koi_depth_err2	0.01402819	19	25
koi_time0bk	0.01362992	8	26
dec	0.0121237	39	27
ra	0.0117483	38	28
koi_impact_err2	0.01148896	13	29
koi_insol_err2	0.01129712	26	30
koi_srad_err1	0.01077269	36	31
koi_slogg_err2	0.01062553	34	32
koi_impact_err1	0.01061399	12	33
koi_kepmag	0.01005387	40	34
koi_steff	0.00967942	29	35
koi_slogg	0.00952907	32	36
koi_srad	0.00903537	35	37
koi_slogg_err1	0.00869145	33	38
koi_srad_err2	0.00826094	37	39
koi_tce_plnt_num	0.00272827	28	40
![image](https://user-images.githubusercontent.com/74890495/118577981-f922b480-b750-11eb-82de-61ba1f8268d3.png)

#model 4 has all the features.  Then minmax scaler and used SelectKBest to find the best features.  I started with 10 features and played around with that.  I ended up using K=15.  I tried k=20 and there was not much difference.  Used SVM with Grid search to look at different parameters.  I change dthe parameters in Grid Search a few times.  First I tried lower C values, And then lower Gamma.  I tried a few others that can not be used for linear so I had to comment out.  Ended up with almost 87%.  Saved and used this model.

