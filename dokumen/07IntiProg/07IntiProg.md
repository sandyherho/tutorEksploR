# Konsep - konsep inti pemrograman

## Operator - operator logika

### `&` (AND)


```R
b <- 15
b
```


15



```R
b < 20
```


TRUE



```R
b > 10
```


TRUE



```R
b > 10 & b < 20 # TRUE & TRUE = TRUE
```


TRUE



```R
b > 30 & b < 20 # FALSE & TRUE = FALSE
```


FALSE



```R
(b > 5) & (b < 25) & (b == 15) # TRUE & TRUE & TRUE = TRUE
```


TRUE



```R
(b < 5) & (b < 25) & (b == 15) # FALSE & TRUE & TRUE = FALSE
```


FALSE


### `|` (OR)


```R
(b==10) | (b < 25) # FALSE | TRUE = TRUE
```


TRUE



```R
(b > 10) | (b < 10)
```


TRUE



```R
(b > 10) | (b < 10) | (b == 12)
```


TRUE



```R
TRUE | FALSE
```


TRUE



```R
FALSE | FALSE
```


FALSE


### `!` (NOT)


```R
(b == 10) | (b < 25)
```


TRUE



```R
!((b == 10) | (b < 25))
```


FALSE



```R
!T
```


FALSE



```R
!(b > 10)
```


FALSE


### Penerapan operator - operator logika pada data frame


```R
# Kita juga dapat menggunakan operator - operator logika pada data frame
df <- mtcars
```


```R
head(df)
```


<table>
<thead><tr><th></th><th scope=col>mpg</th><th scope=col>cyl</th><th scope=col>disp</th><th scope=col>hp</th><th scope=col>drat</th><th scope=col>wt</th><th scope=col>qsec</th><th scope=col>vs</th><th scope=col>am</th><th scope=col>gear</th><th scope=col>carb</th></tr></thead>
<tbody>
	<tr><th scope=row>Mazda RX4</th><td>21.0 </td><td>6    </td><td>160  </td><td>110  </td><td>3.90 </td><td>2.620</td><td>16.46</td><td>0    </td><td>1    </td><td>4    </td><td>4    </td></tr>
	<tr><th scope=row>Mazda RX4 Wag</th><td>21.0 </td><td>6    </td><td>160  </td><td>110  </td><td>3.90 </td><td>2.875</td><td>17.02</td><td>0    </td><td>1    </td><td>4    </td><td>4    </td></tr>
	<tr><th scope=row>Datsun 710</th><td>22.8 </td><td>4    </td><td>108  </td><td> 93  </td><td>3.85 </td><td>2.320</td><td>18.61</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Hornet 4 Drive</th><td>21.4 </td><td>6    </td><td>258  </td><td>110  </td><td>3.08 </td><td>3.215</td><td>19.44</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
	<tr><th scope=row>Hornet Sportabout</th><td>18.7 </td><td>8    </td><td>360  </td><td>175  </td><td>3.15 </td><td>3.440</td><td>17.02</td><td>0    </td><td>0    </td><td>3    </td><td>2    </td></tr>
	<tr><th scope=row>Valiant</th><td>18.1 </td><td>6    </td><td>225  </td><td>105  </td><td>2.76 </td><td>3.460</td><td>20.22</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
</tbody>
</table>




```R
df[df$mpg > 20,'mpg']
```


<ol class=list-inline>
	<li>21</li>
	<li>21</li>
	<li>22.8</li>
	<li>21.4</li>
	<li>24.4</li>
	<li>22.8</li>
	<li>32.4</li>
	<li>30.4</li>
	<li>33.9</li>
	<li>21.5</li>
	<li>27.3</li>
	<li>26</li>
	<li>30.4</li>
	<li>21.4</li>
</ol>




```R
subset(df, mpg > 20)
```


