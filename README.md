# 이미지 생성 모델
---
> main.py -> 학습과 샘플링, 설명 입력하여 이미지 생성 기능
> - 학습의 경우는 image encoder과 text encoder은 제외
> 
> main_finetune.py -> 설명 입력하여 이미지 생성하는 기능을 제외하고 같은 기능 제공
> - 학습의 경우 netD, netG, image encoder, text encoder전부 포함
> 
> [Text2Image](https://github.com/wtliao/text2image)를 이용해 조금 수정하여 기능 구현.
> 
> 새로운 데이터를 사용할 때 필요한 캡션 생성코드는 추후 업로드 예정
> - 지금은 colab에 .ipynb파일로 구현되어있다.
> 
> mscoco 데이터셋과 CUB 데이터셋으로 사전학습 된 모델을 pororoSV데이터셋으로 finetuning하여 사용하였다.
> 
> 생성되는 이미지의 해상도는 256*256 이다.
> 
> 현재 계속 훈련하며 성능을 높이기 위해 노력중.
