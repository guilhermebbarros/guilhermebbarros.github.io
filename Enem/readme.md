# Enem - How socioeconomic factors are tied to the final score 

In this project, I used data provided by the Brazilian government with the aim of analyzing how the scores of the National High School Exam (ENEM, in Portuguese) are related to the socioeconomic conditions of the students. 

Most commonly, graduating high school students take this exam aiming to enter a highly-regarded public university - most of them use ENEM as the one and only method of entrance. For that reason, a large number of candidates take the test every year - in 2014, about 9.5 million took the exam. The ENEM data provides a very interesting way of analyzing Brazilian education in general - all its idiosyncrasies, injustices, strengths and weaknesses. For that reason, I chose to spend some time analyzing this data. 

My goals with this project were:
1. To clean the data set and to make it usable for my analysis purposes.
2. To analyze how different socioeconomic factors influence the ENEM scores. 
3. To train machine learning models to predict the scores based on socioeconomic factors. It is not my intention here to predict any particular score - the score itself depends on many features that are symply not available to us, and on the candidate itself. Nonetheless, the features should be somehow correlated with the scores - making it possible to construct a machine learning model that predicts, with some accuracy, the scores of candidates, as long as we have a large number of observations.

# Files

The Enem.ipynp file is a Jupyter Notebook containing the code and the analysis of the data.

The Dicionário_Microdados_Enem_2014.xlsx file is a dictionary that should be used to understand the columns of the data used. For example, some columns represent the candidate's answer to the socioeconomic questionaire, and their names are just 'Q001', 'Q002' etc. in the file. In order to find out what each column means, look at the dictionary for answers. Some of the most important features will be explained in the notebook.

The data that I used could not be uploaded to this folder, due to its size. Nevertheless, the data is publicly available and can be accessed in https://dados.gov.br/dataset/microdados-do-exame-nacional-do-ensino-medio-enem/resource/94731b73-e9f1-4262-b8d6-479b6d02a6f0 .

# Conclusion

The EDA performed in the notebook helped us elucidate some points about how socioeconomic factors may are correlated with the ENEM score. We see that the average scores are strongly correlated with the family income (and hence, the class) of the candidates. The differences in school type (that is, if the school is private or public) also seem to have an impact on the average score. However, this seems to be less predictive of the final ENEM score, since in general higher income families send their children to private schools. In fact, when we plot a bar plot for the average scores for public and private schools for each income bracket, we can see that the public/private school divide is more predictive of the score for lower income candidates, while the difference between school types tends to decrease as the income gets higher.

The region of the country where the student lives also has an influence on the average score. The region with the highest average score is the Southeast. Only two regions (Southeast and South) have an average score greater than 500. The North is the region with the lowest score. 

I also tried to create machine learning models that attempted to predict the scores based on some socieconomic features. First, I trained a random forest, with 40 estimators (that proved to be a satisfactory number of estimators in my analysis). In average, the model got the average score wrong by 51.3 points (RMSE 64.9). There was clearly something to be learned by our model here - the model's accuracy increases with the number of estimators, and the graph shows that it captures general trends in the population score. Furthermore, I trained a neural network. I used 5 hidden layers, with 8 nodes each. The results were not much different from the random forest ones (mean absolute error 51.4 and RMSE 65). This shows that the random forest is a very good model to predict the ENEM scores. 

It should be pointed out that trying to predict the scores of an exam is an intrinsecally tricky affair. We can never have access to all variables that are important to the problem in hand - individual factors not taken into account in our analyses play a huge role. It was never my intention, in this project, to claim that any individual ENEM score can be predicted with any level of accuracy. The intention was to detect general trends and show that the some features are reasonable predictors of the scores, when a large group is taken into account. 
