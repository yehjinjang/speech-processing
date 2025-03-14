## 🎙️ 음성 감정 분석 프로젝트

### 📌 프로젝트 개요
이 프로젝트는 CNN과 LSTM을 활용하여 음성 데이터를 기반으로 감정을 분석하는 딥러닝 모델을 개발하는 프로젝트입니다. 다양한 음성 특징(MFCC, Zero-Crossing Rate, Chroma 등)을 추출하고, Soft Voting 앙상블 기법을 적용하여 최적의 성능을 달성하였습니다.

---

### 📂 프로젝트 구조
```
├── speech-emotion.ipynb  
├── /data                #ignore 
├── /models               
├── /new-recorded        #ignore
├── .gitignore         
├── README.md            
```

---

### 🛠️ 사용 기술
- **프로그래밍 언어:** Python
- **딥러닝 프레임워크:** TensorFlow, Keras
- **음성 데이터 처리:** Librosa
- **데이터 저장 및 처리:** Pandas, NumPy
- **실시간 오디오 녹음:** Sounddevice, Soundfile

---

### 📊 모델 개요
이 프로젝트에서는 CNN과 LSTM 모델을 개별적으로 학습한 후, **Soft Voting 앙상블 기법**을 적용하여 최적의 성능을 도출했습니다.

#### **1️⃣ CNN 모델**
- **입력:** Mel Spectrogram
- **구성:** Conv1D → MaxPooling → Dense → Softmax
- **역할:** 음성의 주파수 기반 패턴을 분석

#### **2️⃣ LSTM 모델**
- **입력:** MFCC, Zero-Crossing Rate, Chroma Features
- **구성:** LSTM → Dense → Softmax
- **역할:** 음성의 시간적 흐름을 반영하여 감정 예측

#### **3️⃣ Soft Voting 앙상블**
- CNN과 LSTM 모델의 **출력 확률을 평균 내어 최종 감정 결정**
- **결과:** CNN과 LSTM의 장점을 결합하여 **96% 정확도** 달성

---

### 🎤 실시간 감정 분석 기능
이 프로젝트는 **실시간 음성 감정 분석 기능**을 지원합니다.

#### **✅ 실행 방법 (Jupyter Notebook 사용)**
```bash
jupyter notebook
```
- `speech-emotion.ipynb` 파일을 열어 순차적으로 실행하면 됩니다.
- 마이크를 통해 3초간 녹음 후 감정을 예측합니다.
- `new-recorded/` 폴더에 녹음된 파일이 저장됩니다.
---

### 📌 참고자료
- [Librosa Documentation](https://librosa.org/doc/latest/index.html)
- [TensorFlow Documentation](https://www.tensorflow.org/)
- [SoundDevice Documentation](https://python-sounddevice.readthedocs.io/)
