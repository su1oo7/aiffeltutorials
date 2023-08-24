# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 홍수정
- 리뷰어 : 어윤석


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [X] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 코드가 정상적으로 동작하고 평가문항의 모든 기준을 수행하였습니다.
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  > 필요한 내용에 주석으로 설명이 되어있어 코드를 이해하는데 도움이 되었습니다.
- [X] 코드가 에러를 유발할 가능성이 없나요?
  > 에러를 유발할 것 같은 코드를 발견하지 못했습니다.
- [X] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 코드를 잘 이해하고 작성하였습니다.
- [X] 코드가 간결한가요?
  > 기능에 필요한 코드로 간결하게 작성되었습니다.

# 예시
1. 코드의 작동 방식을 주석으로 기록합니다.
2. 코드의 작동 방식에 대한 개선 방법을 주석으로 기록합니다.
3. 참고한 링크 및 ChatGPT 프롬프트 명령어가 있다면 주석으로 남겨주세요.
### bounding box의 height기준 확인 등 kitti 데이터셋에 대한 분석을 체계적으로 진행하였습니다.
```python
def visualize_reverse_bbox(input_image, object_bbox):
    input_image = copy.deepcopy(input_image)
    draw = ImageDraw.Draw(input_image)
    
    # 바운딩 박스 좌표(x_min, x_max, y_min, y_max) 구하기
    width, height = img.size
    x_min = object_bbox[:,1] * width
    x_max = object_bbox[:,3] * width
    # 좌표 원점 기존 사분면 위치라 image 영점과 일치하지 않음
    y_min = (object_bbox[:,0]) * height
    y_max = (object_bbox[:,2]) * height
    
    # 바운딩 박스 그리기
    rects = np.stack([x_min, y_min, x_max, y_max], axis=1)
    for _rect in rects:
        draw.rectangle(_rect, outline=(255,0,0), width=5)

    return input_image
```
### epoch 15회 학습하고 loss, val_loss 결과를 시각화하였습니다.
```python
plt.figure(figsize=(7,5))
plt.plot(range(len(history.history['loss'])), history.history['loss'],label = 'loss')
plt.plot(range(len(history.history['val_loss'])), history.history['val_loss'],label = 'val_'+'loss')
plt.title('Training and Validation Loss')
plt.legend()
plt.show()
```

# 참고 링크 및 코드 개선
```python
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
