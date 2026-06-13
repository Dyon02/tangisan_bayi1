# Baby Cry Classification System

Web app klasifikasi tangisan bayi berbasis TensorFlow.js, berjalan sepenuhnya di browser — siap di-host via GitHub Pages.

## Struktur Folder

```
baby-cry-web/
├── index.html
├── models/
│   ├── cnn_lstm/
│   │   ├── model.json
│   │   ├── group1-shard1of3.bin
│   │   ├── group1-shard2of3.bin
│   │   └── group1-shard3of3.bin
│   ├── cnn/
│   │   ├── model.json
│   │   └── group1-shard*.bin (14 file)
│   └── rnn/
│       ├── model.json
│       └── group1-shard1of1.bin
└── README.md
```

## Deploy ke GitHub Pages

### 1. Buat Repository GitHub
```bash
git init
git add .
git commit -m "Initial commit: Baby Cry Classifier"
git branch -M main
git remote add origin https://github.com/USERNAME/baby-cry-classifier.git
git push -u origin main
```

### 2. Aktifkan GitHub Pages
- Buka repo di GitHub
- Settings → Pages
- Source: **Deploy from a branch**
- Branch: `main` / `root`
- Klik **Save**

Web aktif di: `https://USERNAME.github.io/baby-cry-classifier`

### 3. Jika file .bin terlalu besar (>25MB)
```bash
# Gunakan Git LFS
git lfs install
git lfs track "*.bin"
git add .gitattributes
git commit -m "Add LFS tracking"
git push
```

## Kelas yang Dideteksi

| Label | Arti |
|-------|------|
| belly_pain | Sakit Perut / Kolik |
| burping | Ingin Bersendawa |
| discomfort | Tidak Nyaman |
| hungry | Lapar |
| tired | Mengantuk |

## Model yang Tersedia

| Model | Arsitektur | Input Shape |
|-------|-----------|-------------|
| CNN + LSTM (Disarankan) | CNN-BiLSTM Hybrid | (216, 128, 1) |
| CNN | Convolutional NN | (128, 216, 1) |
| RNN | BiLSTM | (216, 128) |
