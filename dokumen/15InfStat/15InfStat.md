# Statistika inferensi

* Statistika deskriptif: mengidentifikasi hubungan dari suatu data, menarik kesimpulan dari sampel.
* Statistika inferensi: menarik kesimpulan tentang populasi.

# Nilai $p$

Nilai $p$ merupakan peluang:
* Jika hipotesis awal benar, maka sampel dapat menghasilkan estimasi.
* Menerangkan kemungkinan kita mendapatkan hasil.

Contoh: 
Ada warung Zominos Pizza:
* **Komplain** pelanggan bahwa kejunya tidak cukup banyak.
* **Regulasi**: Harus pakai 100 gr keju untuk setiap pizza.

Namun, manajer Zominos tidak dapat mengunjungi seluruh warung di kota tersebut, sehingga diambilah sampel dari beberapa warung.

Pada kasus ini:
* $H_{0}$: (*Trying to provide evidence against*) Menolak klaim pelanggan (Cukup kok kejunya).
* $H_{1}$: Apa yang hendak kita buktikan, yakni tidak cukup keju untuk setiap Pizza.

*Significance level* ($\alpha$) = 0,05 <br>
Jika nilai $p$ dibawah $\alpha$, maka kita dapat menolak hipotesis awal.


```R
library(dplyr)
df <- read.csv("../data/ZominosCheese.csv")
head(df)
```


    Attaching package: ‘dplyr’
    
    The following objects are masked from ‘package:stats’:
    
        filter, lag
    
    The following objects are masked from ‘package:base’:
    
        intersect, setdiff, setequal, union




<table>
<thead><tr><th scope=col>GramsCheese</th></tr></thead>
<tbody>
	<tr><td> 85</td></tr>
	<tr><td>100</td></tr>
	<tr><td> 85</td></tr>
	<tr><td> 98</td></tr>
	<tr><td> 94</td></tr>
	<tr><td> 97</td></tr>
</tbody>
</table>




```R
# peraturannya harus pakai keju 100 gr (mu)
t.test(df,mu=100)
```


​    
    	One Sample t-test
    
    data:  df
    t = -0.96396, df = 29, p-value = 0.343
    alternative hypothesis: true mean is not equal to 100
    95 percent confidence interval:
      95.94179 101.45821
    sample estimates:
    mean of x 
         98.7 



Nilai $p$ -nya 0,0343, nilai rata2nya = 98,7. Nilai $p > 0,05$, maka kita menolak hipotesis awal.

## Derajat kebebasan

Derajat kebebasan merujuk pada ukuran maksimum dari nilai - nilai logikal yang bersifat independen.
$$
df = n - 1
$$


```R
data <- read.csv("../data/ZominosCheese.csv")
head(data)
t.test(data, mu=100)
```


<table>
<thead><tr><th scope=col>GramsCheese</th></tr></thead>
<tbody>
	<tr><td> 85</td></tr>
	<tr><td>100</td></tr>
	<tr><td> 85</td></tr>
	<tr><td> 98</td></tr>
	<tr><td> 94</td></tr>
	<tr><td> 97</td></tr>
</tbody>
</table>





    	One Sample t-test
    
    data:  data
    t = -0.96396, df = 29, p-value = 0.343
    alternative hypothesis: true mean is not equal to 100
    95 percent confidence interval:
      95.94179 101.45821
    sample estimates:
    mean of x 
         98.7 



$df = 29$


```R
df = length(data$GramsCheese) - 1
df
```


29


## Selang dan level kepercayaan

* Selang kepercayaan mengukur derajat ketidakpastian atau kepastian.
* Level kepercayaan merupakan persentase dari peluang atau kepastian.


```R
t.test(data,mu=100)
```


​    
    	One Sample t-test
    
    data:  data
    t = -0.96396, df = 29, p-value = 0.343
    alternative hypothesis: true mean is not equal to 100
    95 percent confidence interval:
      95.94179 101.45821
    sample estimates:
    mean of x 
         98.7 



