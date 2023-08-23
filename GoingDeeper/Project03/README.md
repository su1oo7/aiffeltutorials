# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 홍수정
- 리뷰어 : 최연석


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [X] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 네 평가 항목 3가지에 부합하고 있습니다.
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  > 평가문항과 상세기준을 기재했습니다.
  '''
  Project Rubric
  ~ 생략
  '''
  > INDEX를 추가하여 코드 이해하는데 도움이 되었습니다.
  ''' 
  데이터 로드 및 전처리
  모델 구축 및 학습
  CAM feature map 확인
  grad-CAM feature map 확인
  CAM vs grad-CAM
  Draw bbox
  Calculate IOU
  (additional) trainded model with cutmix
  실패노트
  ''' 
- [X] 코드가 에러를 유발할 가능성이 없나요?
  > 에러를 방생시키지 않고 작동이 원할하게 되었으며 테스트시 실패코드에 대해 따로 기재하였습니다.
- [X] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 결과에 대한 해석을 추가하여 작성자가 코드에 대한 이해를 하고 작성한 것을 알 수 있습니다.
- [X] 코드가 간결한가요?
  > 네 필요 부분 함수화를 하여 간결히 작성하였씁니다.

# 참고 링크 및 코드 개선
```python
실패 노트에서
mix_2_labels에서 image_a.shape호출시 image_a 대한 정보가 없습니다. image_a를 parameter에 넣거나 고정 shape으로 주면 해결될 듯 합니다.
```
