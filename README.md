# COVID19-XRay-Classification-CNN

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)  
[![Python Version](https://img.shields.io/badge/python-3.7%2B-yellow.svg)](#requirements)

**Proyek tugas edukatif**: klasifikasi citra X-ray dada menjadi COVID-19 vs Non-COVID menggunakan pipeline segmentasi–augmentasi–CNN dari awal.

---

## Deskripsi

Laporan tugas ini membahas implementasi end-to-end pipeline:

1. **Segmentasi paru-paru**  
   - Masking area paru-paru pada X-ray menggunakan U-Net pra-latih  
2. **Augmentasi data**  
   - Geometrik (rotasi, zoom, brightness, flip) hingga:  
     - 1 000 sampel positif, 500 sampel negatif  
3. **Arsitektur CNN sederhana**  
   - 3×(Conv2D + ReLU + MaxPool) → Flatten → Dense(256) + Dropout(0.5) → Sigmoid  
4. **Pelatihan & Evaluasi**  
   - 10 epoch, batch size 32, optimizer RMSprop, loss binary_crossentropy  
   - Data training 85 %, validasi 15 %  

> **Catatan**: Proyek ini bersifat edukatif dan **tidak** untuk penggunaan klinis.

---

## Fitur

- Pra-proses citra X-ray dengan segmentasi paru-paru  
- Augmentasi on-the-fly selama pelatihan  
- Model CNN *from scratch* (tanpa transfer learning)  
- Notebook Google Colab terintegrasi  
- Hasil evaluasi: akurasi pelatihan > 95 %, akurasi uji ≈ 53 %  

---

## Instalasi

1. **Clone** repository  
   ```bash
   git clone https://github.com/username/COVID19-XRay-Classification-CNN.git
   cd COVID19-XRay-Classification-CNN
   ```

2. **Buat & aktifkan** virtual environment  
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install** dependensi  
   ```bash
   pip install -r requirements.txt
   ```

---

## Dataset

- **MV Dataset (154 citra X-ray)**  
  – 56 positive COVID-19, 98 negative  
  – Download: [http://ugm.id/MVDataset](http://ugm.id/MVDataset)  

Letakkan hasil unduhan ke folder `data/raw/`.

---

## Pra-proses Data

> Notebook segmentasi tersedia di `notebooks/segmentation.ipynb` (berbasis [Farhan Haikhan, Kaggle](https://www.kaggle.com/code/farhanhaikhan/pretrained-unet-lung-segmentation-dataset/notebook)).

---

## Pelatihan Model
buka `notebooks/training.ipynb` di Google Colab untuk eksekusi interaktif.

---

## Evaluasi & Hasil

- **Training accuracy**: > 95 %  
- **Validation accuracy**: ≈ 53 %  
- **Recall (COVID-19)**: 33 %  

Grafik kurva loss dan akurasi, confusion matrix, serta classification report dapat ditemukan di folder `reports/figures/`.

---

## Referensi

1. MV Dataset: http://ugm.id/MVDataset  
2. Farhan Haikhan, “Pretrained U‑Net Lung Segmentation Dataset,” Kaggle Notebook.  
3. N. L. I. Huda et al., “Covid‑19 Classification Using HOG‑SVM and Deep Learning Models,” IRASET 2022.  
4. A. Raaouf, “Cnn_model.ipynb,” GitHub: raaouf/Covid-19-Detection-CNN  
5. YoNG‑Zaii, “COVID‑19 Detection Model.ipynb,” GitHub: YoNG-Zaii/COVID-19-Detection-using-CNN  

---

## Lisensi

Proyek ini dirilis di bawah [Lisensi MIT](LICENSE).

---

## Kontak

Ravie Arjun Nadhief  
Email: raviearjunnadhief@mail.ugm.ac.id  