Selang kepercayaan: 95,94179 hingga 101,45821

## Pengujian hipotesis

Pengujian hipotesis merupakan prosedur di dalam statistika inferensi

* $H_0$ (hipotesis awal): Dua populasi tidak berbeda jika merujuk pada sifat tertentu.
* $H_1$ (hipotesis alternatif): Efek tertentu terjadi pada dua buah populasi.

Jika nilai$-p$ dibawah *significance level*, maka kita dapat menolak hipotesis awal.

Untuk melakukan pengujian hipotesis, kita menggunakan uji$-t$

Uji$-t$ adalah salah satu teknik statistika inferensi yang digunakan untuk menentukan perbedaan signifikan rata - rata antar dua kelompok.

Terdapat 3 jenis uji$-t$:
* Uji sampel tunggal.
* Uji dua sampel.
* Uji sampel berpasangan.

### Studi kasus
Zominos mempunyai penawaran beli 1 gratis 1 pada hari tertentu untuk meningkatkan penjualan.

* Sampel 1: Penjualan pada hari - hari promosi.
* Sampel 2: Penjualan pada hari - hari biasa.

Berikut adalah hipotesis nya:
* $H_0$: Tidak ada perbedaan antara penjualan di hari - hari promosi dan hari - hari biasa (Penjualan promo = Penjualan biasa).
* $H_1$: Terdapat perbedaan (Penjualan promo $\neq$ Penjualan biasa).

(Disebut sebagai *two-tail test*).

* $H_0$: Penjualan promo - Penjualan biasa = 0
* $H_1$: Penjualan promo - Penjualan biasa $\neq$ 0

Jika kita tidak tertarik pada penjualan yang berkurang pada hari - hari promosi, maka uji hipotesis dapat diubah formulasinya:
* $H_0$: Penjualan promo - Penjualan biasa $\leq$ 0.
* $H_1$:  Penjualan promo - Penjualan biasa > 0.


```R
df <- read.csv("../data/ZominosSales.csv")
head(df)
```


<table>
<thead><tr><th scope=col>OfferDays</th><th scope=col>NonOfferDays</th></tr></thead>
<tbody>
	<tr><td>248.3</td><td>215.1</td></tr>
	<tr><td>335.2</td><td>300.0</td></tr>
	<tr><td>338.0</td><td>320.6</td></tr>
	<tr><td>285.3</td><td>276.6</td></tr>
	<tr><td>322.2</td><td>282.9</td></tr>
	<tr><td>283.6</td><td>288.1</td></tr>
</tbody>
</table>




```R
t.test(df$OfferDays, df$NonOfferDays) # Two-tail test
```


​    
    	Welch Two Sample t-test
    
    data:  df$OfferDays and df$NonOfferDays
    t = 2.6105, df = 17.229, p-value = 0.01814
    alternative hypothesis: true difference in means is not equal to 0
    95 percent confidence interval:
      7.997416 75.042584
    sample estimates:
    mean of x mean of y 
       307.35    265.83 



Nilai$-p < 0,05$, maka kita menolak $H_0$ (Penjualan promo - Penjualan biasa = 0).


```R
# One-tail test
t.test(df$OfferDays, mu = 265.83) # mu = NonOfferDays
```


​    
    	One Sample t-test
    
    data:  df$OfferDays
    t = 4.1576, df = 9, p-value = 0.002456
    alternative hypothesis: true mean is not equal to 265.83
    95 percent confidence interval:
     284.7592 329.9408
    sample estimates:
    mean of x 
       307.35 



Nilai$-p < 0,05$, maka kita menolak $H_0$ (Penjualan promo - Penjualan biasa $\leq$ 0).

## Uji chi-kuadrat

Uji chi-kuadrat menilai apakah baris dan kolom pada tabel kontingensi berhubungan secara siginifikan secara statistik.

Terdapat dua jenis uji chi-kuadrat:
* *Test of independence*
* *Goodness-of-Fit Test*