<table>
<thead><tr><th></th><th scope=col>mpg</th><th scope=col>cyl</th><th scope=col>disp</th><th scope=col>hp</th><th scope=col>drat</th><th scope=col>wt</th><th scope=col>qsec</th><th scope=col>vs</th><th scope=col>am</th><th scope=col>gear</th><th scope=col>carb</th></tr></thead>
<tbody>
	<tr><th scope=row>Mazda RX4</th><td>21.0 </td><td>6    </td><td>160.0</td><td>110  </td><td>3.90 </td><td>2.620</td><td>16.46</td><td>0    </td><td>1    </td><td>4    </td><td>4    </td></tr>
	<tr><th scope=row>Mazda RX4 Wag</th><td>21.0 </td><td>6    </td><td>160.0</td><td>110  </td><td>3.90 </td><td>2.875</td><td>17.02</td><td>0    </td><td>1    </td><td>4    </td><td>4    </td></tr>
	<tr><th scope=row>Datsun 710</th><td>22.8 </td><td>4    </td><td>108.0</td><td> 93  </td><td>3.85 </td><td>2.320</td><td>18.61</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Hornet 4 Drive</th><td>21.4 </td><td>6    </td><td>258.0</td><td>110  </td><td>3.08 </td><td>3.215</td><td>19.44</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
	<tr><th scope=row>Merc 240D</th><td>24.4 </td><td>4    </td><td>146.7</td><td> 62  </td><td>3.69 </td><td>3.190</td><td>20.00</td><td>1    </td><td>0    </td><td>4    </td><td>2    </td></tr>
	<tr><th scope=row>Merc 230</th><td>22.8 </td><td>4    </td><td>140.8</td><td> 95  </td><td>3.92 </td><td>3.150</td><td>22.90</td><td>1    </td><td>0    </td><td>4    </td><td>2    </td></tr>
	<tr><th scope=row>Fiat 128</th><td>32.4 </td><td>4    </td><td> 78.7</td><td> 66  </td><td>4.08 </td><td>2.200</td><td>19.47</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Honda Civic</th><td>30.4 </td><td>4    </td><td> 75.7</td><td> 52  </td><td>4.93 </td><td>1.615</td><td>18.52</td><td>1    </td><td>1    </td><td>4    </td><td>2    </td></tr>
	<tr><th scope=row>Toyota Corolla</th><td>33.9 </td><td>4    </td><td> 71.1</td><td> 65  </td><td>4.22 </td><td>1.835</td><td>19.90</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Toyota Corona</th><td>21.5 </td><td>4    </td><td>120.1</td><td> 97  </td><td>3.70 </td><td>2.465</td><td>20.01</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
	<tr><th scope=row>Fiat X1-9</th><td>27.3 </td><td>4    </td><td> 79.0</td><td> 66  </td><td>4.08 </td><td>1.935</td><td>18.90</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Porsche 914-2</th><td>26.0 </td><td>4    </td><td>120.3</td><td> 91  </td><td>4.43 </td><td>2.140</td><td>16.70</td><td>0    </td><td>1    </td><td>5    </td><td>2    </td></tr>
	<tr><th scope=row>Lotus Europa</th><td>30.4 </td><td>4    </td><td> 95.1</td><td>113  </td><td>3.77 </td><td>1.513</td><td>16.90</td><td>1    </td><td>1    </td><td>5    </td><td>2    </td></tr>
	<tr><th scope=row>Volvo 142E</th><td>21.4 </td><td>4    </td><td>121.0</td><td>109  </td><td>4.11 </td><td>2.780</td><td>18.60</td><td>1    </td><td>1    </td><td>4    </td><td>2    </td></tr>
</tbody>
</table>




```R
df[(df$mpg > 20) & (df$cyl > 4),]
```


