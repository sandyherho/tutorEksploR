# Pendahuluan

## Apa itu R?

<p align="justify">R merupakan bahasa pemrograman dan lingkungan perangkat lunak yang digunakan untuk analisis statistik, pemodelan data, visuliasi grafik, dan pelaporan data. R bersifat sumber terbuka dan gratis diunduh oleh siapapun. Tutorial ini ditujukan untuk membantu pemula untuk memulai eksplorasi data dengan menggunakan R.</p>

## Instalasi

1. Kunjungi <url>https://docs.conda.io/projects/conda/en/latest/user-guide/install/</url> untuk instalasi Miniconda versi 3.
2. Ikuti prosedur instalasi (jangan lupa atur PATH -nya).
3. Ikuti prosedur instalasi git pada situs:
<url>https://git-scm.com/book/en/v2/Getting-Started-Installing-Git</url>.
4. Buku *Command Line Interface* (CLI), jalankan perintah:
```bash
git clone git@github.com:sandyherho/eksploR.git
```
5. Lakukan instalasi lingkungan virtual conda dengan menjalankan perintah di folder hasil *cloning* tersebut:
```bash
conda env create -f environment.yml
```
6. Aktifkan lingkungan virtual dengan perintah:
```bash
conda activate r-env
```
7. Untuk mengaktifkan Jupyter Notebook, jalankan perintah:
```(bash)
jupyter notebook
```
8. Jika sudah terbuka di *browser* masing - masing sesi R interaktif dapat dimulai.
9. Untuk mengakhiri sesi tekan tombol `<CTRL> + C` di CLI, dan jalankan perintah sebagai berikut untuk menonaktifkan lingkungan virtual conda:
    ```(bash)
    conda deactivate
    ```

## Materi 

Pada tutorial ini kami tidak akan membahas tentang penggunaan algoritma - algoritma pemelajaran mesin pada R, melainkan lebih terfokus pada metode statistika klasik dan eksplorasi data menggunakan R. Berikut ini susunan materi yang kami sampaikan dalam tutorial ini:

1. Dasar - dasar pemrograman
2. Matriks
3. Data Frame
4. List
5. Penanganan data tabular
6. Konsep inti pemrograman
7. Konsep pemrograman lanjut
8. Manipulasi data
9. Visualisasi data menggunakan *Base* R
10. Penanganan data kuantitatif dan kualitatif
11. Statistika deskriptif
12. Data bivariat dan multivariat
13. Distribusi peluang
14. Statistika inferensi
15. Visualisasi data menggunakan `ggplot2`
