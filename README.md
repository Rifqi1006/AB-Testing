# 🍔 Analisis A/B Testing Kampanye Promosi Fast Food

A/B testing adalah metode eksperimen yang digunakan untuk membandingkan dua atau lebih variasi untuk menentukan mana yang paling efektif dalam mencapai tujuan bisnis. Project ini menganalisis hasil A/B testing dari tiga kampanye pemasaran yang berbeda yang dijalankan oleh sebuah jaringan fast food untuk meluncurkan menu baru. Analisis ini bertujuan untuk memberikan rekomendasi data-driven berdasarkan evaluasi statistik terhadap performa penjualan masing-masing strategi promosi.  

---

## 🎯 Tujuan  

1. Mengevaluasi hasil uji A/B dan menentukan strategi pemasaran mana yang memberikan hasil penjualan terbaik.  
2. Sebagai portofolio pribadi yang menunjukkan kemampuan dalam melakukan analisis data statistik (A/B testing).  

---

## 📂 Dataset

- Data bersumber dari Kaggle: [Fast Food Marketing Campaign A/B Test](https://www.kaggle.com/datasets/chebotinaa/fast-food-marketing-campaign-ab-test)
- Ukuran Data: 548 observasi, 8 kolom
- Struktur Kolom:
   - `MarketID` : Pengidentifikasi unik untuk pasar
   - `MarketSize` : Ukuran area pasar berdasarkan penjualan
   - `LocationID` : Pengidentifikasi unik untuk lokasi toko
   - `AgeOfStore` : Usia toko dalam tahun
   - `Promotion` : Tipe promosi (satu dari tiga strategi yang diuji)
   - `week` : Minggu ke-berapa dari periode promosi (1–4)
   - `SalesInThousands` : Jumlah penjualan (dalam ribuan USD) untuk kombinasi lokasi, promosi, dan minggu tertentu

---

## 🔍 Tahapan Analisis  

1. **Exploratory Data Analysis (EDA):** Memeriksa kualitas data, missing values, statistik deskriptif, dan keseimbangan grup promosi.
2. **Visualisasi Distribusi Data:** Membuat histogram dan boxplot untuk memahami distribusi penjualan dan memeriksa normalitas data menggunakan Q-Q plot.
5. **Transformasi Data:** Menerapkan transformasi logaritmik pada data penjualan (`SalesInThousands`) dan memeriksan pemenuhan asumsi normalitas.   
7. **Analisis Statistik:** 
   - Melakukan ANOVA pada data transformasi untuk menguji perbedaan mean antar grup
   - Melakukan uji Kruskal-Wallis pada data asli sebagai validasi non-parametrik
8. **Uji Tukey HSD:** Melakukan analisis post-hoc untuk mengetahui pasangan promosi mana yang secara spesifik berbeda signifikan. 
9. **Bootstrap Analysis:** Menghitung confidence intervals untuk mean penjualan setiap promosi dan perbedaan antar mereka untuk estimasi yang robust.   

---

## 🛠️ Teknologi dan Tools  

- Bahasa Pemrograman : `Python`   
- Manipulasi dan Analisis Data: `Pandas`  
- Komputasi Numerik : `NumPy`  
- Uji Statistik : Shapiro-Wilk, Kruskal-Wallis (`SciPy`)  
- ANOVA, Tukey HSD : `Statsmodels`   
- Visualisasi Data : `Matplotlib` dan `Seaborn`  
- Environment : `Jupyter Notebook` 

---

## 📊 Temuan Statistik  

- Q-Q Plot menunjukkan data transformasi log telah mendekati distribusi normal dan memadai untuk ANOVA. 
- ANOVA pada data transformasi log: `p-value = 9.796796e-12` (Signifikan pada α = 0.05).  
- Uji Kruskal-Wallis pada data asli: `statistic = 53.2948, p-value = 0.000000` (Sangat signifikan).
- Uji Tukey HSD mengidentifikasi pasangan promosi mana yang berbeda signifikan.  
- Bootstrap 95% CI untuk perbedaan promosi menunjukkan selang kepercayaan yang tidak mengandung nol untuk pasangan tertentu.  

---

## 💡 Key Insight  

- Terdapat perbedaan signifikan secara statistik dalam performa penjualan antar ketiga promosi, dengan Promosi 1 unggul 22.8% dibanding Promosi 2 dan 4.9% dibanding Promosi 3.
- Promosi 1 menghasilkan penjualan tertinggi (USD 58.10K), diikuti Promosi 3 (USD 55.36K), sementara Promosi 2 performanya paling rendah (USD 47.32K).
- Perbedaan ini memiliki dampak praktis nyata - implementasi Promosi 1 dapat meningkatkan revenue USD 10.78K per outlet per minggu dibanding Promosi 2.
- Hasil analisis robust dan konsisten di berbagai metode statistik (ANOVA dan Kruskal-Wallis).  

---

## 🚀 Rekomendasi Bisnis  

Promosi 1 direkomendasikan sebagai strategi pemasaran yang optimal karena konsisten menunjukkan performa penjualan terbaik dibandingkan alternatif lainnya. Dibandingkan Promosi 2, strategi ini memberikan peningkatan hasil yang nyata dan berdampak signifikan pada revenue. Sementara itu, perbedaan dengan Promosi 3 lebih kecil dan tidak terbukti signifikan secara statistik. Secara keseluruhan, Promosi 1 adalah pilihan paling efektif untuk diterapkan dalam kampanye pemasaran berikutnya.