<table>
<thead><tr><th></th><th scope=col>mpg</th><th scope=col>cyl</th><th scope=col>disp</th><th scope=col>hp</th><th scope=col>drat</th><th scope=col>wt</th><th scope=col>qsec</th><th scope=col>vs</th><th scope=col>am</th><th scope=col>gear</th><th scope=col>carb</th></tr></thead>
<tbody>
	<tr><th scope=row>Mazda RX4</th><td>21.0 </td><td>6    </td><td>160  </td><td>110  </td><td>3.90 </td><td>2.620</td><td>16.46</td><td>0    </td><td>1    </td><td>4    </td><td>4    </td></tr>
	<tr><th scope=row>Mazda RX4 Wag</th><td>21.0 </td><td>6    </td><td>160  </td><td>110  </td><td>3.90 </td><td>2.875</td><td>17.02</td><td>0    </td><td>1    </td><td>4    </td><td>4    </td></tr>
	<tr><th scope=row>Hornet 4 Drive</th><td>21.4 </td><td>6    </td><td>258  </td><td>110  </td><td>3.08 </td><td>3.215</td><td>19.44</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
</tbody>
</table>




```R
df[(df$mpg > 20) | (df$cyl > 4),]
```


<table>
<thead><tr><th></th><th scope=col>mpg</th><th scope=col>cyl</th><th scope=col>disp</th><th scope=col>hp</th><th scope=col>drat</th><th scope=col>wt</th><th scope=col>qsec</th><th scope=col>vs</th><th scope=col>am</th><th scope=col>gear</th><th scope=col>carb</th></tr></thead>
<tbody>
	<tr><th scope=row>Mazda RX4</th><td>21.0 </td><td>6    </td><td>160.0</td><td>110  </td><td>3.90 </td><td>2.620</td><td>16.46</td><td>0    </td><td>1    </td><td>4    </td><td>4    </td></tr>
	<tr><th scope=row>Mazda RX4 Wag</th><td>21.0 </td><td>6    </td><td>160.0</td><td>110  </td><td>3.90 </td><td>2.875</td><td>17.02</td><td>0    </td><td>1    </td><td>4    </td><td>4    </td></tr>
	<tr><th scope=row>Datsun 710</th><td>22.8 </td><td>4    </td><td>108.0</td><td> 93  </td><td>3.85 </td><td>2.320</td><td>18.61</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Hornet 4 Drive</th><td>21.4 </td><td>6    </td><td>258.0</td><td>110  </td><td>3.08 </td><td>3.215</td><td>19.44</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
	<tr><th scope=row>Hornet Sportabout</th><td>18.7 </td><td>8    </td><td>360.0</td><td>175  </td><td>3.15 </td><td>3.440</td><td>17.02</td><td>0    </td><td>0    </td><td>3    </td><td>2    </td></tr>
	<tr><th scope=row>Valiant</th><td>18.1 </td><td>6    </td><td>225.0</td><td>105  </td><td>2.76 </td><td>3.460</td><td>20.22</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
	<tr><th scope=row>Duster 360</th><td>14.3 </td><td>8    </td><td>360.0</td><td>245  </td><td>3.21 </td><td>3.570</td><td>15.84</td><td>0    </td><td>0    </td><td>3    </td><td>4    </td></tr>
	<tr><th scope=row>Merc 240D</th><td>24.4 </td><td>4    </td><td>146.7</td><td> 62  </td><td>3.69 </td><td>3.190</td><td>20.00</td><td>1    </td><td>0    </td><td>4    </td><td>2    </td></tr>
	<tr><th scope=row>Merc 230</th><td>22.8 </td><td>4    </td><td>140.8</td><td> 95  </td><td>3.92 </td><td>3.150</td><td>22.90</td><td>1    </td><td>0    </td><td>4    </td><td>2    </td></tr>
	<tr><th scope=row>Merc 280</th><td>19.2 </td><td>6    </td><td>167.6</td><td>123  </td><td>3.92 </td><td>3.440</td><td>18.30</td><td>1    </td><td>0    </td><td>4    </td><td>4    </td></tr>
	<tr><th scope=row>Merc 280C</th><td>17.8 </td><td>6    </td><td>167.6</td><td>123  </td><td>3.92 </td><td>3.440</td><td>18.90</td><td>1    </td><td>0    </td><td>4    </td><td>4    </td></tr>
	<tr><th scope=row>Merc 450SE</th><td>16.4 </td><td>8    </td><td>275.8</td><td>180  </td><td>3.07 </td><td>4.070</td><td>17.40</td><td>0    </td><td>0    </td><td>3    </td><td>3    </td></tr>
	<tr><th scope=row>Merc 450SL</th><td>17.3 </td><td>8    </td><td>275.8</td><td>180  </td><td>3.07 </td><td>3.730</td><td>17.60</td><td>0    </td><td>0    </td><td>3    </td><td>3    </td></tr>
	<tr><th scope=row>Merc 450SLC</th><td>15.2 </td><td>8    </td><td>275.8</td><td>180  </td><td>3.07 </td><td>3.780</td><td>18.00</td><td>0    </td><td>0    </td><td>3    </td><td>3    </td></tr>
	<tr><th scope=row>Cadillac Fleetwood</th><td>10.4 </td><td>8    </td><td>472.0</td><td>205  </td><td>2.93 </td><td>5.250</td><td>17.98</td><td>0    </td><td>0    </td><td>3    </td><td>4    </td></tr>
	<tr><th scope=row>Lincoln Continental</th><td>10.4 </td><td>8    </td><td>460.0</td><td>215  </td><td>3.00 </td><td>5.424</td><td>17.82</td><td>0    </td><td>0    </td><td>3    </td><td>4    </td></tr>
	<tr><th scope=row>Chrysler Imperial</th><td>14.7 </td><td>8    </td><td>440.0</td><td>230  </td><td>3.23 </td><td>5.345</td><td>17.42</td><td>0    </td><td>0    </td><td>3    </td><td>4    </td></tr>
	<tr><th scope=row>Fiat 128</th><td>32.4 </td><td>4    </td><td> 78.7</td><td> 66  </td><td>4.08 </td><td>2.200</td><td>19.47</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Honda Civic</th><td>30.4 </td><td>4    </td><td> 75.7</td><td> 52  </td><td>4.93 </td><td>1.615</td><td>18.52</td><td>1    </td><td>1    </td><td>4    </td><td>2    </td></tr>
	<tr><th scope=row>Toyota Corolla</th><td>33.9 </td><td>4    </td><td> 71.1</td><td> 65  </td><td>4.22 </td><td>1.835</td><td>19.90</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Toyota Corona</th><td>21.5 </td><td>4    </td><td>120.1</td><td> 97  </td><td>3.70 </td><td>2.465</td><td>20.01</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
	<tr><th scope=row>Dodge Challenger</th><td>15.5 </td><td>8    </td><td>318.0</td><td>150  </td><td>2.76 </td><td>3.520</td><td>16.87</td><td>0    </td><td>0    </td><td>3    </td><td>2    </td></tr>
	<tr><th scope=row>AMC Javelin</th><td>15.2 </td><td>8    </td><td>304.0</td><td>150  </td><td>3.15 </td><td>3.435</td><td>17.30</td><td>0    </td><td>0    </td><td>3    </td><td>2    </td></tr>
	<tr><th scope=row>Camaro Z28</th><td>13.3 </td><td>8    </td><td>350.0</td><td>245  </td><td>3.73 </td><td>3.840</td><td>15.41</td><td>0    </td><td>0    </td><td>3    </td><td>4    </td></tr>
	<tr><th scope=row>Pontiac Firebird</th><td>19.2 </td><td>8    </td><td>400.0</td><td>175  </td><td>3.08 </td><td>3.845</td><td>17.05</td><td>0    </td><td>0    </td><td>3    </td><td>2    </td></tr>
	<tr><th scope=row>Fiat X1-9</th><td>27.3 </td><td>4    </td><td> 79.0</td><td> 66  </td><td>4.08 </td><td>1.935</td><td>18.90</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Porsche 914-2</th><td>26.0 </td><td>4    </td><td>120.3</td><td> 91  </td><td>4.43 </td><td>2.140</td><td>16.70</td><td>0    </td><td>1    </td><td>5    </td><td>2    </td></tr>
	<tr><th scope=row>Lotus Europa</th><td>30.4 </td><td>4    </td><td> 95.1</td><td>113  </td><td>3.77 </td><td>1.513</td><td>16.90</td><td>1    </td><td>1    </td><td>5    </td><td>2    </td></tr>
	<tr><th scope=row>Ford Pantera L</th><td>15.8 </td><td>8    </td><td>351.0</td><td>264  </td><td>4.22 </td><td>3.170</td><td>14.50</td><td>0    </td><td>1    </td><td>5    </td><td>4    </td></tr>
	<tr><th scope=row>Ferrari Dino</th><td>19.7 </td><td>6    </td><td>145.0</td><td>175  </td><td>3.62 </td><td>2.770</td><td>15.50</td><td>0    </td><td>1    </td><td>5    </td><td>6    </td></tr>
	<tr><th scope=row>Maserati Bora</th><td>15.0 </td><td>8    </td><td>301.0</td><td>335  </td><td>3.54 </td><td>3.570</td><td>14.60</td><td>0    </td><td>1    </td><td>5    </td><td>8    </td></tr>
	<tr><th scope=row>Volvo 142E</th><td>21.4 </td><td>4    </td><td>121.0</td><td>109  </td><td>4.11 </td><td>2.780</td><td>18.60</td><td>1    </td><td>1    </td><td>4    </td><td>2    </td></tr>
