# Konsep - konsep pemrograman lanjut

## Fitur - fitur *built-in*

### `seq()`: Mendefinisikan sikuen


```R
seq(0,10, by=2)
```


<ol class=list-inline>
	<li>0</li>
	<li>2</li>
	<li>4</li>
	<li>6</li>
	<li>8</li>
	<li>10</li>
</ol>




```R
seq(0,100, by = 10)
```


<ol class=list-inline>
	<li>0</li>
	<li>10</li>
	<li>20</li>
	<li>30</li>
	<li>40</li>
	<li>50</li>
	<li>60</li>
	<li>70</li>
	<li>80</li>
	<li>90</li>
	<li>100</li>
</ol>




```R
seq(0,30, by = 2)
```


<ol class=list-inline>
	<li>0</li>
	<li>2</li>
	<li>4</li>
	<li>6</li>
	<li>8</li>
	<li>10</li>
	<li>12</li>
	<li>14</li>
	<li>16</li>
	<li>18</li>
	<li>20</li>
	<li>22</li>
	<li>24</li>
	<li>26</li>
	<li>28</li>
	<li>30</li>
</ol>



### `sort()` : Mengurutkan vektor


```R
v <- c(2,7,1,49,54,32)
v
```


<ol class=list-inline>
	<li>2</li>
	<li>7</li>
	<li>1</li>
	<li>49</li>
	<li>54</li>
	<li>32</li>
</ol>




```R
sort(v) # dari kecil ke besar
```


<ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>7</li>
	<li>32</li>
	<li>49</li>
	<li>54</li>
</ol>




```R
sort(v, decreasing = T) # dari besar ke kecil
```


<ol class=list-inline>
	<li>54</li>
	<li>49</li>
	<li>32</li>
	<li>7</li>
	<li>2</li>
	<li>1</li>
</ol>




```R
nama <- c('s', 'a', 'n', 'd', 'y')
nama
```


<ol class=list-inline>
	<li>'s'</li>
	<li>'a'</li>
	<li>'n'</li>
	<li>'d'</li>
	<li>'y'</li>
</ol>




```R
sort(nama)
```


<ol class=list-inline>
	<li>'a'</li>
	<li>'d'</li>
	<li>'n'</li>
	<li>'s'</li>
	<li>'y'</li>
</ol>




```R
nama <- c('s', 'a', 'n', 'd', 'Y')
sort(nama)
```


<ol class=list-inline>
	<li>'a'</li>
	<li>'d'</li>
	<li>'n'</li>
	<li>'s'</li>
	<li>'Y'</li>
</ol>




```R
nama <- c('s', 'a', 'n', 'd', 'Y','A')
sort(nama)
```


<ol class=list-inline>
	<li>'a'</li>
	<li>'A'</li>
	<li>'d'</li>
	<li>'n'</li>
	<li>'s'</li>
	<li>'Y'</li>
</ol>



### `rev()`: Membalikan elemen di dalam suatu objek


```R
b <- seq(1,10)
b
```


<ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
	<li>6</li>
	<li>7</li>
	<li>8</li>
	<li>9</li>
	<li>10</li>
</ol>




```R
rev(b)
```


<ol class=list-inline>
	<li>10</li>
	<li>9</li>
	<li>8</li>
	<li>7</li>
	<li>6</li>
	<li>5</li>
	<li>4</li>
	<li>3</li>
	<li>2</li>
	<li>1</li>
</ol>




```R
d <- c('a','b','e','d')
d
```


<ol class=list-inline>
	<li>'a'</li>
	<li>'b'</li>
	<li>'e'</li>
	<li>'d'</li>
</ol>




```R
rev(d)
```


<ol class=list-inline>
	<li>'d'</li>
	<li>'e'</li>
	<li>'b'</li>
	<li>'a'</li>
</ol>



### `str()`: Menunjukkan struktur dari suatu objek


```R
str(b)
```

     int [1:10] 1 2 3 4 5 6 7 8 9 10



```R
str(mtcars)
```

    'data.frame':	32 obs. of  11 variables:
     $ mpg : num  21 21 22.8 21.4 18.7 18.1 14.3 24.4 22.8 19.2 ...
     $ cyl : num  6 6 4 6 8 6 8 4 4 6 ...
     $ disp: num  160 160 108 258 360 ...
     $ hp  : num  110 110 93 110 175 105 245 62 95 123 ...
     $ drat: num  3.9 3.9 3.85 3.08 3.15 2.76 3.21 3.69 3.92 3.92 ...
     $ wt  : num  2.62 2.88 2.32 3.21 3.44 ...
     $ qsec: num  16.5 17 18.6 19.4 17 ...
     $ vs  : num  0 0 1 1 0 1 0 1 1 1 ...
     $ am  : num  1 1 1 0 0 0 0 0 0 0 ...
     $ gear: num  4 4 4 3 3 3 3 4 4 4 ...
     $ carb: num  4 4 1 1 2 1 4 2 2 4 ...



