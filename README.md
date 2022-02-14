# music_vae_drum_4bar
colab 환경에서 magenta를 활용해 MusicVAE 모델 학습 후 4bar 비트 생성하기

## process

1. 데이터셋 다운로드

  - [groove dataset](https://magenta.tensorflow.org/datasets/groove) 에서 `groove-v1.0.0-midionly.zip` 다운로드

2. 전처리 (midi to tfrecord)

  - magenta/script/convert_dir_to_note_sequences 를 활용하여 midi 파일을 tfrecord 형태로 변환


4. 학습

  - magenta/models/musicvae/music_vae_train

  - 직접 생성한 전처리 데이터셋 또는 tfds에서 제공하는 `groove/4bar-midionly`를 사용하여 학습할 수 있음

5. 생성 ( model.sample 또는 interpolate)

  - 학습된 weight를 활용하여 샘플 생성
  - 기존에 있는 비트 2개로 보간하여 새로운 샘플 생성
  - 모델은 직접 학습한 weight 또는 magenta에서 제공하는 사전학습모델 (groovae_4bar) 활용

### reference
---
- [paper](https://arxiv.org/pdf/1803.05428.pdf)
- [magenta/musicvae](https://github.com/magenta/magenta/tree/main/magenta/models/music_vae)
- [groove dataset](https://magenta.tensorflow.org/datasets/groove)



