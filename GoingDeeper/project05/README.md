# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 홍수정
- 리뷰어 : 이수봉


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [X] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  > 네, 간단한 주석을 통해서 코드를 이해할 수 있었습니다.
- [X] 코드가 에러를 유발할 가능성이 없나요?
  > 네, 에러를 유발할 가능성이 없습니다.
- [X] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > Unet, Unet++의 구조를 이해하고 코드를 작성한 것 같았습니다.
- [X] 코드가 간결한가요?
  > 네 불필요한 코드없이 간결하였습니다.

# 예시
1. 코드의 작동 방식을 주석으로 기록합니다.
2. 코드의 작동 방식에 대한 개선 방법을 주석으로 기록합니다.
3. 참고한 링크 및 ChatGPT 프롬프트 명령어가 있다면 주석으로 남겨주세요.
```python
def display(display_list, titles=[], display_string=None):
    ''' displays list of images/masks'''
    plt.figure(figsize=(15,7))
 
    for i in range(len(display_list)):
        plt.subplot(1, len(display_list), i+1)
        plt.title(titles[i])
        plt.xticks([])
        plt.yticks([])
        if display_string and i == 1:
            plt.xlabel(display_string, fontsize=12)
        try:
            img_arr = tf.keras.preprocessing.image.array_to_img(display_list[i])
        except: # mask => 1-channel
            img_arr = display_list[i]
        plt.imshow(img_arr)
    
    plt.show()

def show_image_from_dataset(dataset):
    for image, mask in dataset:
        sample_image, sample_mask = image, mask
        break
    display([sample_image[0], sample_mask[0]], titles=['Image', 'True Maks'])

# 마스크 이미지를 시각화 해서 보여준 부분이 인상깊었습니다.
# 학습 중간 과정을 회고를 해서 정리해둔 부분이 인상깊었습니다.
```

# 참고 링크 및 코드 개선
```python
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```