</tbody>
</table>



## Pernyataan `if`, `else`, dan `else if`


```R
if (5 > 3){
    print('Bener, Bro!')
}
```

    [1] "Bener, Bro!"



```R
if (5 < 3){
    print('Bener, Bro!')
}

# tidak ada output karena kondisi FALSE
```


```R
if (5 < 3){
    print('Bener, Bro!')
}else{
    print('Salah, Bro!')
}
```

    [1] "Salah, Bro!"



```R
a <- 10
b <- 20

if (a > b){
    print('a lebih besar dari b.')
}else{
    print('a lebih kecil dari b.')
}
```

    [1] "a lebih kecil dari b."



```R
minuman <- 'Coca Cola'

if (minuman == 'Kopi'){
    print('Ngopi, Bro!')
}else if (minuman == 'Coca Cola'){
    print('Mantap!')
}else if (minuman == 'air putih'){
    print('Bagus, Bro buat kesehatan.')
}else{
    print('Terserah mau minum apa, Bro yang penting halal.')
}
```

    [1] "Mantap!"


## Pengulangan `while`


```R
b <- 0
while (b < 10){
    print(b)
    b = b + 1
}
```

    [1] 0
    [1] 1
    [1] 2
    [1] 3
    [1] 4
    [1] 5
    [1] 6
    [1] 7
    [1] 8
    [1] 9