```R
summary(mtcars)
```


          mpg             cyl             disp             hp       
     Min.   :10.40   Min.   :4.000   Min.   : 71.1   Min.   : 52.0  
     1st Qu.:15.43   1st Qu.:4.000   1st Qu.:120.8   1st Qu.: 96.5  
     Median :19.20   Median :6.000   Median :196.3   Median :123.0  
     Mean   :20.09   Mean   :6.188   Mean   :230.7   Mean   :146.7  
     3rd Qu.:22.80   3rd Qu.:8.000   3rd Qu.:326.0   3rd Qu.:180.0  
     Max.   :33.90   Max.   :8.000   Max.   :472.0   Max.   :335.0  
          drat             wt             qsec             vs        
     Min.   :2.760   Min.   :1.513   Min.   :14.50   Min.   :0.0000  
     1st Qu.:3.080   1st Qu.:2.581   1st Qu.:16.89   1st Qu.:0.0000  
     Median :3.695   Median :3.325   Median :17.71   Median :0.0000  
     Mean   :3.597   Mean   :3.217   Mean   :17.85   Mean   :0.4375  
     3rd Qu.:3.920   3rd Qu.:3.610   3rd Qu.:18.90   3rd Qu.:1.0000  
     Max.   :4.930   Max.   :5.424   Max.   :22.90   Max.   :1.0000  
           am              gear            carb      
     Min.   :0.0000   Min.   :3.000   Min.   :1.000  
     1st Qu.:0.0000   1st Qu.:3.000   1st Qu.:2.000  
     Median :0.0000   Median :4.000   Median :2.000  
     Mean   :0.4062   Mean   :3.688   Mean   :2.812  
     3rd Qu.:1.0000   3rd Qu.:4.000   3rd Qu.:4.000  
     Max.   :1.0000   Max.   :5.000   Max.   :8.000  


### `append()`: Menggabungkan objek


```R
v1 <- seq(1,5)
v2 <- seq(10,30, by=10)
```


```R
append(v1,v2)
```


<ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
	<li>10</li>
	<li>20</li>
	<li>30</li>
</ol>



### Memeriksa dan mengonversi tipe data pada objek - objek R


```R
v1
```


<ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>




```R
is.vector(v1)
```


TRUE



```R
is.data.frame(v1)
```


FALSE



```R
is.data.frame(mtcars)
```


TRUE



```R
as.list(v1)
```


<ol>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>




```R
as.matrix(v1)
```


<table>
<tbody>
	<tr><td>1</td></tr>
	<tr><td>2</td></tr>
	<tr><td>3</td></tr>
	<tr><td>4</td></tr>
	<tr><td>5</td></tr>
</tbody>
</table>



## Fungsi - fungsi `apply`


```R
v <- seq(10,50,by=10)
v
```


<ol class=list-inline>
	<li>10</li>
	<li>20</li>
	<li>30</li>
	<li>40</li>
	<li>50</li>
</ol>




```R
sample(v,2) # mengambil dua buah sampel acak dari vektor
```


<ol class=list-inline>
	<li>30</li>
	<li>20</li>
</ol>




```R
sample(1:100,5)
```


<ol class=list-inline>
	<li>98</li>
	<li>17</li>
	<li>78</li>
	<li>100</li>
	<li>40</li>
</ol>




```R
v <- 1:5
v
```


<ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>




```R
tambah_acak <- function(x){
    acak <- sample(1:100,1)
    return(x + acak)
}
```


```R
tambah_acak(10)
```


63



```R
hasil <- tambah_acak(20)
hasil
```


91


### `lapply()`: dalam bentuk list


```R
lapply(v, tambah_acak)
# outputnya dalam bentuk list
```


<ol>
	<li>80</li>
	<li>95</li>
	<li>36</li>
	<li>102</li>
	<li>8</li>
</ol>



## `sapply()`: dalam bentuk vektor


```R
sapply(v,tambah_acak)
```


<ol class=list-inline>
	<li>52</li>
	<li>8</li>
	<li>84</li>
	<li>22</li>
	<li>8</li>
</ol>




```R
v1 <- seq(5,25, by=5)
kuadrat <- function(bil){
    return(bil^2)
}
```


```R
kuadrat(5)
```


25



```R
lapply(v, kuadrat)
```


<ol>
	<li>1</li>
	<li>4</li>
	<li>9</li>
	<li>16</li>
	<li>25</li>
</ol>




```R
sapply(v, kuadrat)
```


<ol class=list-inline>
	<li>1</li>
	<li>4</li>
	<li>9</li>
	<li>16</li>
	<li>25</li>