* $H_0$: Variabel baris dan kolom dari tabel kontingensi bersifat independen.
* $H_1$: Variabel baris dan kolom saling bergantung.

Jika nilai uji chi-kuadrat lebih besar dari *significance level*, maka mengindikasikan bahwa kolom dan baris saling berhubungan satu dengan yang lain.


```R
ratings <-  factor(c(2,4,3,3,2,1,1,2,3,4,2,3,3,4,1,3,2,1,4,3,2,4))
ratings
```


<ol class=list-inline>
	<li>2</li>
	<li>4</li>
	<li>3</li>
	<li>3</li>
	<li>2</li>
	<li>1</li>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>2</li>
	<li>3</li>
	<li>3</li>
	<li>4</li>
	<li>1</li>
	<li>3</li>
	<li>2</li>
	<li>1</li>
	<li>4</li>
	<li>3</li>
	<li>2</li>
	<li>4</li>
</ol>

<details>
	<summary style=display:list-item;cursor:pointer>
		<strong>Levels</strong>:
	</summary>
	<ol class=list-inline>
		<li>'1'</li>
		<li>'2'</li>
		<li>'3'</li>
		<li>'4'</li>
	</ol>
</details>



```R
kursus <- factor(c(1,1,1,0,0,0,0,0,1,1,1,0,0,0,0,0,1,1,1,1,1,0))
kursus
```


<ol class=list-inline>
	<li>1</li>
	<li>1</li>
	<li>1</li>
	<li>0</li>
	<li>0</li>
	<li>0</li>
	<li>0</li>
	<li>0</li>
	<li>1</li>
	<li>1</li>
	<li>1</li>
	<li>0</li>
	<li>0</li>
	<li>0</li>
	<li>0</li>
	<li>0</li>
	<li>1</li>
	<li>1</li>
	<li>1</li>
	<li>1</li>
	<li>1</li>
	<li>0</li>
</ol>

<details>
	<summary style=display:list-item;cursor:pointer>
		<strong>Levels</strong>:
	</summary>
	<ol class=list-inline>
		<li>'0'</li>
		<li>'1'</li>
	</ol>
</details>



```R
levels(kursus) <- c('R', 'Python')
```


```R
kursus
```


<ol class=list-inline>
	<li>Python</li>
	<li>Python</li>
	<li>Python</li>
	<li>R</li>
	<li>R</li>
	<li>R</li>
	<li>R</li>
	<li>R</li>
	<li>Python</li>
	<li>Python</li>
	<li>Python</li>
	<li>R</li>
	<li>R</li>
	<li>R</li>
	<li>R</li>
	<li>R</li>
	<li>Python</li>
	<li>Python</li>
	<li>Python</li>
	<li>Python</li>
	<li>Python</li>
	<li>R</li>
</ol>

<details>
	<summary style=display:list-item;cursor:pointer>
		<strong>Levels</strong>:
	</summary>
	<ol class=list-inline>
		<li>'R'</li>
		<li>'Python'</li>
	</ol>
</details>



```R
data <- table(ratings, kursus)
data
```


           kursus
    ratings R Python
          1 3      1
          2 2      4
          3 4      3
          4 2      3



```R
chisq.test(data)
```

    Warning message in chisq.test(data):
    “Chi-squared approximation may be incorrect”


​    
    	Pearson's Chi-squared test
    
    data:  data
    X-squared = 2.0095, df = 3, p-value = 0.5704



Nilai$-p$: 0,5704. Maka dapat disimpulkan jika variabel baris dan kolom tidak independen. Secara implisit menyatakan ada hubungan antara kursus dengan ratings.


```R
chisq.test(data,simulate.p.value=T)
# Karena datanya kurang, kita simulasikan untuk jumlah data replikasi yang lebih besar
```


​    
    	Pearson's Chi-squared test with simulated p-value (based on 2000
    	replicates)
    
    data:  data
    X-squared = 2.0095, df = NA, p-value = 0.7076
