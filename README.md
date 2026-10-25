# Sales-Performance-Dashboard-Analysis
Proyek ini bertujuan untuk menganalisis performa penjualan bisnis secara menyeluruh guna memahami tren transaksi, kontribusi wilayah, performa kategori produk, hingga produk yang paling diminati oleh pelanggan. Dengan memanfaatkan Power BI, dashboard interaktif ini menyajikan ringkasan metrik utama (KPIs) yang membantu manajemen dalam mengidentifikasi peluang pertumbuhan bisnis dan menentukan langkah strategis berbasis data (data-driven decision making).

<img width="1325" height="745" alt="image" src="https://github.com/user-attachments/assets/8ff919a4-8cd2-4262-8f24-8f362a64502d" />

## Pertanyaan Bisnis
1. Bagaimana ringkasan performa penjualan secara keseluruhan (Total Penjualan, Transaksi, Pelanggan, Item Terjual, dan Rata-rata Nilai Transaksi)?
2. Bagaimana tren penjualan dari bulan ke bulan (bulan dengan penjualan tertinggi dan terendah)?
3. Kategori produk mana yang memberikan kontribusi penjualan terbesar terhadap total pendapatan?
4. Wilayah (Region) mana yang menjadi penyumbang utama penjualan?
5. Apa saja 5 produk terlaris berdasarkan kuantitas penjualan, dan produk apa yang paling mendominasi?
6. Strategi bisnis apa yang dapat diterapkan untuk meningkatkan performa kategori/wilayah yang masih di bawah rata-rata?

## Insight
1. Tren Penjualan: Penjualan puncak terjadi pada bulan Agustus (mendekati Rp50 Juta), sementara penurunan paling signifikan terjadi di akhir tahun pada bulan Desember (< Rp5 Juta).
2. Kategori Utama: Office Supplies mendominasi pendapatan sebesar Rp171 Juta (51,51%), diikuti oleh Technology (Rp92 Juta / 27,68%) dan Furniture (Rp69 Juta / 20,81%).
3. Produk Terlaris: Staples merupakan produk dengan volume penjualan tertinggi (64 unit), disusul oleh Easy-staple paper (55 unit).
4. Kontribusi Wilayah: Wilayah Central menjadi penyumbang pendapatan terbesar (Rp128 Juta), sedangkan wilayah South menghasilkan penjualan terendah (Rp42 Juta).

## Rekomendasi Strategi
1. Strategi Bundling Product: Naikkan kontribusi penjualan kategori Furniture dari 20,81% ke 25% dalam 3 bulan melalui skema bundling produk terlaris (Office Supplies) dengan produk Furniture (seperti Storage Drawers atau Bookcases).
2. Penetrasi Wilayah Potensial: Terapkan program promosi khusus atau potongan ongkos kirim di wilayah South dan East untuk mendongkrak pangsa pasar regional minimal 15% pada kuartal berikutnya.
3. Kampanye Promosi Akhir Tahun: Luncurkan strategi End-of-Year Sale atau Corporate Procurement Promo pada awal Q4 untuk memitigasi penurunan tren penjualan drastis di bulan September hingga Desember.

## Tools yang Digunakan
1. Power BI Desktop: Untuk manipulasi data (Power Query), pemodelan data (DAX), serta desain visualisasi dashboard interaktif.
2. GitHub: Untuk repositori kode, dokumentasi proyek (README.md), dan portofolio data analisis.

## Visualisasi 
1. Header & KPIs: Menampilkan metrik utama (Total Penjualan, Transaksi, Pelanggan, Item Terjual, Rata-rata Transaksi) dan slicer filter Tahun (2014–2017).
2. Tren Penjualan Bulanan (Line Chart): Melacak fluktuasi pendapatan dari bulan Januari hingga Desember.
3. Proporsi & Distribusi Kategori (Donut & Column Chart): Menampilkan kontribusi penjualan kategori Office Supplies, Technology, dan Furniture.
4. Top 5 Produk Terlaris (Bar Chart): Menampilkan 5 produk unggulan berdasarkan kuantitas unit yang terjual.
5. Penjualan per Wilayah (Bar Chart): Membandingkan kontribusi pendapatan dari wilayah Central, West, East, dan South.
6. Detail Penjualan Top 10 (Table): Menampilkan detail nama produk, jumlah unit terjual, total penjualan, dan persentase kontribusi.

## Proses Pembersihan Data 
A. Pembersihan data
1. Validasi Data: Menghapus data ganda (duplicate rows) dan menangani nilai kosong (null/missing values).
2. Format Tipe Data: Mengubah Order Date ke Date, Sales & Price ke Currency/Decimal, dan Quantity ke Whole Number.
3. Transformasi Data: Standardisasi nama produk/kategori dan pengelompokan wilayah (Region).
   
B. DAX Measures (Data Analysis Expressions)

| No |Measure |
| :--- | :--- |
| **1.** | Total Penjualan = SUM(Sales[Sales Amount])  |
| **2.** | Total Transaksi = DISTINCTCOUNT(Sales[Order ID]) |
| **3.** | Jumlah Pelanggan = DISTINCTCOUNT(Sales[Customer ID]) |
| **4.** | Jumlah Item Terjual = SUM(Sales[Quantity]) |
| **5.** | Rata-rata Transaksi = DIVIDE([Total Penjualan], [Total Transaksi], 0) |
| **6.** |  Persentase Penjualan = DIVIDE( <br>SUM(Sales[Sales Amount]),<br>CALCULATE(SUM(Sales[Sales Amount]), ALL(Sales[Product Name])),<br>0) |
