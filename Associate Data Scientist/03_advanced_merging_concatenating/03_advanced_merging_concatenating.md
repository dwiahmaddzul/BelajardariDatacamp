Advanced Merging and Concatenating
Overview
Dalam analisis data, sering kali kita perlu menggabungkan beberapa tabel dengan teknik yang lebih kompleks daripada sekadar join sederhana. Pandas menyediakan berbagai metode untuk melakukan advanced merging dan concatenation yang lebih fleksibel.

Metode Merging dan Concatenating
1️⃣ Merging dengan Multiple Keys
Menggabungkan dua tabel berdasarkan lebih dari satu kolom kunci.

2️⃣ Concatenation dengan Axis
Menggabungkan DataFrame secara vertikal (baris) atau horizontal (kolom).

3️⃣ Handling Duplicate Indexes
Mengelola indeks yang bertumpuk saat penggabungan.

Contoh Implementasi
Berikut adalah contoh implementasi berbagai teknik merging dan concatenation dalam Pandas.

python
Copy
Edit
import pandas as pd

# Contoh data
df1 = pd.DataFrame({
    'ID': [1, 2, 3],
    'Nama': ['Ari', 'Budi', 'Citra'],
    'Skor': [90, 85, 88]
})

df2 = pd.DataFrame({
    'ID': [2, 3, 4],
    'Nama': ['Budi', 'Citra', 'Dika'],
    'Skor': [87, 80, 75]
})

# 1. Merging dengan multiple keys
df_merge_multi = df1.merge(df2, on=['ID', 'Nama'], how='outer')

# 2. Concatenation secara vertikal (axis=0)
df_concat_vertical = pd.concat([df1, df2], axis=0)

# 3. Concatenation secara horizontal (axis=1)
df_concat_horizontal = pd.concat([df1.set_index('ID'), df2.set_index('ID')], axis=1)

df_merge_multi, df_concat_vertical, df_concat_horizontal
Kesimpulan
Teknik advanced merging dan concatenation dalam Pandas sangat berguna untuk menggabungkan dataset dalam berbagai situasi, terutama saat bekerja dengan multi-key joins atau struktur tabel kompleks. Beberapa hal yang perlu diperhatikan:

Merging dengan multiple keys berguna saat ada lebih dari satu kolom kunci yang harus diperhatikan.
Concatenation dengan axis=0 digunakan untuk menggabungkan baris baru, sedangkan axis=1 digunakan untuk menggabungkan kolom baru.
Duplicate indexes harus dikelola dengan baik untuk menghindari inkonsistensi data.
Eksperimenlah dengan dataset lain untuk memahami lebih dalam! 🚀

