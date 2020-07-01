# Visualisasi data menggunakan `ggplot2`

## Pendahuluan

* `ggplot2` merupakan pustaka visualisasi pada bahasa pemrograman R.
* Dibangun berdasarkan konsep penambahan lapisan (*layer*) dalam visualisasi.
* Terdapat 7 lapisan: Data, Aesthetics, Geometries, Facets, Statistics, Coordinates, Themes.
* 4 lapisan terakhir tidak wajib, namun dpt digunakan untuk kostumisasi.


```R
library(ggplot2)
```

    Registered S3 methods overwritten by 'ggplot2':
      method         from 
      [.quosures     rlang
      c.quosures     rlang
      print.quosures rlang



```R
ggplot(data = mtcars, # 1) Lapisan 1: Data
    aes(x = mpg, y = hp)) # 2) Lapisan 2: Aesthetics
```


![png](output_4_0.png)



```R
# Lapisan 3): Geometrics
pl <- ggplot(data = mtcars,
             aes(x = mpg, y = hp))
pl + geom_point()
```


![png](output_5_0.png)



```R
# 4) Layer 4: Facets
## Membuat kita dapat memplot banyak grafik di dalam satu kanvas

# 5) Layer 5: Statistics

# 6) Layer 6: Coordinates
## Membatasi limit sumbu-x dan y
 
# 7) Lapisan 7: Theme
## Menambahkan tema ke dalam suatu plot
```

## Histogram


```R
library(ggplot2movies)
```


```R
head(movies)
```


<table>
<thead><tr><th scope=col>title</th><th scope=col>year</th><th scope=col>length</th><th scope=col>budget</th><th scope=col>rating</th><th scope=col>votes</th><th scope=col>r1</th><th scope=col>r2</th><th scope=col>r3</th><th scope=col>r4</th><th scope=col>...</th><th scope=col>r9</th><th scope=col>r10</th><th scope=col>mpaa</th><th scope=col>Action</th><th scope=col>Animation</th><th scope=col>Comedy</th><th scope=col>Drama</th><th scope=col>Documentary</th><th scope=col>Romance</th><th scope=col>Short</th></tr></thead>
<tbody>
	<tr><td>$                       </td><td>1971                    </td><td>121                     </td><td>NA                      </td><td>6.4                     </td><td>348                     </td><td> 4.5                    </td><td> 4.5                    </td><td>4.5                     </td><td> 4.5                    </td><td>...                     </td><td> 4.5                    </td><td> 4.5                    </td><td>                        </td><td>0                       </td><td>0                       </td><td>1                       </td><td>1                       </td><td>0                       </td><td>0                       </td><td>0                       </td></tr>
	<tr><td>$1000 a Touchdown       </td><td>1939                    </td><td> 71                     </td><td>NA                      </td><td>6.0                     </td><td> 20                     </td><td> 0.0                    </td><td>14.5                    </td><td>4.5                     </td><td>24.5                    </td><td>...                     </td><td> 4.5                    </td><td>14.5                    </td><td>                        </td><td>0                       </td><td>0                       </td><td>1                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td></tr>
	<tr><td>$21 a Day Once a Month  </td><td>1941                    </td><td>  7                     </td><td>NA                      </td><td>8.2                     </td><td>  5                     </td><td> 0.0                    </td><td> 0.0                    </td><td>0.0                     </td><td> 0.0                    </td><td>...                     </td><td>24.5                    </td><td>24.5                    </td><td>                        </td><td>0                       </td><td>1                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>1                       </td></tr>
	<tr><td>$40,000                 </td><td>1996                    </td><td> 70                     </td><td>NA                      </td><td>8.2                     </td><td>  6                     </td><td>14.5                    </td><td> 0.0                    </td><td>0.0                     </td><td> 0.0                    </td><td>...                     </td><td>34.5                    </td><td>45.5                    </td><td>                        </td><td>0                       </td><td>0                       </td><td>1                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td></tr>
	<tr><td>$50,000 Climax Show, The</td><td>1975                    </td><td> 71                     </td><td>NA                      </td><td>3.4                     </td><td> 17                     </td><td>24.5                    </td><td> 4.5                    </td><td>0.0                     </td><td>14.5                    </td><td>...                     </td><td> 0.0                    </td><td>24.5                    </td><td>                        </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td></tr>
	<tr><td>$pent                   </td><td>2000                    </td><td> 91                     </td><td>NA                      </td><td>4.3                     </td><td> 45                     </td><td> 4.5                    </td><td> 4.5                    </td><td>4.5                     </td><td>14.5                    </td><td>...                     </td><td>14.5                    </td><td>14.5                    </td><td>                        </td><td>0                       </td><td>0                       </td><td>0                       </td><td>1                       </td><td>0                       </td><td>0                       </td><td>0                       </td></tr>
</tbody>
</table>




```R
colnames(movies)
```


<ol class=list-inline>
	<li>'title'</li>
	<li>'year'</li>
	<li>'length'</li>
	<li>'budget'</li>
	<li>'rating'</li>
	<li>'votes'</li>
	<li>'r1'</li>
	<li>'r2'</li>
	<li>'r3'</li>
	<li>'r4'</li>
	<li>'r5'</li>
	<li>'r6'</li>
	<li>'r7'</li>
	<li>'r8'</li>
	<li>'r9'</li>
	<li>'r10'</li>
	<li>'mpaa'</li>
	<li>'Action'</li>
	<li>'Animation'</li>
	<li>'Comedy'</li>
	<li>'Drama'</li>
	<li>'Documentary'</li>
	<li>'Romance'</li>
	<li>'Short'</li>
</ol>



*Cheatsheet* : <url>https://rstudio.com/wp-content/uploads/2015/03/ggplot2-cheatsheet.pdf</url> 


```R
pl <- ggplot(data = movies,
          aes(x = rating))
pl + geom_histogram()
```

    `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.



![png](output_12_1.png)



```R
# Untuk mengetahui lebih lanjut, perintahkan:
# help("geom_histogram")
```


```R
pl + geom_histogram(binwidth=0.1) # binwidth = 0.1
```


![png](output_14_0.png)



```R
pl + geom_histogram(binwidth=0.1, bins=100) # defaultnya bins = 30
```


![png](output_15_0.png)



```R
pl + geom_histogram(binwidth=0.1, bins=100, 
                    color = 'red', fill='green',
                   alpha = 0.4)
```


![png](output_16_0.png)


### Menambahkan label


```R
pl2 <- pl + geom_histogram(binwidth=0.1, bins=100, 
                    color = 'red', fill='green',
                   alpha = 0.4)
pl2 + xlab('Rating Film') + ylab('Banyaknya') + ggtitle("Histogram")
```


![png](output_18_0.png)


### Teknik aesthetics lanjutan


```R
pl + geom_histogram(binwidth=0.1, aes(fill= ..count..))
```


![png](output_20_0.png)


## *Scatterplot*


```R
df <- mtcars
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
pl <- ggplot(data = df, aes(x=wt, y=mpg))
pl + geom_point()
```


![png](output_23_0.png)



```R
pl + geom_point(color = 'red', size=4, alpha = 0.5)
```


![png](output_24_0.png)



```R
# Untuk mengetahui secara lebih lanjut, perintahkan:
# help("geom_point")
```

### Menambahkan pemetaan aesthetics


```R
pl + geom_point(aes(size = hp)) # ukuran titik berdasarkan besaran hp
```


![png](output_27_0.png)



```R
pl + geom_point(aes(size = cyl))  # ukuran titik berdasarkan besaran cyl
```


![png](output_28_0.png)



```R
df$cyl # bersifat kategorikal, maka kita harus menggunakan fungsi factor()
```


<ol class=list-inline>
	<li>6</li>
	<li>6</li>
	<li>4</li>
	<li>6</li>
	<li>8</li>
	<li>6</li>
	<li>8</li>
	<li>4</li>
	<li>4</li>
	<li>6</li>
	<li>6</li>
	<li>8</li>
	<li>8</li>
	<li>8</li>
	<li>8</li>
	<li>8</li>
	<li>8</li>
	<li>4</li>
	<li>4</li>
	<li>4</li>
	<li>4</li>
	<li>8</li>
	<li>8</li>
	<li>8</li>
	<li>8</li>
	<li>4</li>
	<li>4</li>
	<li>4</li>
	<li>8</li>
	<li>6</li>
	<li>8</li>
	<li>4</li>
</ol>




```R
pl + geom_point(aes( size = factor(cyl)))
```

    Warning message:
    “Using size for a discrete variable is not advised.”


![png](output_30_1.png)


Terdapat pesan: 

Warning message:
“Using size for a discrete variable is not advised.”

Maka, lebih baik tidak usah digunakan


```R
pl + geom_point(aes(shape=factor(cyl), size=4)) # pakai ini lebih baik
```


![png](output_32_0.png)



```R
# Kita juga dapat membedakan dengan warna
pl + geom_point(aes(color=factor(cyl), size=4))
```


![png](output_33_0.png)



```R
# Sintaks lengkap
pl + geom_point(aes(color=factor(cyl), shape = factor(cyl), size=4))
```


![png](output_34_0.png)



```R
pl + geom_point(aes(shape = factor(cyl), size=4), color='blue', alpha=0.5)
# menambahkan warna di luar aes
```


![png](output_35_0.png)


### *Hex color coding*


```R
pl + geom_point(size=4, color='green')
```


![png](output_37_0.png)


Cari di mesin pencari: hex color code


```R
pl + geom_point(size=4, color='#269BC9')
```


![png](output_39_0.png)



```R
p <- ggplot(df, aes(x=wt, y=mpg))
pl2 <- p + geom_point(aes(color=hp), size=4)
pl2
```


![png](output_40_0.png)



```R
pl2 + scale_color_gradient(low='green', high='red')
```


![png](output_41_0.png)



```R
# help("geom_point")
```


```R
b <- ggplot(mtcars, aes(mpg, wt, shape = factor(cyl)))
b + geom_point(aes(colour = factor(cyl)), size = 4) +
  geom_point(colour = "grey90", size = 1.5)
b + geom_point(colour = "black", size = 4.5) +
  geom_point(colour = "pink", size = 4) +
  geom_point(aes(shape = factor(cyl)))
```


![png](output_43_0.png)



![png](output_43_1.png)


## Diagram batang

Umum digunakan untuk menangani data kategorikal


```R
df <- mpg
head(mpg)
```


<table>
<thead><tr><th scope=col>manufacturer</th><th scope=col>model</th><th scope=col>displ</th><th scope=col>year</th><th scope=col>cyl</th><th scope=col>trans</th><th scope=col>drv</th><th scope=col>cty</th><th scope=col>hwy</th><th scope=col>fl</th><th scope=col>class</th></tr></thead>
<tbody>
	<tr><td>audi      </td><td>a4        </td><td>1.8       </td><td>1999      </td><td>4         </td><td>auto(l5)  </td><td>f         </td><td>18        </td><td>29        </td><td>p         </td><td>compact   </td></tr>
	<tr><td>audi      </td><td>a4        </td><td>1.8       </td><td>1999      </td><td>4         </td><td>manual(m5)</td><td>f         </td><td>21        </td><td>29        </td><td>p         </td><td>compact   </td></tr>
	<tr><td>audi      </td><td>a4        </td><td>2.0       </td><td>2008      </td><td>4         </td><td>manual(m6)</td><td>f         </td><td>20        </td><td>31        </td><td>p         </td><td>compact   </td></tr>
	<tr><td>audi      </td><td>a4        </td><td>2.0       </td><td>2008      </td><td>4         </td><td>auto(av)  </td><td>f         </td><td>21        </td><td>30        </td><td>p         </td><td>compact   </td></tr>
	<tr><td>audi      </td><td>a4        </td><td>2.8       </td><td>1999      </td><td>6         </td><td>auto(l5)  </td><td>f         </td><td>16        </td><td>26        </td><td>p         </td><td>compact   </td></tr>
	<tr><td>audi      </td><td>a4        </td><td>2.8       </td><td>1999      </td><td>6         </td><td>manual(m5)</td><td>f         </td><td>18        </td><td>26        </td><td>p         </td><td>compact   </td></tr>
</tbody>
</table>




```R
pl <- ggplot(df, aes(x=class)) # class : data kategorikal
pl + geom_bar()
```


![png](output_47_0.png)



```R
# Untuk mengetahui secara lebih lanjut, perintahkan:
# help("geom_bar")
```


```R
pl + geom_bar(color='red')
```


![png](output_49_0.png)



```R
pl + geom_bar(fill='red')
```


![png](output_50_0.png)



```R
pl + geom_bar(aes(fill=drv)) # fill di dasarkan pada jumlah drv
```


![png](output_51_0.png)



```R
pl + geom_bar(aes(fill=drv), position='dodge') # dipisahkan
```


![png](output_52_0.png)



```R
pl + geom_bar(aes(fill=drv), position='fill') # dihitung berdasarkan persentase 
```


![png](output_53_0.png)



```R
# help("geom_bar")
```


```R
# Total engine displacement of each class
pl + geom_bar(aes(weight = displ))
```


![png](output_55_0.png)



```R
# help("geom_bar")
```


```R
# You can also use geom_bar() with continuous data, in which case
# it will show counts at unique locations
df <- data.frame(x = rep(c(2.9, 3.1, 4.5), c(5, 10, 4)))
ggplot(df, aes(x)) + geom_bar()
```


![png](output_57_0.png)


## *Boxplots*

Digunakan untuk menampilkan sari statistik


```R
df <- mtcars
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
pl <- ggplot(df, aes(x = factor(cyl), y = mpg))
pl + geom_boxplot()
```


![png](output_61_0.png)



```R
pl <- ggplot(df, aes(x = cyl, y = mpg)) # tanpa factor
pl + geom_boxplot()
```

    Warning message:
    “Continuous x aesthetic -- did you forget aes(group=...)?”


![png](output_62_1.png)



```R
# help("geom_boxplot")
```


```R
pl <- ggplot(df, aes(x = factor(cyl), y = mpg)) 
pl + geom_boxplot(color='red', fill = 'green')
```


![png](output_64_0.png)



```R
# memutar koordinat
pl + geom_boxplot() + coord_flip()
```


![png](output_65_0.png)



```R
pl + geom_boxplot(aes(fill=factor(cyl))) + theme_dark()
```


![png](output_66_0.png)


## Visualisasi dua variabel


```R
head(movies)
```


<table>
<thead><tr><th scope=col>title</th><th scope=col>year</th><th scope=col>length</th><th scope=col>budget</th><th scope=col>rating</th><th scope=col>votes</th><th scope=col>r1</th><th scope=col>r2</th><th scope=col>r3</th><th scope=col>r4</th><th scope=col>...</th><th scope=col>r9</th><th scope=col>r10</th><th scope=col>mpaa</th><th scope=col>Action</th><th scope=col>Animation</th><th scope=col>Comedy</th><th scope=col>Drama</th><th scope=col>Documentary</th><th scope=col>Romance</th><th scope=col>Short</th></tr></thead>
<tbody>
	<tr><td>$                       </td><td>1971                    </td><td>121                     </td><td>NA                      </td><td>6.4                     </td><td>348                     </td><td> 4.5                    </td><td> 4.5                    </td><td>4.5                     </td><td> 4.5                    </td><td>...                     </td><td> 4.5                    </td><td> 4.5                    </td><td>                        </td><td>0                       </td><td>0                       </td><td>1                       </td><td>1                       </td><td>0                       </td><td>0                       </td><td>0                       </td></tr>
	<tr><td>$1000 a Touchdown       </td><td>1939                    </td><td> 71                     </td><td>NA                      </td><td>6.0                     </td><td> 20                     </td><td> 0.0                    </td><td>14.5                    </td><td>4.5                     </td><td>24.5                    </td><td>...                     </td><td> 4.5                    </td><td>14.5                    </td><td>                        </td><td>0                       </td><td>0                       </td><td>1                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td></tr>
	<tr><td>$21 a Day Once a Month  </td><td>1941                    </td><td>  7                     </td><td>NA                      </td><td>8.2                     </td><td>  5                     </td><td> 0.0                    </td><td> 0.0                    </td><td>0.0                     </td><td> 0.0                    </td><td>...                     </td><td>24.5                    </td><td>24.5                    </td><td>                        </td><td>0                       </td><td>1                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>1                       </td></tr>
	<tr><td>$40,000                 </td><td>1996                    </td><td> 70                     </td><td>NA                      </td><td>8.2                     </td><td>  6                     </td><td>14.5                    </td><td> 0.0                    </td><td>0.0                     </td><td> 0.0                    </td><td>...                     </td><td>34.5                    </td><td>45.5                    </td><td>                        </td><td>0                       </td><td>0                       </td><td>1                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td></tr>
	<tr><td>$50,000 Climax Show, The</td><td>1975                    </td><td> 71                     </td><td>NA                      </td><td>3.4                     </td><td> 17                     </td><td>24.5                    </td><td> 4.5                    </td><td>0.0                     </td><td>14.5                    </td><td>...                     </td><td> 0.0                    </td><td>24.5                    </td><td>                        </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td><td>0                       </td></tr>
	<tr><td>$pent                   </td><td>2000                    </td><td> 91                     </td><td>NA                      </td><td>4.3                     </td><td> 45                     </td><td> 4.5                    </td><td> 4.5                    </td><td>4.5                     </td><td>14.5                    </td><td>...                     </td><td>14.5                    </td><td>14.5                    </td><td>                        </td><td>0                       </td><td>0                       </td><td>0                       </td><td>1                       </td><td>0                       </td><td>0                       </td><td>0                       </td></tr>
</tbody>
</table>




```R
colnames(movies)
```


<ol class=list-inline>
	<li>'title'</li>
	<li>'year'</li>
	<li>'length'</li>
	<li>'budget'</li>
	<li>'rating'</li>
	<li>'votes'</li>
	<li>'r1'</li>
	<li>'r2'</li>
	<li>'r3'</li>
	<li>'r4'</li>
	<li>'r5'</li>
	<li>'r6'</li>
	<li>'r7'</li>
	<li>'r8'</li>
	<li>'r9'</li>
	<li>'r10'</li>
	<li>'mpaa'</li>
	<li>'Action'</li>
	<li>'Animation'</li>
	<li>'Comedy'</li>
	<li>'Drama'</li>
	<li>'Documentary'</li>
	<li>'Romance'</li>
	<li>'Short'</li>
</ol>




```R
pl <- ggplot(movies, aes(x=year, y=rating))
```


```R
pl + geom_bin2d() 
# mirip dengan heatmap
# jumlah kejadian dihitung berdasarkan warna
```


![png](output_71_0.png)



```R
pl + geom_bin2d(bins=10)
```


![png](output_72_0.png)



```R
pl + geom_bin2d(binwidth=c(2,3), bins=10)
```


![png](output_73_0.png)



```R
# help("geom_bin2d")
```


```R
# mengubah warna
pl2 <- pl + geom_bin2d()
pl2 + scale_fill_gradient(high = 'red', low='green')
```


![png](output_75_0.png)



```R
# mengubah shape jadi hexagon
library(hexbin)
pl + geom_hex()
```


![png](output_76_0.png)



```R
pl + geom_density2d()
```


![png](output_77_0.png)


## Koordinat dan *faceting*


```R
head(mpg)
```


<table>
<thead><tr><th scope=col>manufacturer</th><th scope=col>model</th><th scope=col>displ</th><th scope=col>year</th><th scope=col>cyl</th><th scope=col>trans</th><th scope=col>drv</th><th scope=col>cty</th><th scope=col>hwy</th><th scope=col>fl</th><th scope=col>class</th></tr></thead>
<tbody>
	<tr><td>audi      </td><td>a4        </td><td>1.8       </td><td>1999      </td><td>4         </td><td>auto(l5)  </td><td>f         </td><td>18        </td><td>29        </td><td>p         </td><td>compact   </td></tr>
	<tr><td>audi      </td><td>a4        </td><td>1.8       </td><td>1999      </td><td>4         </td><td>manual(m5)</td><td>f         </td><td>21        </td><td>29        </td><td>p         </td><td>compact   </td></tr>
	<tr><td>audi      </td><td>a4        </td><td>2.0       </td><td>2008      </td><td>4         </td><td>manual(m6)</td><td>f         </td><td>20        </td><td>31        </td><td>p         </td><td>compact   </td></tr>
	<tr><td>audi      </td><td>a4        </td><td>2.0       </td><td>2008      </td><td>4         </td><td>auto(av)  </td><td>f         </td><td>21        </td><td>30        </td><td>p         </td><td>compact   </td></tr>
	<tr><td>audi      </td><td>a4        </td><td>2.8       </td><td>1999      </td><td>6         </td><td>auto(l5)  </td><td>f         </td><td>16        </td><td>26        </td><td>p         </td><td>compact   </td></tr>
	<tr><td>audi      </td><td>a4        </td><td>2.8       </td><td>1999      </td><td>6         </td><td>manual(m5)</td><td>f         </td><td>18        </td><td>26        </td><td>p         </td><td>compact   </td></tr>
</tbody>
</table>




```R
# scatterplot simpel
pl <- ggplot(mpg, aes(x=displ, y=hwy)) +
            geom_point()
```


```R
pl
```


![png](output_81_0.png)



```R
# Mengatur limit sumbu-x dan y
pl + coord_cartesian(xlim = c(1,3), ylim = c(14,28))
```


![png](output_82_0.png)



```R
# Mengatur rasio sumbu
pl + coord_fixed(ratio = 1/3) # y/x
```


![png](output_83_0.png)



```R
# Facets
pl
```


![png](output_84_0.png)



```R
pl + facet_grid(.~cyl) # dipisahkan menurut silinder pada sumbu-x
```


![png](output_85_0.png)


 sintaks: `facet_grid(sb-x~sb-y)`


```R
pl + facet_grid(drv~.) # membagi facet sumbu-y dengan menggunakan drv
```


![png](output_87_0.png)



```R
pl + facet_grid(drv~cyl) 
```


![png](output_88_0.png)



```R
# Untuk mengetahui secara lebih lanjut, jalankan perintah:
help("facet_grid")
```


```R
# Use vars() to supply variables from the dataset: (berbasis baris, kolom)
pl + facet_grid(rows = vars(drv))
```


![png](output_90_0.png)



```R
pl + facet_grid(cols = vars(cyl))
```


![png](output_91_0.png)



```R
pl + facet_grid(vars(drv), vars(cyl))
```


![png](output_92_0.png)


## Tema


```R
df <- mtcars
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
pl <- ggplot(df, aes(x=wt, y = mpg)) + geom_point()
pl
```


![png](output_95_0.png)



```R
theme_set(theme_dark()) # mengatur tema untuk seluruh plot di dalam script
pl
```


![png](output_96_0.png)



```R
pl + theme_bw()
```


![png](output_97_0.png)


Untuk tema tambahan kita dapat menjalankan perintah sebagai berikut:


```R
library(ggthemes)
```


```R
pl + theme_wsj() # tema dari Wall Street Journal
```


![png](output_100_0.png)

