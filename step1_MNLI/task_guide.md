## 준비

------

수업 중에 사용했던 실습 자료들을 참고하셔서 이번 과제를 수행하시면 됩니다:

[Google Colab](https://colab.research.google.com/drive/1iIhvEqckb-eDT5uhS92rnod2EVjSfj6K?usp=drive_link)



## 목표

------

이번 과제는 자연어 task 중 하나인 MNLI를 해결하는 모델을 HuggingFace로 학습하는 것입니다. MNLI를 요약하면 다음과 같습니다.

- **입력**: premise에 해당하는 문장과 hypothesis에 해당하는 문장 두 개가 입력으로 들어옵니다.

- 출력:

   분류 문제로, 두 문장이 들어왔을 때 다음 세 가지를 예측하시면 됩니다.

  - **Entailment:** 두 문장에 논리적 모순이 없습니다.
  - **Neutral:** 두 문장은 논리적으로 관련이 없습니다.
  - **Contradiction:** 두 문장 사이에 논리적 모순이 존재합니다.

이 때, 다음 요구사항이 담긴 colab notebook을 만들어내시면 됩니다:

- [ ]  

  ```
  load_dataset("nyu-mll/glue", "mnli")
  ```

   로 dataset을 불러옵니다.

  - 학습 때는 `train` split만 활용하셔야 합니다. 나머지 split은 사용불가입니다.
  - Validation data가 필요한 경우, `train` split에서 가져오셔야 합니다.

- [ ]  `trainer.train()`를 통해 학습된 log가 남아있어야 합니다.

- [ ]  Dataset의 `validation_matched`에 대한 성능을 출력하고, 50%를 넘기셔야 합니다.

이전 과제와 똑같이 validation data 유무, 모델 architecture, hyper-parameter 등은 위의 조건만 만족한다는 가정 하에서 마음대로 수정하셔도 됩니다.

## 제출자료

------

위의 요구사항들이 만족된 notebook을 public github repository에 업로드하여 공유해주시면 됩니다(**반드시 출력 결과가 남아있어야 합니다!!**).

