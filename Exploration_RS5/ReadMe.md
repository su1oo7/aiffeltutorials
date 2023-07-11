# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 홍수정
- 리뷰어 : 최연석


# PRT(PeerReviewTemplate) - Bike_Sharing_Demand_Prediction
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [X] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  > 주석과 작성한 코드의 결과값을 바로 확인할 수 있게 작성하여 이해하기 쉬웠습니다.
  > ```
  > type(df_X), type(df_y), df_X.shape, df_y.shape
  > (numpy.ndarray, numpy.ndarray, (442, 10), (442,))
  > ```
- [X] 코드가 에러를 유발할 가능성이 없나요?
  > 런타임 시 오류가 발생하지 않을 것으로 예상 됩니다
- [X] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 데이터 호출부터 분할 학습등 해당 데이터 분석에 맞는 순서로 작성하여 이해하고 작성하였다고 할 수 있습니다.
  > LEARNING_RATE = 0.5등 loss값을 줄이기 위해 인자값을 조절하였습니다.
- [X] 코드가 간결한가요?
  > 다음과 같이 기능별로 코드를 구분하여 재사용성 및 가독성을 증가시켰습니다.
  > ```
  > def model(X, W, b):
  > def MSE(a, b):
  > def loss(X, W, b, y):
  > def gradient(X, W, b, y):
  > ```


# PRT(PeerReviewTemplate) - Multiple_Linear_Regression_for_predicting_diabetes
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [X] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  > 주석과 작성한 코드의 결과값을 바로 확인할 수 있게 작성하여 이해하기 쉬웠습니다.
  > ```
  >  # 각 항목의 세부 개수 확인
    train['year'].value_counts().plot.bar()
    plt.title('rental history per year')
    ```
- [X] 코드가 에러를 유발할 가능성이 없나요?
  > 런타임 시 오류가 발생하지 않을 것으로 예상 됩니다
- [X] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 데이터 호출부터 분할 학습등 해당 데이터 분석에 맞는 순서로 작성하여 이해하고 작성하였다고 할 수 있습니다.
  > RMSE 값을 줄이기 위해 필요없는 dtemp 컬럼 제거등을 하였습니다.
    ```
    del train['dtemp']
    ```
- [X] 코드가 간결한가요?
  > 작성한 코드별 시각화를 하여 간결하게 볼 수 있습니다.
  > ```
    wedgeprops={'width': 0.7, 'edgecolor': 'w', 'linewidth': 5}
    plt.pie(train['hour'].value_counts().sort_index(), labels = train['hour'].value_counts().sort_index().index,
            autopct = '%.1f%%',
            wedgeprops = wedgeprops )
    plt.show()  
    train[train.holiday==1].hour.value_counts().sort_index().plot.bar()
    train['dtemp'] = train['atemp'] - train['temp'] # 체감과 실제온도에 대한 값에 대한 차이 확인
    train['dtemp'].plot.hist(bins = 30)
    plt.show()
    train[train['dtemp']<0].shape
    sns.scatterplot(res, x ='true', y = 'pred')
    ```


# 참고 링크 및 코드 개선
파일 호출시 예외 처리 추가
```
try: 
  데이터 호출
except:
  예외처리
```
