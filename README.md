# predictive-modeling
고객 이탈예측 모델생성

# 데이터 전처리
1. 결측치를 확인해본 결과 결측치가 없어 결측치에 대한 전처리는 진행되지 않았다.
2. grade가 'G011','G012' 와 같이 문자로 표기되어있어 해당부분을 '1','2'와 같이 정수형으로 변경하였다.



# 모델학습
1. 저학년 (남자, 여자), 고학년 (남자, 여자)에 따라 이탈에 중요하게 작용하는 요소가 다를 것이라 예상하고 4개의 그룹으로 나누어 모델학습을 진행하였다.
2. 학습결과 이탈에 관여하는 요소는 대부분 비슷하게 나타나는 것을 확인하였다.
3. 이중 저학년 여자그룹에 대해 모델 성능을 개선하고자 중요도가 낮다고 판단되는 'media_action_cnt_sum' 요소를 제외하고 재학습을 진행하였다.

 # 학습결과
 1. 학습결과 recall 값이 소폭 상승하는것으로 보아 실제로 이탈할것이라 예상되는 인원의 관리가 더욱 잘 될것이라 판단되며 이는 곳 모델의 성능이 높아졌다고 볼 수 있다.
    * 재학습 전 저학년 여자그룹 결과
      <p align="center">
        <img src="image/변경전 저학년 여자.png" weight = 500>
      </p>
      
    * 재학습 후 저학년 여자그룹 결과
      <p align="center">
        <img src="image/변경후 저학년 여자.png" weight = 500>
      </p>

  2. 똑같은 요소를 제외하고 고학년 남자에 대해 적용해본 결과 저학년 여자그룹에서와는 달리 오히려 precision 값과, recall 값이 모두 낮게 나오는 것으로 나타났게 되었다.
     * 재학습 전 고학년 남자그룹 결과
       <p align="center">
        <img src="image/변경전 고학년 남자.png" weight = 500>
        </p>
     * 재학습 후 고학년 남자그룹 결과
       <p align="center">
        <img src="image/변경후 고학년 남자.png" weight = 500>
        </p>
    

  # 느낀점
  - 중요도가 낮은것을 제외한다해서 무조건적으로 모델의 성능이 개선되는것이 아님을 확인할 수 있었다.
  - 데이터 상에 이탈에 관련된 타겟이 현저히 적었으므로 예측을 하는데에 무리가 있다 판단되며 데이터셋이 지금보다 많아지게 되면 예측률이 증가할 수 있을것이라 기대된다.
  - 모델을 여러개로 나누지 않고 원핫 인코딩 등으로 구분하여 주었다면 여러번 학습하지 않고도 한번에 모델학습이 가능하여 더 수월하게 학습이 진행될 수 있었을 것으로 보인다.
