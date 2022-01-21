# Readme

## Introduction

In this project, we will use machine learning models to investigate the correlations and patterns behind stock closing prices and candidate data.  We use the LASSO regression algorithm to extract the factors in the dataset that have a high correlation with the closing prices, and then use Support Vector Regression and Kernel ridge regression to fit and predict the closing prices of Amazon and China The closing prices of Amazon and Ping An Bank Co. The accuracy of the final prediction is over 85%. 

## Install

- **Running environment: **Google Colaboratory

  If you are also using Google colaboratory, then the following installation packages can be installed without it, as they are already pre-installed on colab.

  If not, the following modules need to be pre-installed

- The modules used in this project are listed below. Go check them out if you don't have them locally installed.

  - Numpy

  - Pandas

  - Matplotlib

  - Sklearn

  - jqdatasdk

     - Make sure to update and install the newest version of JoinQuant Local SDK on your computer environment or using Anaconda prompt and type: 

       `sudo pip3 install jqdatasdk` 

      - Details: [Install JQData on your local computer](https://www.joinquant.com/view/community/detail/cdf86c624992fc86ed51d920ef8c637b)

    In addition, JointQuant requires an account in advance in order to download the relevant stock factor data.**you should apply for an account at JointQuant to allow you log in and access the authentication of the API.**

    - Guideline: [Apply for a JoinQuant account](https://www.joinquant.com/default/index/sdk?utm_campaign=JQData%E7%94%B3%E8%AF%B7&utm_medium=%E7%BD%91%E9%A1%B5&utm_source=%E8%81%9A%E5%AE%BD&gio_link_id=xRxqAjP5) 


Finally, Congratulation! You are ready to go.

## Usage

### Data_Crawling

- Open `Data_Crawling.ipynb`

- Fill out the information with your personal account in the code.
  `JointQuant_UserName`: Your_UserName
  `JoinQuant_Password`: Your_Password

-  Define and specify the start_date & end_date of the data

  Note: Define the range of dates in minutes separately

Run the program and the obtained data will be exported in **xlsx** format.

Note: It's okay if you don't have an account, the data needed for the project has been obtained and processed by the window function. The data is stored in the DataSource folder and can be used directly for subsequent use.

### Feature_Selection (LASSO)

- Open `Feature_Select_Lasso.ipynb`

#### Using Diabetes dataset as the testing part

Simply run the blocks in sequence and the results will be displayed step by step.

#### Using Real Dataset for feature selection

- **Select features from 30 factors (PingAn Bank)**
  - Fill the file_path with the absolute path of file *PingAnBank_daily.xlsx*, which is under /DataSource/PingAnBank.
  - Run the blocks in sequence.

- **Select features from 129 factors (PingAn Bank)**
  - Fill the file_path with the absolute path of file *PingAnBank_All.xlsx*, which is under /DataSource/PingAnBank.
  - Run the blocks in sequence.

### Regression (SVR&KRR)

- **Using Amazon Dataset**

  - Open `SVR&KRR_Amazon.ipynb`

  - Fill the file_path with the absolute path of file *Amazon*, which is under /DataSource.
  - Run the blocks in sequence.

  Note: In SVM and KRR part, the model parameters have been tuned and pre-set, if you want to tune the parameters by yourself, you can change the `grid_svr` and `grid_krr` to `GridSearchCV`， and the range of tuned parameters can be changed in C_svr, gamma_svr, alpha_krr and gamma_krr. 

  ```python
  # SVM
  grid_svr = GridSearchCV(SVR(), parameters_svr, cv = 5, verbose = 1)
  # grid_svr = SVR(kernel = 'rbf', gamma = 1e-5, C = 1e4)
  
  # KRR
  grid_krr = GridSearchCV(KernelRidge(), parameters_krr, cv = 5, verbose = 1)
  # grid_krr = KernelRidge(kernel='rbf', alpha=1e-05, gamma=0.0001)
  ```

- **Using PingAn Dataset (30 factors) **
  - Open `SVR&KRR_PingAn.ipynb`
  - Fill the file_path with the absolute path of file *PingAnBank*, which is under /DataSource.
  - Run the blocks in sequence.
- **Using PingAn Dataset (129 factors) **
  - Open `SVR&KRR_PingAn_only_factors.ipynb`
  - Fill the file_path with the absolute path of file *only_factors*, which is under /DataSource/PingAnBank.
  - Run the blocks in sequence.