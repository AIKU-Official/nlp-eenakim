# nlp-eenakim
AIKU 2023-Summer Project: AI 김이나 만들기
----

# 💿프로젝트 소개
---
Target Task - 오디오 input -> 음절과 오디오 데이터의 분위기를 고려해 가사 텍스트 output 생성을 목표로 하는 프로젝트입니다.


기존 target과는 조금 다른 방향으로, text input을 넣으면 그에 맞는 가사 text output을 주도록 task를 일부 수정하였습니다.


프로젝트는 크게 두 가지 트랙으로 나누어 진행했습니다.

# 1️⃣Track 1 - Generating Lyrics with Fine-tuned KoBART
---
Encoder - Decoder 구조의 KoBART를 Fine-tune 하여 음절 수에 맞는 가사를 생성하도록 했습니다.


![image](https://github.com/AIKU-Official/nlp-eenakim/assets/137471403/4e621219-698d-4f2a-8325-7eb664341ec8)
위 사진과 같이 한국어 기준의 음절을 숫자로 입력하면, 음절 수에 맞는 가사를 생성하도록 Fine-Tune 하였습니다.



# 2️⃣Track 2 - Generating Lyrics with Fine-tuned KoGPT2
---

Decoder - only 구조의 KoGPT2를 Fine-tune 하여 평서문 형태의 가사와 장르를 input하면, 그 장르에 맞게 가사 input text를 가사로 다시 써서 생성해주도록 하였습니다.
![image](https://github.com/AIKU-Official/nlp-eenakim/assets/137471403/c7a3a9d4-3cfd-4ac0-8e26-6c52e7b297ad)

(...Track 2의 경우,Fine-tuning이 깔끔하게 되지 않았습니다.)



# 3️⃣Track 3 - Audio-based Approach : LSTM , RNN, and SongMASS
---
LSTM - LSTM 구조의 모델을 통해 audio input data를 가공하여 라벨이 일치하는 text output을 생성하도록 학습하는 것이 목표였습니다. 


RNN - <https://github.com/malikudit/LSTM-RNN-lyrics-generator/blob/master/lyrics.py> 를 재구현하여 audio-to-lyrics를 실현하는 것이 목표였습니다.


SongMASS - <https://github.com/microsoft/muzic/tree/main/songmass> 의 재구현을 시도하였습니다.



# ⭐ Dataset
---
Track 1 - 멜론 크롤링 가사 데이터셋
Track 2 - 멜론 Top 50 스테디셀러 (락/발라드/댄스/트로트) 장르별 크롤링 가사 데이터셋 (train)
          멜론 Top 50 스테디셀러 (락/발라드/댄스/트로트) 장르별 크롤링 가사 데이터셋 (val)

# ⭐ Models used
---
Track 1 - [SKT-AI/KoBART] (https://github.com/SKT-AI/KoBART/)


Track 2 - [SKT-AI/KoGPT2] (https://github.com/SKT-AI/KoGPT2/)

# ⭐ Train Epochs
---
Track 1 - 4 Epochs


Track 2 - 15 Epochs






