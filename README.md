# 🎙️ Sistem Speech-to-Text Bahasa Indonesia
### Proyek Pengolahan Sinyal Digital - Kelompok 15 | Sains Data 2023D

---

## 📌 Deskripsi Proyek

Proyek ini mengembangkan sistem **Speech-to-Text (STT) Bahasa Indonesia** dengan membandingkan dua pendekatan model:

- **Whisper (OpenAI)** - Model pretrained berbasis Transformer yang mendukung transkripsi multibahasa secara langsung tanpa pelatihan ulang.
- **LSTM (Long Short-Term Memory)** - Model sekuensial berbasis RNN yang dilatih menggunakan fitur MFCC dari dataset audio Bahasa Indonesia.

Dataset yang digunakan berasal dari **Common Voice Mozilla** dengan 3.618 sampel rekaman suara Bahasa Indonesia beserta transkripnya.

> **Kesimpulan:** Whisper unggul secara signifikan dengan akurasi tinggi, sementara LSTM hanya mencapai akurasi 4% pada dataset ini.

---

## 👥 Anggota Kelompok

| Nama | NIM |
|------|-----|
| Faishal Bayu Pratama | 23031554092 |
| Mutiara Restu Aulya | 23031554113 |
| Yogi Ramadhani | 23031554198 |

**Program Studi:** Sains Data - Fakultas MIPA, Universitas Negeri Surabaya

---

## 📁 Struktur Folder

```
├── PSD_source.ipynb        # Notebook utama (Whisper + LSTM)
├── wav/                    # Folder berisi file audio (.wav)
│   └── Coba.wav            # Sample audio uji coba
├── requirements.txt        # Daftar library yang dibutuhkan
└── README.md               # Dokumentasi proyek
```

---

## ⚙️ Cara Menjalankan

### ✅ Opsi 1: Google Colab (Recommended)

1. Buka notebook melalui link berikut:  
   👉 [Buka di Google Colab](https://colab.research.google.com/drive/1OEExsYG20tErJRupxHzanYGnUZwx8nrD?usp=sharing)

2. Upload file audio `.wav` ke Colab (atau mount Google Drive jika dataset ada di Drive)

3. Jalankan semua cell secara berurutan dari atas ke bawah (**Runtime > Run all**)

---

### 💻 Opsi 2: Menjalankan Secara Lokal

#### Prasyarat
- Python 3.9 atau lebih baru
- FFmpeg terinstall di sistem ([download FFmpeg](https://ffmpeg.org/download.html))

#### Langkah-langkah

```bash
# 1. Clone repository
git clone https://github.com/username/nama-repo.git
cd nama-repo

# 2. Buat virtual environment (opsional tapi direkomendasikan)
python -m venv venv
source venv/bin/activate        # Linux/Mac
venv\Scripts\activate           # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Install Whisper dari GitHub
pip install git+https://github.com/openai/whisper.git

# 5. Jalankan Jupyter Notebook
jupyter notebook PSD_source.ipynb
```

#### Persiapan Dataset

Taruh file audio `.wav` ke dalam folder `wav/`:
```
wav/
└── Coba.wav    ← file audio uji coba
```

Jika menggunakan dataset penuh dari Common Voice Mozilla, download di:  
🔗 https://commonvoice.mozilla.org/id/datasets

---

## 📊 Hasil Perbandingan Model

| Aspek | LSTM | Whisper |
|-------|------|---------|
| Akurasi | 4% | Tinggi |
| Kebutuhan Training | Ya (manual) | Tidak (pretrained) |
| Denoising | Manual | Otomatis |
| Dukungan Bahasa Indonesia | Terbatas | ✅ Native |
| Kecepatan | Lambat | Cepat (GPU optimal) |

---

## 📦 Dataset

- **Sumber:** [Common Voice Mozilla - Bahasa Indonesia](https://commonvoice.mozilla.org/id/datasets)
- **Jumlah sampel:** 3.618 rekaman suara
- **Format:** `.wav` + file transkrip

> ⚠️ Dataset tidak disertakan di repository karena ukurannya besar. Download manual dari link di atas, lalu taruh di folder `wav/`.

---

## 🔗 Referensi

- Pratama, R. S. A., & Amrullah, A. (2024). *Analysis of Whisper Automatic Speech Recognition Performance on Low Resource Language*. Jurnal Pilar Nusa Mandiri.
- Wang, S., et al. (2023). *Can Whisper Perform Speech-Based In-Context Learning*. arXiv.
- Zeyer, A., et al. (2017). *A Comprehensive Study of Deep Bidirectional LSTM RNNs for Acoustic Modeling in Speech Recognition*. ICASSP.