```R
b <- 0
while (b < 10){
    print(paste0('b sama dengan ',b))
    b = b + 1
}
```

    [1] "b sama dengan 0"
    [1] "b sama dengan 1"
    [1] "b sama dengan 2"
    [1] "b sama dengan 3"
    [1] "b sama dengan 4"
    [1] "b sama dengan 5"
    [1] "b sama dengan 6"
    [1] "b sama dengan 7"
    [1] "b sama dengan 8"
    [1] "b sama dengan 9"



```R
b <- 0
while (b < 10){
    print(paste0('b sama dengan ',b))
    b = b + 1
    if (b == 10){
        print('b sama dengan 10. Pengulangan selesai.')
    }
}
```

    [1] "b sama dengan 0"
    [1] "b sama dengan 1"
    [1] "b sama dengan 2"
    [1] "b sama dengan 3"
    [1] "b sama dengan 4"
    [1] "b sama dengan 5"
    [1] "b sama dengan 6"
    [1] "b sama dengan 7"
    [1] "b sama dengan 8"
    [1] "b sama dengan 9"
    [1] "b sama dengan 10. Pengulangan selesai."



```R
b <- 0
while (b < 10){
    print(paste0('b sama dengan ',b))
    b = b + 1
    if (b == 10){
        print('b sama dengan 10. Pengulangan selesai.')
        print('Yuk Belajar pemrograman R!')
    }
}
```

    [1] "b sama dengan 0"
    [1] "b sama dengan 1"
    [1] "b sama dengan 2"
    [1] "b sama dengan 3"
    [1] "b sama dengan 4"
    [1] "b sama dengan 5"
    [1] "b sama dengan 6"
    [1] "b sama dengan 7"
    [1] "b sama dengan 8"
    [1] "b sama dengan 9"
    [1] "b sama dengan 10. Pengulangan selesai."
    [1] "Yuk Belajar pemrograman R!"



