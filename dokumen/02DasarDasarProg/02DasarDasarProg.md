# Dasar - dasar pemrograman

## Aritmatika


```R
1 + 2
```


3



```R
5 - 3
```


2



```R
5.25 + 3.95
```


9.2



```R
3 * 2
```


6



```R
15 / 2
```


7.5



```R
2 ^ 3
```


8



```R
# operator modulus

15/2 
```


7.5



```R
15 %% 2
```


1



```R
# urutan operasi
15 * 20 + 50 / 2
```


325



```R
15 * 20 + (50 / 2)
```


325



```R
15 * (20 + 50) / 2
```


525


## Variabel


```R
# komentar
v <- 10
```


```R
print(v)
```

    [1] 10



```R
v
```


10



```R
uang <- 100000
uang
```


1e+05



```R
tiket.bioskop <- 2e5 # paling sering digunakan di komunitas R
tiket.bioskop
```


2e+05



```R
tiketBioskop <- 2.05e5
tiketBioskop
```


205000



```R
tiket_bioskop <-2.1e5
tiket_bioskop
```


210000



```R
popcorn <- 5e4
popcorn
```


50000



```R
tiket.bioskop <- tiket.bioskop + popcorn + 2e4
print(tiket.bioskop)
```

    [1] 270000


## Tipe - tipe data

### Numerik


```R
b <- 2
b
```


2



```R
d <- 3.5
d
```


3.5



```R
class(d)
```


'numeric'



```R
class(b)
```


'numeric'


Integer dan float di R dianggap sebagai tipe data numerik

### Logical


```R
TRUE
```


TRUE



```R
FALSE
```


FALSE



```R
T
```


TRUE



```R
F
```


FALSE



```R
a <- TRUE
a
```


TRUE



```R
class(a)
```


'logical'


### Character


```R
"Halo"
```


'Halo'



```R
'Halo'
```


'Halo'



```R
txt <- "Hello world!"
print(txt)
```

    [1] "Hello world!"



```R
class(txt)
```


'character'


## Vektor


```R
num <- c(1,2,3,4,5)
```


```R
class(num)
```


'numeric'



```R
txt <- c('a', 'b', 'c')
txt
```


<ol class=list-inline>
	<li>'a'</li>
	<li>'b'</li>
	<li>'c'</li>
</ol>




```R
class(txt)
```


'character'



```R
l <- c(T,F)
l
```


<ol class=list-inline>
	<li>TRUE</li>
	<li>FALSE</li>
</ol>




```R
class(l)
```


'logical'



```R
v1 <- c(TRUE, 10, 20)
v1
```


<ol class=list-inline>
	<li>1</li>
	<li>10</li>
	<li>20</li>
</ol>




```R
class(v1) # logical dikonversi menjadi numeric
```


'numeric'



```R
v2 <- c('a', 'b', 20)
v2
```


<ol class=list-inline>
	<li>'a'</li>
	<li>'b'</li>
	<li>'20'</li>
</ol>




```R
class(v2) # numeric dikonversi menjadi character
```


'character'



```R
v3 <- c(TRUE, 128, 'Meteorologi')
v3
```


<ol class=list-inline>
	<li>'TRUE'</li>
	<li>'128'</li>
	<li>'Meteorologi'</li>
</ol>




```R
class(v3) # logical & numeric dikonversi menjadi character
```


'character'



```R
# names : metode penamaaan vektor (metode 1) 
hari <- c(1,2,3,4,5,6,7)
hari
```


<ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
	<li>6</li>
	<li>7</li>
</ol>




```R
names(hari) <- c('sen', 'sel', 'rab', 'kam', 'jum', 'sab', 'min')
```


```R
hari
```


<dl class=dl-horizontal>
	<dt>sen</dt>
		<dd>1</dd>
	<dt>sel</dt>
		<dd>2</dd>
	<dt>rab</dt>
		<dd>3</dd>
	<dt>kam</dt>
		<dd>4</dd>
	<dt>jum</dt>
		<dd>5</dd>
	<dt>sab</dt>
		<dd>6</dd>
	<dt>min</dt>
		<dd>7</dd>
</dl>




```R
# names : metode penamaaan vektor (metode 2)
b <-  c('sen', 'sel', 'rab', 'kam', 'jum', 'sab', 'min')
names(hari) <- b
hari
```


<dl class=dl-horizontal>
	<dt>sen</dt>
		<dd>1</dd>
	<dt>sel</dt>
		<dd>2</dd>
	<dt>rab</dt>
		<dd>3</dd>
	<dt>kam</dt>
		<dd>4</dd>
	<dt>jum</dt>
		<dd>5</dd>
	<dt>sab</dt>
		<dd>6</dd>
	<dt>min</dt>
		<dd>7</dd>
</dl>




```R
hari['sen']
```


<strong>sen:</strong> 1



```R
hari[1]
```


<strong>sen:</strong> 1


## Operasi - operasi vektor


```R
v1 <- c(1,2,3,4,5)
v2 <- c(6,7,8,9,10)
```


```R
v1 + v2 # element-by-element
```


