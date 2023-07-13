# MiraeAssetHackathon
After Learner Project


import pandas as pd
import os
import datetime
import numpy as np
from typing import *

marketIndex_linearPCA = pd.DataFrame()
    # class PrincipalComponentAnalysis에 file_path 설정하여 생성한 PCAinstance 객체의
    # linearCombinationPCA()메서드에 제1주성분으로 5차원축소하도록 k = 1로 설정했을 때
    # return된 2022-12-01부터 2023-04-30까지의 시계열 데이터프레임

class SearchEventPattern():

    def __init__(self, news_data_path):
        self.AInews_data = pd.read_excel(
            news_data_path, index_col = False)

    def loadAInewsData(self):
        return self.AInews_data



# date_time_list = datetime.datetime.strptime("2023-01", "%Y%m") + relativedelta(month = 1)
date_time1: str = ""
    # 202301 : 202306
date_time2: str = ""
    # 2023_01 : 2023_06

PointofView = SearchEventPattern(
    news_data_path = f"/content/drive/MyDrive/AfterLearnerProject/DataArchive/news_dataset_{date_time1}/2023BigFesta+News_{date_time2}_5.xlsx")
PointofView.loadAInewsData()
    # 문제는 DATE_TIME 컬럼이 YYYYMMDD_HHmmSS형식이라는 점
    # 6개의 xlsx 확장자 데이터(파일 크기를 고려할 때)를 어떻게 메모리 공간에 
    # 부담이 가지 않도록 병합하여 활용할지가 관건
    