</ol>



### Fungsi anonim


```R
v
```


<ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>




```R
kuadrat <- function(bil){
    return(bil^2)
}
```


```R
sapply(v, function(bil){bil^2}) # fungsi anonim
```


<ol class=list-inline>
	<li>1</li>
	<li>4</li>
	<li>9</li>
	<li>16</li>
	<li>25</li>
</ol>



### Fungsi `apply` dengan banyak *input*


```R
v
```


<ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>




```R
tambah_dua_bil <- function(b1,b2){
    return(b1+b2)
}
```


```R
tambah_dua_bil(20,30)
```


50



```R
sapply(v, tambah_dua_bil) # error
```


    Error in FUN(X[[i]], ...): argument "b2" is missing, with no default
    Traceback:


    1. sapply(v, tambah_dua_bil)

    2. lapply(X = X, FUN = FUN, ...)

    3. FUN(X[[i]], ...)



```R
sapply(v, tambah_dua_bil, b2 = 10)
```


<ol class=list-inline>
	<li>11</li>
	<li>12</li>
	<li>13</li>
	<li>14</li>
	<li>15</li>
</ol>



## Ekspresi regular : RegEx


```R
txt <- "Halo semuanya! Selamat Pagi! Cuaca lagi bagus, nih buat touring."
```


```R
txt
```


'Halo semuanya! Selamat Pagi! Cuaca lagi bagus, nih buat touring.'



```R
grepl("Halo",txt) # kata "Halo" ada di txt
```


TRUE



```R
grepl("Malam", txt)
```


FALSE



```R
grepl("halo", txt) # Sifatnya case-sensitive
```


FALSE



```R
v <- c('a','d','k', 'l','t','k')
grepl('k',v)
```


<ol class=list-inline>
	<li>FALSE</li>
	<li>FALSE</li>
	<li>TRUE</li>
	<li>FALSE</li>
	<li>FALSE</li>
	<li>TRUE</li>
</ol>




```R
grep('k',v) # outputnya indeks
```


<ol class=list-inline>
	<li>3</li>
	<li>6</li>
</ol>




```R
grep('a',v)
```


1


## Fungsi - fungsi matematika

### `abs()`: menghitung nilai absolut


```R
abs(-2)
```


2



```R
v <- c(-3,-5,7,10)
abs(v)
```


<ol class=list-inline>
	<li>3</li>
	<li>5</li>
	<li>7</li>
	<li>10</li>
</ol>



### `sum()`: menghitung penjumlahan seluruh elemen


```R
sum(2,4,6)
```


12



```R
v <- c(2,3,4,5)
sum(v)
```


14


### `mean()`: menghitung rata - rata aritmatika   


```R
mean(v)
```


3.5



```R
mean(c(3,4,5))
```


4


### `round()`: membulatkan nilai


```R
round(2.777645)
```


3



```R
round(2.777645, digits=2)
```


2.78



```R
round(2.777645, 4)
```


2.7776


## *Dates* dan *Timestamps*


```R
Sys.Date() # waktu saat ini
```


<time datetime="2020-07-01">2020-07-01</time>



```R
d <- Sys.Date()
d
```


<time datetime="2020-07-01">2020-07-01</time>



```R
class(d)
```


'Date'



```R
d <- '1993-03-13'
d
```


'1993-03-13'



```R
class(d)
```


'character'



```R
# dikonversi menjadi date
b.day <- as.Date(d)
b.day
```


<time datetime="1993-03-13">1993-03-13</time>



```R
class(b.day)
```


'Date'



```R
as.Date('Mar-13-93') # format tidak sesuai
```


    Error in charToDate(x): character string is not in a standard unambiguous format
    Traceback:


    1. as.Date("Mar-13-93")

    2. as.Date.character("Mar-13-93")

    3. charToDate(x)

    4. stop("character string is not in a standard unambiguous format")



```R
as.Date('Mar-13-93', format = '%b-%d-%y')
```


<time datetime="1993-03-13">1993-03-13</time>


* `%d`: hari (desimal)
* `%m`: bulan (desimal)
* `%b`: bulan (singkatan)
* `%B`: bulan (tidak disingkat)
* `%y`: tahun (2 digit)
* `%Y`: tahun (4 digit)


```R
as.Date('March,01,2009', format= "%B, %d, %Y")
```


<time datetime="2009-03-01">2009-03-01</time>



```R
# POSIXct
```


```R
as.POSIXct('11:03:05', format='%H:%M:%S')
```


    [1] "2020-07-01 11:03:05 WIB"



```R
strptime('11:03:05', format = '%H:%M:%S') # lebih banyak dipakai di pemrograman R
```


    [1] "2020-07-01 11:03:05 WIB"

