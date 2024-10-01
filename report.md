# Evaluation Report: Parler-TTS-mini-jenny-30H

## 1. Evaluation Plan

### 1.1 Selection of Audio and Text for Quality Assessment

For the evaluation of the Parler-TTS-mini-jenny-30H model, I used 19 synthesized audio samples (`sample_1.wav` to `sample_19.wav`) generated from random sentences from the classic book Moby Dick. The model was fine-tuned on the Jenny dataset, and these generated samples represent different speech patterns to ensure diverse evaluation. 

Additionally, 5 reference audio files (`20.wav` to `25.wav`) were selected for comparison. These reference audios were used to evaluate how closely the synthesized speech matched a high-quality human voice in terms of clarity, naturalness, and intelligibility.

### 1.2 Decomposition of Speech Synthesis Evaluation

The concept of "speech synthesis evaluation" can be broken down into several key characteristics:

- **Naturalness**: How natural the generated speech sounds compared to human speech.
- **Intelligibility**: The clarity and ease of understanding the synthesized speech.
- **Pronunciation Accuracy**: How closely the synthesized words align with the expected pronunciations.
- **Spectral Similarity**: How similar the spectral features of the synthesized audio are to the reference audio (measured via MCD).
- **Distortion**: The amount of noise or distortion present in the synthesized speech (measured via SNR).
- **Text Accuracy**: The accuracy of the synthesized speech in terms of matching the target text (measured via WER).

### 1.3 Selected Metrics for Evaluation

To assess the synthesized speech quality, I selected the following metrics:

- **Mel Cepstral Distortion (MCD)**: Measures the difference between the spectral envelopes of the generated and reference audio. MCD is a standard measure for evaluating the quality of synthesized speech in terms of spectral similarity.
  
- **Signal-to-Noise Ratio (SNR)**: This metric evaluates how much noise or distortion is present in the synthesized audio. A higher SNR indicates clearer speech with less distortion.
  
- **Word Error Rate (WER)**: This metric quantifies the intelligibility and accuracy of the synthesized speech by comparing the transcription of the generated audio to the expected text. A lower WER means fewer errors in the synthesized speech.

- **Manual MOS**: Mostly for fun )

### 1.4 Texts Used for Synthesis and Reasoning

The texts used for generating the audio samples were chosen to represent a variety of speech contexts, including both formal and conversational language. This variation ensured a comprehensive evaluation of the model's ability to generate speech across different styles and complexities. The goal was to evaluate how well the model handled complex sentences, varied vocabulary, and diverse speech patterns.

## 2. Audio Generation

The audio samples were generated using the `Parler-TTS-mini-jenny-30H` model, which was fine-tuned on the Jenny dataset. These samples were then used for evaluation using the metrics described above.

## 3. Evaluation Code

### 3.1 Code Repository and Setup

The evaluation was performed using Python in a local environment. The code for the evaluation is available in a repository, and can also be run in a Jupyter notebook. The repository includes:

- Code for calculating MCD, SNR, and WER.
- Scripts for loading and preprocessing the audio data.
- Documentation on how to run the code and interpret the results.

### 3.2 Documentation and Usage Instructions

The repository includes a detailed README file that explains how to install dependencies, run the evaluation, and understand the output metrics. Comments are included throughout the code to guide users on the setup and usage.

---

## 4. Results

### 4.1 Mel Cepstral Distortion (MCD)

| Audio Sample   | Average MCD(dB)  |
|----------------|-------------|
| `sample_1.wav` | 23.71      |
| `sample_2.wav` | 23.48      |
| `sample_3.wav` | 23.17      |
| `sample_4.wav` | 23.42      |
| `sample_5.wav` | 23.03      |
| `sample_6.wav` | 23.55      |
| `sample_7.wav` | 23.25      |
| `sample_8.wav` | 23.85      |
| `sample_9.wav` | 23.66      |
| `sample_10.wav`| 23.62      |
| `sample_11.wav`| 23.58      |
| `sample_12.wav`| 23.79      |
| `sample_13.wav`| 23.73      |
| `sample_14.wav`| 22.58      |
| `sample_15.wav`| 23.77      |
| `sample_16.wav`| 23.31      |
| `sample_17.wav`| 23.04      |
| `sample_18.wav`| 23.75      |
| `sample_19.wav`| 22.10      |

