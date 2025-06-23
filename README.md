### Kelompok 4 - Deep Learning (A)
# 🍊 Klasifikasi Penyakit Daun Jeruk dengan Deep Learning (VGG16 + Transfer Learning)

Repositori ini berisi implementasi sistem klasifikasi citra penyakit daun jeruk menggunakan pendekatan **Transfer Learning** dengan arsitektur **VGG16**. Tujuannya adalah untuk mendeteksi jenis penyakit daun jeruk secara otomatis melalui citra digital, sehingga dapat membantu petani melakukan diagnosis secara cepat dan akurat.

---

## 📂 Dataset

Dataset yang digunakan adalah **Citrus Leaf Disease Image Dataset**, yang terdiri dari gambar daun jeruk dalam 5 kelas:
- **Black spot**
- **Canker**
- **Greening**
- **Healthy**
- **Melanose**

Namun, jumlah gambar per kelas tidak seimbang. Oleh karena itu dilakukan **augmentasi data** sehingga setiap kelas memiliki **250 gambar**, total menjadi **1250 gambar**.

🔗 [Download Dataset Asli](https://drive.google.com/file/d/1QLilUQCUTKVkHlCajlK-EzGncH2TBm2T/view?usp=sharing)

---

## 🧠 Arsitektur & Metode

- **Model:** VGG16 (pre-trained dari ImageNet, digunakan sebagai feature extractor)
- **Layer Tambahan:**
  - `GlobalAveragePooling2D`
  - `Dropout(0.5)`
  - `Dense(128, activation='relu')`
  - `Dense(5, activation='softmax')`
- **Loss Function:** Categorical Crossentropy
- **Optimizer:** Adam
- **Epoch:** 50
- **Batch Size:** 32
- **Input Size:** 224x224 piksel
- **Augmentasi Citra:** rotasi, flip horizontal, zoom, shear, dan translasi (via `ImageDataGenerator`)

---

## 🔁 Alur Eksekusi

1. **Ekstrak dan susun dataset** berdasarkan label (per kelas)
2. **Augmentasi dataset** untuk menyeimbangkan jumlah gambar antar kelas
3. **Pembagian data** menjadi data pelatihan (80%) dan validasi (20%) menggunakan `ImageDataGenerator`
4. **Bangun model** berbasis arsitektur VGG16 + layer klasifikasi tambahan
5. **Latih model** selama 50 epoch
6. **Evaluasi performa model** menggunakan akurasi, precision, recall, F1-score, dan confusion matrix
7. **Visualisasi prediksi** dengan mencocokkan label asli vs prediksi model

---

## 📊 Hasil Evaluasi

- **Akurasi Validasi:** 86%
- **Kinerja Tertinggi:** Kelas *Melanose* (100% precision dan recall)
- **Kelas Paling Sering Tertukar:** *Black spot* dan *Greening*
- Visualisasi prediksi dan confusion matrix tersedia untuk menilai distribusi hasil klasifikasi

---

## 🎯 Tujuan Proyek

Membuat sistem klasifikasi otomatis untuk mendeteksi penyakit pada daun jeruk berbasis citra digital menggunakan metode deep learning dan transfer learning. Diharapkan sistem ini dapat digunakan sebagai dasar pengembangan aplikasi yang membantu petani dalam proses diagnosis cepat dan akurat.

---
