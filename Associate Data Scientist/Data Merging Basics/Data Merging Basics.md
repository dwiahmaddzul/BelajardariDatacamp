# Data Merging Basics

## Pengantar
Dalam analisis data, sering kali kita harus menggabungkan beberapa dataset untuk mendapatkan informasi yang lebih lengkap. Pandas menyediakan berbagai metode untuk menggabungkan data dengan efisien.

## Konsep Dasar
- `pd.merge()` digunakan untuk menggabungkan dua dataframe berdasarkan kolom kunci.
- `on` menentukan kolom yang digunakan untuk penggabungan.
- `how` menentukan jenis join yang digunakan (inner, outer, left, right).

## Contoh Penggunaan
### Inner Join
```python
import pandas as pd

data1 = pd.DataFrame({'ID': [1, 2, 3], 'Nama': ['Ayu', 'Budi', 'Citra']})
data2 = pd.DataFrame({'ID': [1, 2, 4], 'Nilai': [85, 90, 75]})

merged = pd.merge(data1, data2, on='ID', how='inner')
print(merged)
```

## Kesimpulan
Pemahaman dasar tentang penggabungan data dengan `merge()` sangat penting dalam analisis data. Langkah berikutnya adalah memahami berbagai jenis join yang lebih kompleks.
