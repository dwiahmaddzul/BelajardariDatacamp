# Merging Tables With Different Join Types

## Overview

Ketika bekerja dengan data di pandas, kita seringkali perlu menggabungkan dua atau lebih tabel berdasarkan kolom tertentu. `pandas.merge()` menyediakan berbagai jenis join yang mirip dengan SQL.

## Jenis Join dalam Pandas

1. **Inner Join** – Mengembalikan hanya baris yang memiliki kecocokan di kedua tabel.
2. **Left Join** – Mengembalikan semua baris dari tabel kiri dan mencocokkan data dari tabel kanan.
3. **Right Join** – Mengembalikan semua baris dari tabel kanan dan mencocokkan data dari tabel kiri.
4. **Outer Join** – Mengembalikan semua baris dari kedua tabel dan mengisi nilai yang hilang dengan NaN.

## Contoh Penggunaan

```python
import pandas as pd

df1 = pd.DataFrame({
    'ID': [1, 2, 3],
    'Nama': ['Ari', 'Budi', 'Citra']
})

df2 = pd.DataFrame({
    'ID': [2, 3, 4],
    'Skor': [85, 90, 78]
})

# Inner Join
df_inner = df1.merge(df2, on='ID', how='inner')

# Left Join
df_left = df1.merge(df2, on='ID', how='left')

# Right Join
df_right = df1.merge(df2, on='ID', how='right')

# Outer Join
df_outer = df1.merge(df2, on='ID', how='outer')

df_inner, df_left, df_right, df_outer