```R
# penggunaan break() untuk mengakhiri pengulangan
b <- 0
while (b < 10){
    print(paste0('b sama dengan ',b))
    b = b + 1
    if (b == 10){
        print('b sama dengan 10. Pengulangan selesai.')
        break()
        print('Yuk Belajar pemrograman R!')
    }
}
```

    [1] "b sama dengan 0"
    [1] "b sama dengan 1"
    [1] "b sama dengan 2"
    [1] "b sama dengan 3"
    [1] "b sama dengan 4"
    [1] "b sama dengan 5"
    [1] "b sama dengan 6"
    [1] "b sama dengan 7"
    [1] "b sama dengan 8"
    [1] "b sama dengan 9"
    [1] "b sama dengan 10. Pengulangan selesai."



```R
b <- 0
while (b < 10){
    print(paste0('b sama dengan ',b))
    b = b + 1
    if (b == 5){
        print('b sama dengan 5. Pengulangan selesai.')
        break()
        print('Yuk Belajar pemrograman R!')
    }
}
```

    [1] "b sama dengan 0"
    [1] "b sama dengan 1"
    [1] "b sama dengan 2"
    [1] "b sama dengan 3"
    [1] "b sama dengan 4"
    [1] "b sama dengan 5. Pengulangan selesai."


## Pengulangan `for`


```R
v <- c(1,2,3,4,5)
```


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
for (i in v){
    print(i)
}
```

    [1] 1
    [1] 2
    [1] 3
    [1] 4
    [1] 5



```R
for (i in v){
    print('Halo')
}
```

    [1] "Halo"
    [1] "Halo"
    [1] "Halo"
    [1] "Halo"
    [1] "Halo"



```R
buah2an <- c('Apel', 'Jeruk', 'Pisang', 'Mangga')

for (buah in buah2an){
    print(buah)
}
```

    [1] "Apel"
    [1] "Jeruk"
    [1] "Pisang"
    [1] "Mangga"



```R
# Pengulangan for pada list
c1 <- c(10,20,30,40,50)
c2 <- c('A', 'B', 'C', 'D', 'E')
df <- data.frame(c1,c2)
df
```


<table>
<thead><tr><th scope=col>c1</th><th scope=col>c2</th></tr></thead>
<tbody>
	<tr><td>10</td><td>A </td></tr>
	<tr><td>20</td><td>B </td></tr>
	<tr><td>30</td><td>C </td></tr>
	<tr><td>40</td><td>D </td></tr>
	<tr><td>50</td><td>E </td></tr>
</tbody>
</table>




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
l <- list(v,df)
l
```


<ol>
	<li><ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>
</li>
	<li><table>
<thead><tr><th scope=col>c1</th><th scope=col>c2</th></tr></thead>
<tbody>
	<tr><td>10</td><td>A </td></tr>
	<tr><td>20</td><td>B </td></tr>
	<tr><td>30</td><td>C </td></tr>
	<tr><td>40</td><td>D </td></tr>
	<tr><td>50</td><td>E </td></tr>
</tbody>
</table>
</li>
</ol>




```R
for (i in l){
    print(i)
}
```

    [1] 1 2 3 4 5
      c1 c2
    1 10  A
    2 20  B
    3 30  C
    4 40  D
    5 50  E



