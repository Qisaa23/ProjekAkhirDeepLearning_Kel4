# 🍊 Klasifikasi Penyakit Daun Jeruk dengan Deep Learning

Repositori ini berisi implementasi sistem klasifikasi citra penyakit daun jeruk menggunakan metode *Transfer Learning* dengan arsitektur **EfficientNetB0**. Sistem ini membandingkan performa model pada **dataset asli** dan **dataset augmentasi (modifikasi)** untuk mengevaluasi pengaruh preprocessing terhadap akurasi klasifikasi.

---

## 📂 Dataset

1. **Dataset Asli (Original)**  
   Gambar daun jeruk dalam 5 kelas penyakit.  
   🔗 [Download Original Dataset](https://drive.google.com/file/d/1QLilUQCUTKVkHlCajlK-EzGncH2TBm2T/view?usp=sharing)

2. **Dataset Modifikasi (Augmentasi)**  
   Dataset yang telah mengalami augmentasi untuk meningkatkan variasi data.  
   🔗 [Download Dataset Modifikasi](https://drive.google.com/file/d/1xKI_FS7-3jOurZJ5QU74VGmONcQZXk5S/view?usp=sharing)

---

## 🧠 Metode

- **Model:** EfficientNetB0 (pretrained dengan ImageNet)
- **Fine-tuning:** Freeze sebagian besar layer, hanya bagian akhir yang dilatih
- **Loss Function:** Categorical Crossentropy
- **Optimizer:** Adam (learning rate: 1e-4)
- **Evaluasi:** Akurasi dan *Validation Loss*
- **Early Stopping:** Untuk mencegah overfitting

---

## 🔁 Alur Eksekusi

1. Load dan ekstraksi kedua dataset
2. Preprocessing dan augmentasi citra
3. Pembagian dataset menjadi training dan validasi
4. Definisi arsitektur EfficientNetB0
5. Kompilasi dan training model pada dataset original dan modifikasi
6. Evaluasi dan perbandingan performa kedua model

---

## 🎯 Tujuan

Menguji apakah augmentasi data dapat meningkatkan performa model dalam mendeteksi penyakit daun jeruk berdasarkan citra, dengan pendekatan deep learning menggunakan transfer learning.
