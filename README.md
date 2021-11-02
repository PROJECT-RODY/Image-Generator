# 이미지 생성 모델
---
- 훈련된 모델은 [링크](https://drive.google.com/drive/folders/1xPkj4Xd5DrvpeoA0xjXK1k7Fm57E6zZF?usp=sharing)의 Image-Generator압축파일을 내려받아 사용할 수 있다.
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
---
### 추후 사용을 위해선
>
> 같은 경로에 data폴더를 생성하고 데이터 셋을 구성한다.
> - 디스크립션기반으로 캡션을 생성하는 것은 "뽀로로 학습을 위한 캡션_파일명 저장.ipynb"를 참고한다. captions.pickle, filenames.pickle의 생성 코드가 정리되어있다.
> 
> 훈련의 경우는 main_finetune.py를 사용하여 훈련하면 image_encoder와 text_encoder를 추가적으로 함께 학습시킬 수 있다.
> -  netG, netD는 main.py에서도 훈련 시킬 수 있다.
> 
> 세부적인 설정은 ./cfg/*.yml 파일에 작성되어 있으며 각각 훈련하는 데이터 명으로 작성되어있다.
> - "B_VALIDATION: True" 일때는 가지고 있는 데이터의 디스크립션 기반으로 샘플이미지를 생성한다. False일땐 모델이 훈련 한다.
>  
> - "RESTORE: True" 일때 이미 훈련한 모델을 로드해서 추가적으로 훈련시킨다. False라면 초기 모델부터 다시 훈련을 진행한다.
>  
> 훈련 후 모델들이 저장되는 경로는 ./tmp/"data_name"_sloss01/64/models 디텍토리에 저장된다.
> 
> ### requirements.yaml 을 이용해 동일한 환경의 가상환경을 셋팅할 수 있다.
> 
> 
> 