```R
# Pengunaan pengulangan for pada matriks
mat <- matrix(1:25, nrow=5, byrow=T)
mat
```


<table>
<tbody>
	<tr><td> 1</td><td> 2</td><td> 3</td><td> 4</td><td> 5</td></tr>
	<tr><td> 6</td><td> 7</td><td> 8</td><td> 9</td><td>10</td></tr>
	<tr><td>11</td><td>12</td><td>13</td><td>14</td><td>15</td></tr>
	<tr><td>16</td><td>17</td><td>18</td><td>19</td><td>20</td></tr>
	<tr><td>21</td><td>22</td><td>23</td><td>24</td><td>25</td></tr>
</tbody>
</table>




```R
for (num in mat){
    print(num)
}
```

    [1] 1
    [1] 6
    [1] 11
    [1] 16
    [1] 21
    [1] 2
    [1] 7
    [1] 12
    [1] 17
    [1] 22
    [1] 3
    [1] 8
    [1] 13
    [1] 18
    [1] 23
    [1] 4
    [1] 9
    [1] 14
    [1] 19
    [1] 24
    [1] 5
    [1] 10
    [1] 15
    [1] 20
    [1] 25



```R
# Pengulangan for bersarang
for (i in 1:5){
    print(i^2)
}
```

    [1] 1
    [1] 4
    [1] 9
    [1] 16
    [1] 25



```R
for (i in 1:5){
    for (j in 1:2){
        print(i*j)
    }
}
```

    [1] 1
    [1] 2
    [1] 2
    [1] 4
    [1] 3
    [1] 6
    [1] 4
    [1] 8
    [1] 5
    [1] 10



Proses kerjanya:
1. $1 \times 1$
2. $1 \times 2$
3. $2 \times 1$
4. $2 \times 2$
5. $3 \times 1$
6. $3 \times 2$, dst...

## Fungsi


```R
# sintaks
nama_fungsi <- function(arg_1,arg_2, arg_3 = 10){
    # Kode yang hendak dieksekusi
    hasil <- arg_1 + arg_2
    return(hasil)
}
```


```R
salam <- function(){
    print('Halo!')
}
```


```R
salam()
```

    [1] "Halo!"



```R
salam <- function(nama){
    print(paste('Halo', nama, '!'))
}
```


```R
salam('Sandy')
```

    [1] "Halo Sandy !"



```R
salam() # error karena tidak ada nama default
```


    Error in paste("Halo", nama, "!"): argument "nama" is missing, with no default
    Traceback:


    1. salam()

    2. print(paste("Halo", nama, "!"))   # at line 2 of file <text>

    3. paste("Halo", nama, "!")   # at line 2 of file <text>



```R
salam <- function(nama = 'Priska'){
    print(paste('Halo', nama, '!'))
}
```


```R
salam()
```

    [1] "Halo Priska !"



```R
salam('Sandy')
```

    [1] "Halo Sandy !"



```R
penjumlahan <- function(b1,b2){
    print(b1 + b2)
}
```


```R
penjumlahan(10,20)
```

    [1] 30



```R
# Harusnya pakai return 
penjumlahan <- function(b1,b2){
    return(b1 + b2)
}
```


```R
x <- penjumlahan(10,20) # dapat disimpan di variabel
x
```


30



```R
# Jangkauan variabel
kuadrat <- function(x){
    hasil <- x^2
    return(hasil)
}
```


```R
out <- kuadrat(5)
out
```


25



```R
hasil # ga ada karena bersifat lokal
```


    Error in eval(expr, envir, enclos): object 'hasil' not found
    Traceback:




```R
var <- 'Variabel global'
internet <- 'Jaringan global'

jaringan <- function(internet){
    print(var)
    internet <- 'Jaringan lokal'
    print(internet)
}
```


```R
jaringan()
# redefinisi variabel lokal internet
```

    [1] "Variabel global"
    [1] "Jaringan lokal"



```R
print(internet) # di luar fungsi berlaku variabel global
```

    [1] "Jaringan global"

