## DLThon : Motocycle night rides.

- TASK : Semanic segmentation

- Team : 어수수 (팀장 홍수정, 팀원 어윤석)

- Model : U-Net, U-Net++, SegFormer, GPS-GLASS

- Metrics : mIOU, pixel accuracy

- ipynb

1. moto_unet.ipynb
   : Unet/Unet++ 실험 (학습 O)
3. moto_pretrained_segformer.ipynb
   : [SegFormer](https://github.com/huggingface/transformers/) 실험 (학습 O)
5. moto_pretrained_gps_glass.ipynb
   : [GPS-GLASS](https://github.com/jimmy9704/GPS-GLASS/tree/main) 예측 (학습 X)
6. moto_linemark_pretrained_unet.ipynb
   : [Unet](https://github.com/Frostday/Lane-Segmentation) 예측 (학습 X, linemark specific)