<ol class=list-inline>
	<li>7</li>
	<li>9</li>
	<li>11</li>
	<li>13</li>
	<li>15</li>
</ol>




```R
v1 - v2
```


<ol class=list-inline>
	<li>-5</li>
	<li>-5</li>
	<li>-5</li>
	<li>-5</li>
	<li>-5</li>
</ol>




```R
v1 * v2
```


<ol class=list-inline>
	<li>6</li>
	<li>14</li>
	<li>24</li>
	<li>36</li>
	<li>50</li>
</ol>




```R
v2 / v2
```


<ol class=list-inline>
	<li>1</li>
	<li>1</li>
	<li>1</li>
	<li>1</li>
	<li>1</li>
</ol>




```R
sum(v1) # jumlah seluruh v1
```


15



```R
mean(v1) # rata2 v1
```


3



```R
sd(v1) # std v1
```


1.58113883008419



```R
max(v2)
```


10



```R
min(v2)
```


6



```R
prod(v1) # mengalikan seluruh elemen di vektor 
```


120



```R
prod(v2)
```


30240



```R
b <- sum(v1)
print(b)
```

    [1] 15


## Operator - operator perbandingan


```R
4 > 5
```


FALSE



```R
7 > 4
```


TRUE



```R
10 >= 5
```


TRUE



```R
7 <= 5
```


FALSE



```R
8 == 8
```


TRUE



```R
7 != 15
```


TRUE



```R
7 != 7
```


FALSE



```R
# Operator perbandingan pada vektor
v <- c(1,2,3,4,5)
v < 2
```


<ol class=list-inline>
	<li>TRUE</li>
	<li>FALSE</li>
	<li>FALSE</li>
	<li>FALSE</li>
	<li>FALSE</li>
</ol>




```R
v == 3
```


<ol class=list-inline>
	<li>FALSE</li>
	<li>FALSE</li>
	<li>TRUE</li>
	<li>FALSE</li>
	<li>FALSE</li>
</ol>




```R
v2 <- c(10,20,30,40,50)
v2
```


<ol class=list-inline>
	<li>10</li>
	<li>20</li>
	<li>30</li>
	<li>40</li>
	<li>50</li>
</ol>




```R
v < v2
```


<ol class=list-inline>
	<li>TRUE</li>
	<li>TRUE</li>
	<li>TRUE</li>
	<li>TRUE</li>
	<li>TRUE</li>
</ol>



## Pengindeksan dan pemotongan vektor


```R
v1 <- c(10,20,30,40,50)
v2 <- c('a', 'b', 'c', 'd', 'e')
```


```R
v1[2] # pengindeksan dimulai dari 1
```


20



```R
v1[5]
```


50



```R
v2[c(3,4,5)]
```


<ol class=list-inline>
	<li>'c'</li>
	<li>'d'</li>
	<li>'e'</li>
</ol>




```R
v3 <- c(1,2,3,4,5,6,7,8,9,10)
v3[7:10]
```


<ol class=list-inline>
	<li>7</li>
	<li>8</li>
	<li>9</li>
	<li>10</li>
</ol>




```R
v3[3:5]
```


<ol class=list-inline>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>




```R
b <- c(1,2,3,4,5,6)
names(b) <- c('I', 'G', 'D', 'O', 'R', 'E')
b
```


<dl class=dl-horizontal>
	<dt>I</dt>
		<dd>1</dd>
	<dt>G</dt>
		<dd>2</dd>
	<dt>D</dt>
		<dd>3</dd>
	<dt>O</dt>
		<dd>4</dd>
	<dt>R</dt>
		<dd>5</dd>
	<dt>E</dt>
		<dd>6</dd>
</dl>




```R
b[2]
```


<strong>G:</strong> 2



```R
b['G']
```


<strong>G:</strong> 2



```R
b[c(2,3)]
```


<dl class=dl-horizontal>
	<dt>G</dt>
		<dd>2</dd>
	<dt>D</dt>
		<dd>3</dd>
</dl>




```R
b[c('G', 'D')]
```


<dl class=dl-horizontal>
	<dt>G</dt>
		<dd>2</dd>
	<dt>D</dt>
		<dd>3</dd>
</dl>




```R
# Operator perbandingan
b
```


<dl class=dl-horizontal>
	<dt>I</dt>
		<dd>1</dd>
	<dt>G</dt>
		<dd>2</dd>
	<dt>D</dt>
		<dd>3</dd>
	<dt>O</dt>
		<dd>4</dd>
	<dt>R</dt>
		<dd>5</dd>
	<dt>E</dt>
		<dd>6</dd>
</dl>




```R
b[b > 3]
```


<dl class=dl-horizontal>
	<dt>O</dt>
		<dd>4</dd>
	<dt>R</dt>
		<dd>5</dd>
	<dt>E</dt>
		<dd>6</dd>
</dl>




```R
e <-  b > 3
```


```R
b[e]
```


<dl class=dl-horizontal>
	<dt>O</dt>
		<dd>4</dd>
	<dt>R</dt>
		<dd>5</dd>
	<dt>E</dt>
		<dd>6</dd>
</dl>