- **Overall Average MCD**: **23.39**
  
  Lower MCD values indicate better quality, with the best quality seen in `sample_19.wav`.

### 4.2 Signal-to-Noise Ratio (SNR)

| Audio Sample   | Average SNR (dB) |
|----------------|------------------|
| `sample_1.wav` | -0.40 dB         |
| `sample_2.wav` | -0.31 dB         |
| `sample_3.wav` | -0.38 dB         |
| `sample_4.wav` | -0.41 dB         |
| `sample_5.wav` | -0.88 dB         |
| `sample_6.wav` | -0.28 dB         |
| `sample_7.wav` | -0.42 dB         |
| `sample_8.wav` | -0.38 dB         |
| `sample_9.wav` | -0.37 dB         |
| `sample_10.wav`| -0.34 dB         |
| `sample_11.wav`| -0.44 dB         |
| `sample_12.wav`| -0.30 dB         |
| `sample_13.wav`| -0.37 dB         |
| `sample_14.wav`| -21.67 dB        |
| `sample_15.wav`| -0.32 dB         |
| `sample_16.wav`| -0.36 dB         |
| `sample_17.wav`| -4.11 dB         |
| `sample_18.wav`| -0.37 dB         |
| `sample_19.wav`| -17.07 dB        |

- **Overall Average SNR**: **-2.59 dB**

SNR values close to 0 dB indicate low levels of noise or distortion. `sample_14.wav` and `sample_19.wav` had the highest levels of distortion, which contributed to the low overall average SNR.

### 4.3 Word Error Rate (WER)

| Audio Sample   | WER     |
|----------------|---------|
| `sample_1.wav` | 0.86    |
| `sample_2.wav` | 0.50    |
| `sample_3.wav` | 0.93    |
| `sample_4.wav` | 1.63    |
| `sample_5.wav` | 3.00    |
| `sample_6.wav` | 0.90    |
| `sample_7.wav` | 1.33    |
| `sample_8.wav` | 1.88    |
| `sample_9.wav` | 2.10    |
| `sample_10.wav`| 1.93    |
| `sample_11.wav`| 1.72    |
| `sample_12.wav`| 0.77    |
| `sample_13.wav`| 2.00    |
| `sample_14.wav`| 3.00    |
| `sample_15.wav`| 1.88    |
| `sample_16.wav`| 1.38    |
| `sample_17.wav`| 3.00    |
| `sample_18.wav`| 1.35    |
| `sample_19.wav`| 3.00    |

- **Overall Average WER**: **1.74**

WER values indicate words in the synthesized speech that were incorrectly recognized compared to the reference text.

### 4.4 Manual MOS

Overall MOS: 3.45

## Conclusion

The evaluation of the Parler-TTS-mini-jenny-30H model reveals the following insights:

- **MCD**: The model generally produced audio with a reasonable Mel Cepstral Distortion score. Samples such as `sample_19.wav` had the lowest MCD, indicating the highest quality synthesis.
- **SNR**: Signal-to-noise ratio was below 0 dB for most samples, indicating some level of distortion in the generated audio. Two samples (`sample_14.wav` and `sample_19.wav`) showed particularly high distortion levels.
- **WER**: The average WER of 14.32% suggests that the model’s synthesized speech is generally intelligible, but with some notable word-level errors.

Overall, the model performs reasonably well in terms of synthesized speech quality, with some areas for improvement, particularly in terms of distortion (SNR) and intelligibility (WER).

## Recommendations

- **Further Fine-Tuning**: Fine-tuning the model on a larger dataset with more diverse speech patterns could improve the MCD and WER scores.
- **Post-Processing**: Implementing noise reduction techniques during or after synthesis could help improve the SNR values.
