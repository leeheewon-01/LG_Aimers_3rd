# LG_Aimers_3rd

## 1. Preprocess
- train.csv와 메타 데이터를 transpose하여, stack하는 방법을 사용하였습니다.

## 2. nparray_preprocessing
- 만들어진 csv 파일을 바탕으로, train / test set을 만듭니다.

## 3. Linear_SAM_id_ensemble
- Dlinear 모델을 사용하며, ASAM minimizer를 사용하고, PSFA metric의 특징에 맞게, mseloss에 비대칭을 준 loss function을 사용하여 training 합니다.
- train set으로 학습할 때, id로 stratify를 하여 10개의 모델을 학습합니다.

## 4. ensemble
- 만들어진 10개의 결과물을 산술 평균을 내어 ensemble합니다.

## 5. submit after process
- train.csv의 마지막 90일 데이터의 최댓값과 최솟값을 추출하여, submit 파일에 threshold를 적용합니다.
