# MiraeAssetHackathon
After Learner Project


import pandas as pd
import os
import datetime
import time
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
date_time2: str = ""
    # 2023_01 : 2023_06
date_time1: str = ""
    # 202301 : 202306

    # 1.
    # str(date_time2).replace("_", "")
    # 일단 string에 _있는 버전으로 date_time2 설정 후
    # 공백처리하여 date_time1 설정

    # 2.
    # 아니면 202301을 정수형으로 설정한 후 date_time += 1을 통해 설정
    # date_time1에서 4자리 수 뒤에 "_" 추가하는 방식으로 date_time2 생성

    # 3.
    # 문제는 DATE_TIME 컬럼이 YYYYMMDD_HHmmSS형식이라는 점
    # 6개의 xlsx 확장자 데이터(파일 크기를 고려할 때)를 어떻게 메모리 공간에
    # 부담이 가지 않도록 병합하여 활용할지가 관건

AInews_data = pd.DataFrame()

for date_time1 in range(202301, 202307, 1):
    date_time2 = str(date_time1).replace("0", "_0")
    PointofView = SearchEventPattern(
        news_data_path = f"/content/drive/MyDrive/AfterLearnerProject/DataArchive/news_dataset_{date_time1}/2023BigFesta+News_{date_time2}_5.xlsx")
    AInews_datetime = PointofView.loadAInewsData()
    AInews_data = pd.concat(
        [AInews_data, AInews_datetime], axis = 0, ignore_index = True)
    time.sleep(1)



# def main():
# if __name__ == "__main__": main()
