
## Unet segmentation 실험 

전체 ipynb이 200 mb가 넘어 분할 업로드

quest는 ipynb 용량 문제로 루브릭에 근거해 해당 experiment에서 실험2번 부분을 발췌

2차까지의 최종 결과(seed 고정 후)

|model|Threshold 0.5 iou |
|:--:|:--:|
|U-net(drop=False)|0.0|
|U-net(drop=True)|0.638|
|U-net++(deep_supervision=False)|**0.732**|
|U-net++(deep_supervision=True)|0.0|

*bold : hightest score

seed 고정 후 'unet++'가 가장 높은 수치를 기록함.
(prediction threshold 0.5 기준)
이 결과를 비추어 볼 때, parameter가 더 높았던 unet++이 segmentation에 더 유리했던 것으로 생각된다.
unet도 threshold를 내렸으면 사용할 만한 모델이었을테지만,비교실험인 관계로 기준을 0.5로 기준해서 iou가 0으로 나왔음.

### 실험 1. 노드 그대로 데이터셋 구성 Unet 및 Unet++ 구현

`file: project15_unet_experiment_01.ipynb`

- U-net의 경우 dropout을 마지막 encoding 영역에서 적용하는 경우 augmentation 효과를 볼 수 있다는 얘기가 기억나서 if문 적용
    ```python
    # Comment by chatGPT
    ```
    ```
    Dropout을 U-Net의 인코딩 부분에 추가하는 것은 이러한 augmentation 효과를 시뮬레이션하는 아이디어입니다. U-Net에서는 인코딩 경로에서 특성을 계속 다운샘플링하면서 정보 손실이 발생할 수 있습니다. 이때 Dropout을 적용하면 특정 뉴런이 끄거나 켜져 다양한 경로를 통해 정보를 전달하게 됩니다. 이로 인해 네트워크가 다양한 경로를 통해 정보를 학습하며, 데이터의 다양성을 높일 수 있습니다.즉, Dropout을 적용함으로써 네트워크는 학습 데이터에만 의존하지 않고 다양한 경로를 통해 정보를 학습하게 되어 일종의 데이터 augmentation 효과를 얻을 수 있습니다. 이러한 방식은 모델의 일반화 능력을 향상시키고 과적합을 줄이는 데 도움을 줄 수 있습니다.
    ```

#### index
1. dataset 구성
    - 데이터 200개 => train 170 / valid 30 (indexing)
    - augmentation 적용 ( 랜덤 좌우대칭, 랜덤 crop )
    - image / mask 확인
2. 모델 구현 및 segmentation 확인
 2.1 U-net 구현
    2.1.1 unet no dropout
    2.1.2 unet dropout
 2.2 U-net++ 구현
    2.2.1 unet++ no deep_supervision
    2.2.2 unet++ deep_supervision
3. 1차 실험결과 및 중간회고 

- 1차 실험 결과

|model|Threshold 0.5 iou |segmentation 경향|
|:--:|:--:|:--:|
|U-net(drop=False)|**0.778**|깔끔하게 segmentation 되는 편|
|U-net(drop=True)|0.773|객체 구별이 좀 더 엄격해서 iou가 낮은 느낌|
|U-net++(deep_supervision=False)|**0.657**|길은 좀 더 잘 구별하는 느낌이지만 dot 느낌의 노이즈가 있음|
|U-net++(deep_supervision=True)|0.0| threshold 0.1 부근에서야 도로를 예측함 .>segmentation이 거의 안됨|
*bold : hightest score in model

### 실험 2. 학습하지 않은 데이터 segmentation 능력확인

`file1: project15_unet_experiment_02_unet.ipynb`
`file2: project15_unet_experiment_02_unet++.ipynb`

- 실험2에서 testset 20장 데이터 segmentation 내용 전부를 그린 결과 정리 후에도 50 mb라서 파일 분리 (각각 ipynb에 서로의 link 첨부)

#### index
1. dataset 구성
    - 데이터 200개 => train 150 / valid 30 / test 20 (indexing)
    - augmentation 적용 ( 랜덤 좌우대칭, 랜덤 crop )
    - image / mask 확인
2. segmentation 확인
 2.1 U-net
    2.1.1 unet no dropout
    2.1.2 unet dropout
 2.2 U-net++
    2.2.1 unet++ no deep_supervision
    2.2.2 unet++ deep_supervision
3. 2차 실험결과 및 중간회고 

- 2차 실험 결과
    
|model|Threshold 0.5 iou |
|:--:|:--:|
|U-net(drop=False)|`0.685`|
|U-net(drop=True)|**0.713**|
|U-net++(deep_supervision=False)|0.709|
|U-net++(deep_supervision=True)|0.0|
*bold : hightest score
*block : discuss in disccusion

### 실험 3. Custom loss 사용 (bce_dice) 
: 용량 정리 되는대로 업로드 예정

`file: project15_unet_experiment_03.ipynb`

- Unet++ 논문에서 해당 loss를 사용하는 것을 확인하고 적용 실험

#### index
1. dataset 구성 및 모델 정의
    - 데이터 200개 => train 150 / valid 30 / test 20 (indexing)
    - augmentation 적용 ( 랜덤 좌우대칭, 랜덤 crop )
    - image / mask 확인
2. custom loss 정의
3. custom loss 적용 segmentation 확인
3.1 U-net
    3.1.1 unet no dropout
    3.1.2 unet dropout
 3.2 U-net++
    3.2.1 unet++ no deep_supervision
    3.2.2 unet++ deep_supervision
4. 3차 실험결과 및 최종 회고 

    
