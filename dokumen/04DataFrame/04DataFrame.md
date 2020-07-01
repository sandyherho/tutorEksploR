# Data Frame

## Pengenalan

Kita banyak menggunakan data frame di dalam kegiatan analisis data, karena matriks hanya mampu menampung tipe data yang seragam.


```R
state.x77 # built-in df
```


<table>
<thead><tr><th></th><th scope=col>Population</th><th scope=col>Income</th><th scope=col>Illiteracy</th><th scope=col>Life Exp</th><th scope=col>Murder</th><th scope=col>HS Grad</th><th scope=col>Frost</th><th scope=col>Area</th></tr></thead>
<tbody>
	<tr><th scope=row>Alabama</th><td> 3615 </td><td>3624  </td><td>2.1   </td><td>69.05 </td><td>15.1  </td><td>41.3  </td><td> 20   </td><td> 50708</td></tr>
	<tr><th scope=row>Alaska</th><td>  365 </td><td>6315  </td><td>1.5   </td><td>69.31 </td><td>11.3  </td><td>66.7  </td><td>152   </td><td>566432</td></tr>
	<tr><th scope=row>Arizona</th><td> 2212 </td><td>4530  </td><td>1.8   </td><td>70.55 </td><td> 7.8  </td><td>58.1  </td><td> 15   </td><td>113417</td></tr>
	<tr><th scope=row>Arkansas</th><td> 2110 </td><td>3378  </td><td>1.9   </td><td>70.66 </td><td>10.1  </td><td>39.9  </td><td> 65   </td><td> 51945</td></tr>
	<tr><th scope=row>California</th><td>21198 </td><td>5114  </td><td>1.1   </td><td>71.71 </td><td>10.3  </td><td>62.6  </td><td> 20   </td><td>156361</td></tr>
	<tr><th scope=row>Colorado</th><td> 2541 </td><td>4884  </td><td>0.7   </td><td>72.06 </td><td> 6.8  </td><td>63.9  </td><td>166   </td><td>103766</td></tr>
	<tr><th scope=row>Connecticut</th><td> 3100 </td><td>5348  </td><td>1.1   </td><td>72.48 </td><td> 3.1  </td><td>56.0  </td><td>139   </td><td>  4862</td></tr>
	<tr><th scope=row>Delaware</th><td>  579 </td><td>4809  </td><td>0.9   </td><td>70.06 </td><td> 6.2  </td><td>54.6  </td><td>103   </td><td>  1982</td></tr>
	<tr><th scope=row>Florida</th><td> 8277 </td><td>4815  </td><td>1.3   </td><td>70.66 </td><td>10.7  </td><td>52.6  </td><td> 11   </td><td> 54090</td></tr>
	<tr><th scope=row>Georgia</th><td> 4931 </td><td>4091  </td><td>2.0   </td><td>68.54 </td><td>13.9  </td><td>40.6  </td><td> 60   </td><td> 58073</td></tr>
	<tr><th scope=row>Hawaii</th><td>  868 </td><td>4963  </td><td>1.9   </td><td>73.60 </td><td> 6.2  </td><td>61.9  </td><td>  0   </td><td>  6425</td></tr>
	<tr><th scope=row>Idaho</th><td>  813 </td><td>4119  </td><td>0.6   </td><td>71.87 </td><td> 5.3  </td><td>59.5  </td><td>126   </td><td> 82677</td></tr>
	<tr><th scope=row>Illinois</th><td>11197 </td><td>5107  </td><td>0.9   </td><td>70.14 </td><td>10.3  </td><td>52.6  </td><td>127   </td><td> 55748</td></tr>
	<tr><th scope=row>Indiana</th><td> 5313 </td><td>4458  </td><td>0.7   </td><td>70.88 </td><td> 7.1  </td><td>52.9  </td><td>122   </td><td> 36097</td></tr>
	<tr><th scope=row>Iowa</th><td> 2861 </td><td>4628  </td><td>0.5   </td><td>72.56 </td><td> 2.3  </td><td>59.0  </td><td>140   </td><td> 55941</td></tr>
	<tr><th scope=row>Kansas</th><td> 2280 </td><td>4669  </td><td>0.6   </td><td>72.58 </td><td> 4.5  </td><td>59.9  </td><td>114   </td><td> 81787</td></tr>
	<tr><th scope=row>Kentucky</th><td> 3387 </td><td>3712  </td><td>1.6   </td><td>70.10 </td><td>10.6  </td><td>38.5  </td><td> 95   </td><td> 39650</td></tr>
	<tr><th scope=row>Louisiana</th><td> 3806 </td><td>3545  </td><td>2.8   </td><td>68.76 </td><td>13.2  </td><td>42.2  </td><td> 12   </td><td> 44930</td></tr>
	<tr><th scope=row>Maine</th><td> 1058 </td><td>3694  </td><td>0.7   </td><td>70.39 </td><td> 2.7  </td><td>54.7  </td><td>161   </td><td> 30920</td></tr>
	<tr><th scope=row>Maryland</th><td> 4122 </td><td>5299  </td><td>0.9   </td><td>70.22 </td><td> 8.5  </td><td>52.3  </td><td>101   </td><td>  9891</td></tr>
	<tr><th scope=row>Massachusetts</th><td> 5814 </td><td>4755  </td><td>1.1   </td><td>71.83 </td><td> 3.3  </td><td>58.5  </td><td>103   </td><td>  7826</td></tr>
	<tr><th scope=row>Michigan</th><td> 9111 </td><td>4751  </td><td>0.9   </td><td>70.63 </td><td>11.1  </td><td>52.8  </td><td>125   </td><td> 56817</td></tr>
	<tr><th scope=row>Minnesota</th><td> 3921 </td><td>4675  </td><td>0.6   </td><td>72.96 </td><td> 2.3  </td><td>57.6  </td><td>160   </td><td> 79289</td></tr>
	<tr><th scope=row>Mississippi</th><td> 2341 </td><td>3098  </td><td>2.4   </td><td>68.09 </td><td>12.5  </td><td>41.0  </td><td> 50   </td><td> 47296</td></tr>
	<tr><th scope=row>Missouri</th><td> 4767 </td><td>4254  </td><td>0.8   </td><td>70.69 </td><td> 9.3  </td><td>48.8  </td><td>108   </td><td> 68995</td></tr>
	<tr><th scope=row>Montana</th><td>  746 </td><td>4347  </td><td>0.6   </td><td>70.56 </td><td> 5.0  </td><td>59.2  </td><td>155   </td><td>145587</td></tr>
	<tr><th scope=row>Nebraska</th><td> 1544 </td><td>4508  </td><td>0.6   </td><td>72.60 </td><td> 2.9  </td><td>59.3  </td><td>139   </td><td> 76483</td></tr>
	<tr><th scope=row>Nevada</th><td>  590 </td><td>5149  </td><td>0.5   </td><td>69.03 </td><td>11.5  </td><td>65.2  </td><td>188   </td><td>109889</td></tr>
	<tr><th scope=row>New Hampshire</th><td>  812 </td><td>4281  </td><td>0.7   </td><td>71.23 </td><td> 3.3  </td><td>57.6  </td><td>174   </td><td>  9027</td></tr>
	<tr><th scope=row>New Jersey</th><td> 7333 </td><td>5237  </td><td>1.1   </td><td>70.93 </td><td> 5.2  </td><td>52.5  </td><td>115   </td><td>  7521</td></tr>
	<tr><th scope=row>New Mexico</th><td> 1144 </td><td>3601  </td><td>2.2   </td><td>70.32 </td><td> 9.7  </td><td>55.2  </td><td>120   </td><td>121412</td></tr>
	<tr><th scope=row>New York</th><td>18076 </td><td>4903  </td><td>1.4   </td><td>70.55 </td><td>10.9  </td><td>52.7  </td><td> 82   </td><td> 47831</td></tr>
	<tr><th scope=row>North Carolina</th><td> 5441 </td><td>3875  </td><td>1.8   </td><td>69.21 </td><td>11.1  </td><td>38.5  </td><td> 80   </td><td> 48798</td></tr>
	<tr><th scope=row>North Dakota</th><td>  637 </td><td>5087  </td><td>0.8   </td><td>72.78 </td><td> 1.4  </td><td>50.3  </td><td>186   </td><td> 69273</td></tr>
	<tr><th scope=row>Ohio</th><td>10735 </td><td>4561  </td><td>0.8   </td><td>70.82 </td><td> 7.4  </td><td>53.2  </td><td>124   </td><td> 40975</td></tr>
	<tr><th scope=row>Oklahoma</th><td> 2715 </td><td>3983  </td><td>1.1   </td><td>71.42 </td><td> 6.4  </td><td>51.6  </td><td> 82   </td><td> 68782</td></tr>
	<tr><th scope=row>Oregon</th><td> 2284 </td><td>4660  </td><td>0.6   </td><td>72.13 </td><td> 4.2  </td><td>60.0  </td><td> 44   </td><td> 96184</td></tr>
	<tr><th scope=row>Pennsylvania</th><td>11860 </td><td>4449  </td><td>1.0   </td><td>70.43 </td><td> 6.1  </td><td>50.2  </td><td>126   </td><td> 44966</td></tr>
	<tr><th scope=row>Rhode Island</th><td>  931 </td><td>4558  </td><td>1.3   </td><td>71.90 </td><td> 2.4  </td><td>46.4  </td><td>127   </td><td>  1049</td></tr>
	<tr><th scope=row>South Carolina</th><td> 2816 </td><td>3635  </td><td>2.3   </td><td>67.96 </td><td>11.6  </td><td>37.8  </td><td> 65   </td><td> 30225</td></tr>
	<tr><th scope=row>South Dakota</th><td>  681 </td><td>4167  </td><td>0.5   </td><td>72.08 </td><td> 1.7  </td><td>53.3  </td><td>172   </td><td> 75955</td></tr>
	<tr><th scope=row>Tennessee</th><td> 4173 </td><td>3821  </td><td>1.7   </td><td>70.11 </td><td>11.0  </td><td>41.8  </td><td> 70   </td><td> 41328</td></tr>
	<tr><th scope=row>Texas</th><td>12237 </td><td>4188  </td><td>2.2   </td><td>70.90 </td><td>12.2  </td><td>47.4  </td><td> 35   </td><td>262134</td></tr>
	<tr><th scope=row>Utah</th><td> 1203 </td><td>4022  </td><td>0.6   </td><td>72.90 </td><td> 4.5  </td><td>67.3  </td><td>137   </td><td> 82096</td></tr>
	<tr><th scope=row>Vermont</th><td>  472 </td><td>3907  </td><td>0.6   </td><td>71.64 </td><td> 5.5  </td><td>57.1  </td><td>168   </td><td>  9267</td></tr>
	<tr><th scope=row>Virginia</th><td> 4981 </td><td>4701  </td><td>1.4   </td><td>70.08 </td><td> 9.5  </td><td>47.8  </td><td> 85   </td><td> 39780</td></tr>
	<tr><th scope=row>Washington</th><td> 3559 </td><td>4864  </td><td>0.6   </td><td>71.72 </td><td> 4.3  </td><td>63.5  </td><td> 32   </td><td> 66570</td></tr>
	<tr><th scope=row>West Virginia</th><td> 1799 </td><td>3617  </td><td>1.4   </td><td>69.48 </td><td> 6.7  </td><td>41.6  </td><td>100   </td><td> 24070</td></tr>
	<tr><th scope=row>Wisconsin</th><td> 4589 </td><td>4468  </td><td>0.7   </td><td>72.48 </td><td> 3.0  </td><td>54.5  </td><td>149   </td><td> 54464</td></tr>
	<tr><th scope=row>Wyoming</th><td>  376 </td><td>4566  </td><td>0.6   </td><td>70.29 </td><td> 6.9  </td><td>62.9  </td><td>173   </td><td> 97203</td></tr>
</tbody>
</table>




```R
USPersonalExpenditure
```


<table>
<thead><tr><th></th><th scope=col>1940</th><th scope=col>1945</th><th scope=col>1950</th><th scope=col>1955</th><th scope=col>1960</th></tr></thead>
<tbody>
	<tr><th scope=row>Food and Tobacco</th><td>22.200</td><td>44.500</td><td>59.60 </td><td>73.2  </td><td>86.80 </td></tr>
	<tr><th scope=row>Household Operation</th><td>10.500</td><td>15.500</td><td>29.00 </td><td>36.5  </td><td>46.20 </td></tr>
	<tr><th scope=row>Medical and Health</th><td> 3.530</td><td> 5.760</td><td> 9.71 </td><td>14.0  </td><td>21.10 </td></tr>
	<tr><th scope=row>Personal Care</th><td> 1.040</td><td> 1.980</td><td> 2.45 </td><td> 3.4  </td><td> 5.40 </td></tr>
	<tr><th scope=row>Private Education</th><td> 0.341</td><td> 0.974</td><td> 1.80 </td><td> 2.6  </td><td> 3.64 </td></tr>
</tbody>
</table>




```R
# Mengetahui daftar built-in df
# data()
```


```R
head(state.x77) # 6 baris pertama
```


<table>
<thead><tr><th></th><th scope=col>Population</th><th scope=col>Income</th><th scope=col>Illiteracy</th><th scope=col>Life Exp</th><th scope=col>Murder</th><th scope=col>HS Grad</th><th scope=col>Frost</th><th scope=col>Area</th></tr></thead>
<tbody>
	<tr><th scope=row>Alabama</th><td> 3615 </td><td>3624  </td><td>2.1   </td><td>69.05 </td><td>15.1  </td><td>41.3  </td><td> 20   </td><td> 50708</td></tr>
	<tr><th scope=row>Alaska</th><td>  365 </td><td>6315  </td><td>1.5   </td><td>69.31 </td><td>11.3  </td><td>66.7  </td><td>152   </td><td>566432</td></tr>
	<tr><th scope=row>Arizona</th><td> 2212 </td><td>4530  </td><td>1.8   </td><td>70.55 </td><td> 7.8  </td><td>58.1  </td><td> 15   </td><td>113417</td></tr>
	<tr><th scope=row>Arkansas</th><td> 2110 </td><td>3378  </td><td>1.9   </td><td>70.66 </td><td>10.1  </td><td>39.9  </td><td> 65   </td><td> 51945</td></tr>
	<tr><th scope=row>California</th><td>21198 </td><td>5114  </td><td>1.1   </td><td>71.71 </td><td>10.3  </td><td>62.6  </td><td> 20   </td><td>156361</td></tr>
	<tr><th scope=row>Colorado</th><td> 2541 </td><td>4884  </td><td>0.7   </td><td>72.06 </td><td> 6.8  </td><td>63.9  </td><td>166   </td><td>103766</td></tr>
</tbody>
</table>




```R
tail(state.x77) # 6 baris terakhir
```


<table>
<thead><tr><th></th><th scope=col>Population</th><th scope=col>Income</th><th scope=col>Illiteracy</th><th scope=col>Life Exp</th><th scope=col>Murder</th><th scope=col>HS Grad</th><th scope=col>Frost</th><th scope=col>Area</th></tr></thead>
<tbody>
	<tr><th scope=row>Vermont</th><td> 472 </td><td>3907 </td><td>0.6  </td><td>71.64</td><td>5.5  </td><td>57.1 </td><td>168  </td><td> 9267</td></tr>
	<tr><th scope=row>Virginia</th><td>4981 </td><td>4701 </td><td>1.4  </td><td>70.08</td><td>9.5  </td><td>47.8 </td><td> 85  </td><td>39780</td></tr>
	<tr><th scope=row>Washington</th><td>3559 </td><td>4864 </td><td>0.6  </td><td>71.72</td><td>4.3  </td><td>63.5 </td><td> 32  </td><td>66570</td></tr>
	<tr><th scope=row>West Virginia</th><td>1799 </td><td>3617 </td><td>1.4  </td><td>69.48</td><td>6.7  </td><td>41.6 </td><td>100  </td><td>24070</td></tr>
	<tr><th scope=row>Wisconsin</th><td>4589 </td><td>4468 </td><td>0.7  </td><td>72.48</td><td>3.0  </td><td>54.5 </td><td>149  </td><td>54464</td></tr>
	<tr><th scope=row>Wyoming</th><td> 376 </td><td>4566 </td><td>0.6  </td><td>70.29</td><td>6.9  </td><td>62.9 </td><td>173  </td><td>97203</td></tr>
</tbody>
</table>




```R
str(state.x77) # struktur dari df
```

     num [1:50, 1:8] 3615 365 2212 2110 21198 ...
     - attr(*, "dimnames")=List of 2
      ..$ : chr [1:50] "Alabama" "Alaska" "Arizona" "Arkansas" ...
      ..$ : chr [1:8] "Population" "Income" "Illiteracy" "Life Exp" ...



```R
summary(state.x77) # sari statistik dari df berdasarkan kolom
```


       Population        Income       Illiteracy       Life Exp    
     Min.   :  365   Min.   :3098   Min.   :0.500   Min.   :67.96  
     1st Qu.: 1080   1st Qu.:3993   1st Qu.:0.625   1st Qu.:70.12  
     Median : 2838   Median :4519   Median :0.950   Median :70.67  
     Mean   : 4246   Mean   :4436   Mean   :1.170   Mean   :70.88  
     3rd Qu.: 4968   3rd Qu.:4814   3rd Qu.:1.575   3rd Qu.:71.89  
     Max.   :21198   Max.   :6315   Max.   :2.800   Max.   :73.60  
         Murder          HS Grad          Frost             Area       
     Min.   : 1.400   Min.   :37.80   Min.   :  0.00   Min.   :  1049  
     1st Qu.: 4.350   1st Qu.:48.05   1st Qu.: 66.25   1st Qu.: 36985  
     Median : 6.850   Median :53.25   Median :114.50   Median : 54277  
     Mean   : 7.378   Mean   :53.11   Mean   :104.46   Mean   : 70736  
     3rd Qu.:10.675   3rd Qu.:59.15   3rd Qu.:139.75   3rd Qu.: 81162  
     Max.   :15.100   Max.   :67.30   Max.   :188.00   Max.   :566432  



```R
# mendefinisikan df
nama <- c('Agus', 'Sugio', 'Bayu', 'Atmo', 'Roy')
umur <- c(42,35,37,28,27)
kawin <- c(F,F,T,F,T)
```


```R
data.frame(nama, umur, kawin)
```


<table>
<thead><tr><th scope=col>nama</th><th scope=col>umur</th><th scope=col>kawin</th></tr></thead>
<tbody>
	<tr><td>Agus </td><td>42   </td><td>FALSE</td></tr>
	<tr><td>Sugio</td><td>35   </td><td>FALSE</td></tr>
	<tr><td>Bayu </td><td>37   </td><td> TRUE</td></tr>
	<tr><td>Atmo </td><td>28   </td><td>FALSE</td></tr>
	<tr><td>Roy  </td><td>27   </td><td> TRUE</td></tr>
</tbody>
</table>




```R
df <- data.frame(nama, umur, kawin)
df
```


<table>
<thead><tr><th scope=col>nama</th><th scope=col>umur</th><th scope=col>kawin</th></tr></thead>
<tbody>
	<tr><td>Agus </td><td>42   </td><td>FALSE</td></tr>
	<tr><td>Sugio</td><td>35   </td><td>FALSE</td></tr>
	<tr><td>Bayu </td><td>37   </td><td> TRUE</td></tr>
	<tr><td>Atmo </td><td>28   </td><td>FALSE</td></tr>
	<tr><td>Roy  </td><td>27   </td><td> TRUE</td></tr>
</tbody>
</table>




```R
str(df)
```

    'data.frame':	5 obs. of  3 variables:
     $ nama : Factor w/ 5 levels "Agus","Atmo",..: 1 5 3 2 4
     $ umur : num  42 35 37 28 27
     $ kawin: logi  FALSE FALSE TRUE FALSE TRUE



```R
summary(df)
```


        nama        umur        kawin        
     Agus :1   Min.   :27.0   Mode :logical  
     Atmo :1   1st Qu.:28.0   FALSE:3        
     Bayu :1   Median :35.0   TRUE :2        
     Roy  :1   Mean   :33.8                  
     Sugio:1   3rd Qu.:37.0                  
               Max.   :42.0                  


## Seleksi dan pengindeksan Data Frame


```R
df
```


<table>
<thead><tr><th scope=col>nama</th><th scope=col>umur</th><th scope=col>kawin</th></tr></thead>
<tbody>
	<tr><td>Agus </td><td>42   </td><td>FALSE</td></tr>
	<tr><td>Sugio</td><td>35   </td><td>FALSE</td></tr>
	<tr><td>Bayu </td><td>37   </td><td> TRUE</td></tr>
	<tr><td>Atmo </td><td>28   </td><td>FALSE</td></tr>
	<tr><td>Roy  </td><td>27   </td><td> TRUE</td></tr>
</tbody>
</table>




```R
df[3, ] # ambil baris ketiga
```


<table>
<thead><tr><th></th><th scope=col>nama</th><th scope=col>umur</th><th scope=col>kawin</th></tr></thead>
<tbody>
	<tr><th scope=row>3</th><td>Bayu</td><td>37  </td><td>TRUE</td></tr>
</tbody>
</table>




```R
df[,1]
```


<ol class=list-inline>
	<li>Agus</li>
	<li>Sugio</li>
	<li>Bayu</li>
	<li>Atmo</li>
	<li>Roy</li>
</ol>

<details>
	<summary style=display:list-item;cursor:pointer>
		<strong>Levels</strong>:
	</summary>
	<ol class=list-inline>
		<li>'Agus'</li>
		<li>'Atmo'</li>
		<li>'Bayu'</li>
		<li>'Roy'</li>
		<li>'Sugio'</li>
	</ol>
</details>



```R
df[,'nama']
```


<ol class=list-inline>
	<li>Agus</li>
	<li>Sugio</li>
	<li>Bayu</li>
	<li>Atmo</li>
	<li>Roy</li>
</ol>

<details>
	<summary style=display:list-item;cursor:pointer>
		<strong>Levels</strong>:
	</summary>
	<ol class=list-inline>
		<li>'Agus'</li>
		<li>'Atmo'</li>
		<li>'Bayu'</li>
		<li>'Roy'</li>
		<li>'Sugio'</li>
	</ol>
</details>



```R
df[1:4, c('nama', 'umur')]
```


<table>
<thead><tr><th scope=col>nama</th><th scope=col>umur</th></tr></thead>
<tbody>
	<tr><td>Agus </td><td>42   </td></tr>
	<tr><td>Sugio</td><td>35   </td></tr>
	<tr><td>Bayu </td><td>37   </td></tr>
	<tr><td>Atmo </td><td>28   </td></tr>
</tbody>
</table>




```R
df$umur
```


<ol class=list-inline>
	<li>42</li>
	<li>35</li>
	<li>37</li>
	<li>28</li>
	<li>27</li>
</ol>




```R
df[,'umur']
```


<ol class=list-inline>
	<li>42</li>
	<li>35</li>
	<li>37</li>
	<li>28</li>
	<li>27</li>
</ol>




```R
# fungsi subset
df
```


<table>
<thead><tr><th scope=col>nama</th><th scope=col>umur</th><th scope=col>kawin</th></tr></thead>
<tbody>
	<tr><td>Agus </td><td>42   </td><td>FALSE</td></tr>
	<tr><td>Sugio</td><td>35   </td><td>FALSE</td></tr>
	<tr><td>Bayu </td><td>37   </td><td> TRUE</td></tr>
	<tr><td>Atmo </td><td>28   </td><td>FALSE</td></tr>
	<tr><td>Roy  </td><td>27   </td><td> TRUE</td></tr>
</tbody>
</table>




```R
subset(df,subset = kawin == T) 
```


<table>
<thead><tr><th></th><th scope=col>nama</th><th scope=col>umur</th><th scope=col>kawin</th></tr></thead>
<tbody>
	<tr><th scope=row>3</th><td>Bayu</td><td>37  </td><td>TRUE</td></tr>
	<tr><th scope=row>5</th><td>Roy </td><td>27  </td><td>TRUE</td></tr>
</tbody>
</table>




```R
subset(df, subset = umur > 30)
```


<table>
<thead><tr><th scope=col>nama</th><th scope=col>umur</th><th scope=col>kawin</th></tr></thead>
<tbody>
	<tr><td>Agus </td><td>42   </td><td>FALSE</td></tr>
	<tr><td>Sugio</td><td>35   </td><td>FALSE</td></tr>
	<tr><td>Bayu </td><td>37   </td><td> TRUE</td></tr>
</tbody>
</table>




```R
# Mengurutkan dataframe
urut.umur <- order(df['umur'])
urut.umur
```


<ol class=list-inline>
	<li>5</li>
	<li>4</li>
	<li>2</li>
	<li>3</li>
	<li>1</li>
</ol>




```R
df[urut.umur,]
```


<table>
<thead><tr><th></th><th scope=col>nama</th><th scope=col>umur</th><th scope=col>kawin</th></tr></thead>
<tbody>
	<tr><th scope=row>5</th><td>Roy  </td><td>27   </td><td> TRUE</td></tr>
	<tr><th scope=row>4</th><td>Atmo </td><td>28   </td><td>FALSE</td></tr>
	<tr><th scope=row>2</th><td>Sugio</td><td>35   </td><td>FALSE</td></tr>
	<tr><th scope=row>3</th><td>Bayu </td><td>37   </td><td> TRUE</td></tr>
	<tr><th scope=row>1</th><td>Agus </td><td>42   </td><td>FALSE</td></tr>
</tbody>
</table>




```R
umur.terbalik <- order(-df['umur'])
umur.terbalik
```


<ol class=list-inline>
	<li>1</li>
	<li>3</li>
	<li>2</li>
	<li>4</li>
	<li>5</li>
</ol>




```R
df[umur.terbalik,]
```


<table>
<thead><tr><th></th><th scope=col>nama</th><th scope=col>umur</th><th scope=col>kawin</th></tr></thead>
<tbody>
	<tr><th scope=row>1</th><td>Agus </td><td>42   </td><td>FALSE</td></tr>
	<tr><th scope=row>3</th><td>Bayu </td><td>37   </td><td> TRUE</td></tr>
	<tr><th scope=row>2</th><td>Sugio</td><td>35   </td><td>FALSE</td></tr>
	<tr><th scope=row>4</th><td>Atmo </td><td>28   </td><td>FALSE</td></tr>
	<tr><th scope=row>5</th><td>Roy  </td><td>27   </td><td> TRUE</td></tr>
</tbody>
</table>




```R
urut.umur <- order(df$umur)
df[urut.umur, ]
```


<table>
<thead><tr><th></th><th scope=col>nama</th><th scope=col>umur</th><th scope=col>kawin</th></tr></thead>
<tbody>
	<tr><th scope=row>5</th><td>Roy  </td><td>27   </td><td> TRUE</td></tr>
	<tr><th scope=row>4</th><td>Atmo </td><td>28   </td><td>FALSE</td></tr>
	<tr><th scope=row>2</th><td>Sugio</td><td>35   </td><td>FALSE</td></tr>
	<tr><th scope=row>3</th><td>Bayu </td><td>37   </td><td> TRUE</td></tr>
	<tr><th scope=row>1</th><td>Agus </td><td>42   </td><td>FALSE</td></tr>
</tbody>
</table>



## Operasi - operasi data frame

### Mendefinisikan data frame


```R
c1 <- 1:10
c2 <- letters[1:10]
print(c1)
print(c2)
```

     [1]  1  2  3  4  5  6  7  8  9 10
     [1] "a" "b" "c" "d" "e" "f" "g" "h" "i" "j"



```R
df <- data.frame(c1,c2)
df
```


<table>
<thead><tr><th scope=col>c1</th><th scope=col>c2</th></tr></thead>
<tbody>
	<tr><td> 1</td><td>a </td></tr>
	<tr><td> 2</td><td>b </td></tr>
	<tr><td> 3</td><td>c </td></tr>
	<tr><td> 4</td><td>d </td></tr>
	<tr><td> 5</td><td>e </td></tr>
	<tr><td> 6</td><td>f </td></tr>
	<tr><td> 7</td><td>g </td></tr>
	<tr><td> 8</td><td>h </td></tr>
	<tr><td> 9</td><td>i </td></tr>
	<tr><td>10</td><td>j </td></tr>
</tbody>
</table>




```R
df <- data.frame(kolom1 = c1, kolom2 = c2) # nama kolom bisa kita ubah sesuka kita!
df
```


<table>
<thead><tr><th scope=col>kolom1</th><th scope=col>kolom2</th></tr></thead>
<tbody>
	<tr><td> 1</td><td>a </td></tr>
	<tr><td> 2</td><td>b </td></tr>
	<tr><td> 3</td><td>c </td></tr>
	<tr><td> 4</td><td>d </td></tr>
	<tr><td> 5</td><td>e </td></tr>
	<tr><td> 6</td><td>f </td></tr>
	<tr><td> 7</td><td>g </td></tr>
	<tr><td> 8</td><td>h </td></tr>
	<tr><td> 9</td><td>i </td></tr>
	<tr><td>10</td><td>j </td></tr>
</tbody>
</table>



### Mendapatkan info tentang data frame


```R
nrow(df) # jumlah baris
```


10



```R
ncol(df) # jumlah kolom
```


2



```R
colnames(df)  # nama kolom
```


<ol class=list-inline>
	<li>'kolom1'</li>
	<li>'kolom2'</li>
</ol>




```R
rownames(df) # nama baris
```


<ol class=list-inline>
	<li>'1'</li>
	<li>'2'</li>
	<li>'3'</li>
	<li>'4'</li>
	<li>'5'</li>
	<li>'6'</li>
	<li>'7'</li>
	<li>'8'</li>
	<li>'9'</li>
	<li>'10'</li>
</ol>




```R
str(df) # struktur data frame
```

    'data.frame':	10 obs. of  2 variables:
     $ kolom1: int  1 2 3 4 5 6 7 8 9 10
     $ kolom2: Factor w/ 10 levels "a","b","c","d",..: 1 2 3 4 5 6 7 8 9 10



```R
summary(df) # sari statistik
```


         kolom1          kolom2 
     Min.   : 1.00   a      :1  
     1st Qu.: 3.25   b      :1  
     Median : 5.50   c      :1  
     Mean   : 5.50   d      :1  
     3rd Qu.: 7.75   e      :1  
     Max.   :10.00   f      :1  
                     (Other):4  


### Referensi sel


```R
df
```


<table>
<thead><tr><th scope=col>kolom1</th><th scope=col>kolom2</th></tr></thead>
<tbody>
	<tr><td> 1</td><td>a </td></tr>
	<tr><td> 2</td><td>b </td></tr>
	<tr><td> 3</td><td>c </td></tr>
	<tr><td> 4</td><td>d </td></tr>
	<tr><td> 5</td><td>e </td></tr>
	<tr><td> 6</td><td>f </td></tr>
	<tr><td> 7</td><td>g </td></tr>
	<tr><td> 8</td><td>h </td></tr>
	<tr><td> 9</td><td>i </td></tr>
	<tr><td>10</td><td>j </td></tr>
</tbody>
</table>




```R
df[5,1]
```


5



```R
df[[5,1]]
```


5



```R
df[1,'kolom1']
```


1



```R
df[5, 'kolom1']
```


5



```R
df[[5,'kolom1']]
```


5



```R
df[8,'kolom1'] <- -999 # mengubah nilai
df
```


<table>
<thead><tr><th scope=col>kolom1</th><th scope=col>kolom2</th></tr></thead>
<tbody>
	<tr><td>   1</td><td>a   </td></tr>
	<tr><td>   2</td><td>b   </td></tr>
	<tr><td>   3</td><td>c   </td></tr>
	<tr><td>   4</td><td>d   </td></tr>
	<tr><td>   5</td><td>e   </td></tr>
	<tr><td>   6</td><td>f   </td></tr>
	<tr><td>   7</td><td>g   </td></tr>
	<tr><td>-999</td><td>h   </td></tr>
	<tr><td>   9</td><td>i   </td></tr>
	<tr><td>  10</td><td>j   </td></tr>
</tbody>
</table>




```R
df[[8,'kolom1']] <- 8
df
```


<table>
<thead><tr><th scope=col>kolom1</th><th scope=col>kolom2</th></tr></thead>
<tbody>
	<tr><td> 1</td><td>a </td></tr>
	<tr><td> 2</td><td>b </td></tr>
	<tr><td> 3</td><td>c </td></tr>
	<tr><td> 4</td><td>d </td></tr>
	<tr><td> 5</td><td>e </td></tr>
	<tr><td> 6</td><td>f </td></tr>
	<tr><td> 7</td><td>g </td></tr>
	<tr><td> 8</td><td>h </td></tr>
	<tr><td> 9</td><td>i </td></tr>
	<tr><td>10</td><td>j </td></tr>
</tbody>
</table>



### Referensi baris dan kolom


```R
df[2,]
```


<table>
<thead><tr><th></th><th scope=col>kolom1</th><th scope=col>kolom2</th></tr></thead>
<tbody>
	<tr><th scope=row>2</th><td>2</td><td>b</td></tr>
</tbody>
</table>




```R
df[1:3,]
```


<table>
<thead><tr><th scope=col>kolom1</th><th scope=col>kolom2</th></tr></thead>
<tbody>
	<tr><td>1</td><td>a</td></tr>
	<tr><td>2</td><td>b</td></tr>
	<tr><td>3</td><td>c</td></tr>
</tbody>
</table>




```R
head(mtcars)
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
mtcars$mpg
```


<ol class=list-inline>
	<li>21</li>
	<li>21</li>
	<li>22.8</li>
	<li>21.4</li>
	<li>18.7</li>
	<li>18.1</li>
	<li>14.3</li>
	<li>24.4</li>
	<li>22.8</li>
	<li>19.2</li>
	<li>17.8</li>
	<li>16.4</li>
	<li>17.3</li>
	<li>15.2</li>
	<li>10.4</li>
	<li>10.4</li>
	<li>14.7</li>
	<li>32.4</li>
	<li>30.4</li>
	<li>33.9</li>
	<li>21.5</li>
	<li>15.5</li>
	<li>15.2</li>
	<li>13.3</li>
	<li>19.2</li>
	<li>27.3</li>
	<li>26</li>
	<li>30.4</li>
	<li>15.8</li>
	<li>19.7</li>
	<li>15</li>
	<li>21.4</li>
</ol>




```R
mtcars[,1]
```


<ol class=list-inline>
	<li>21</li>
	<li>21</li>
	<li>22.8</li>
	<li>21.4</li>
	<li>18.7</li>
	<li>18.1</li>
	<li>14.3</li>
	<li>24.4</li>
	<li>22.8</li>
	<li>19.2</li>
	<li>17.8</li>
	<li>16.4</li>
	<li>17.3</li>
	<li>15.2</li>
	<li>10.4</li>
	<li>10.4</li>
	<li>14.7</li>
	<li>32.4</li>
	<li>30.4</li>
	<li>33.9</li>
	<li>21.5</li>
	<li>15.5</li>
	<li>15.2</li>
	<li>13.3</li>
	<li>19.2</li>
	<li>27.3</li>
	<li>26</li>
	<li>30.4</li>
	<li>15.8</li>
	<li>19.7</li>
	<li>15</li>
	<li>21.4</li>
</ol>




```R
mtcars[,'mpg']
```


<ol class=list-inline>
	<li>21</li>
	<li>21</li>
	<li>22.8</li>
	<li>21.4</li>
	<li>18.7</li>
	<li>18.1</li>
	<li>14.3</li>
	<li>24.4</li>
	<li>22.8</li>
	<li>19.2</li>
	<li>17.8</li>
	<li>16.4</li>
	<li>17.3</li>
	<li>15.2</li>
	<li>10.4</li>
	<li>10.4</li>
	<li>14.7</li>
	<li>32.4</li>
	<li>30.4</li>
	<li>33.9</li>
	<li>21.5</li>
	<li>15.5</li>
	<li>15.2</li>
	<li>13.3</li>
	<li>19.2</li>
	<li>27.3</li>
	<li>26</li>
	<li>30.4</li>
	<li>15.8</li>
	<li>19.7</li>
	<li>15</li>
	<li>21.4</li>
</ol>




```R
mtcars[['mpg']]
```


<ol class=list-inline>
	<li>21</li>
	<li>21</li>
	<li>22.8</li>
	<li>21.4</li>
	<li>18.7</li>
	<li>18.1</li>
	<li>14.3</li>
	<li>24.4</li>
	<li>22.8</li>
	<li>19.2</li>
	<li>17.8</li>
	<li>16.4</li>
	<li>17.3</li>
	<li>15.2</li>
	<li>10.4</li>
	<li>10.4</li>
	<li>14.7</li>
	<li>32.4</li>
	<li>30.4</li>
	<li>33.9</li>
	<li>21.5</li>
	<li>15.5</li>
	<li>15.2</li>
	<li>13.3</li>
	<li>19.2</li>
	<li>27.3</li>
	<li>26</li>
	<li>30.4</li>
	<li>15.8</li>
	<li>19.7</li>
	<li>15</li>
	<li>21.4</li>
</ol>




```R
mtcars[1] # indeks lokasi kolom:1, cara ini mereferensi kolom mpg sbg data frame
```


<table>
<thead><tr><th></th><th scope=col>mpg</th></tr></thead>
<tbody>
	<tr><th scope=row>Mazda RX4</th><td>21.0</td></tr>
	<tr><th scope=row>Mazda RX4 Wag</th><td>21.0</td></tr>
	<tr><th scope=row>Datsun 710</th><td>22.8</td></tr>
	<tr><th scope=row>Hornet 4 Drive</th><td>21.4</td></tr>
	<tr><th scope=row>Hornet Sportabout</th><td>18.7</td></tr>
	<tr><th scope=row>Valiant</th><td>18.1</td></tr>
	<tr><th scope=row>Duster 360</th><td>14.3</td></tr>
	<tr><th scope=row>Merc 240D</th><td>24.4</td></tr>
	<tr><th scope=row>Merc 230</th><td>22.8</td></tr>
	<tr><th scope=row>Merc 280</th><td>19.2</td></tr>
	<tr><th scope=row>Merc 280C</th><td>17.8</td></tr>
	<tr><th scope=row>Merc 450SE</th><td>16.4</td></tr>
	<tr><th scope=row>Merc 450SL</th><td>17.3</td></tr>
	<tr><th scope=row>Merc 450SLC</th><td>15.2</td></tr>
	<tr><th scope=row>Cadillac Fleetwood</th><td>10.4</td></tr>
	<tr><th scope=row>Lincoln Continental</th><td>10.4</td></tr>
	<tr><th scope=row>Chrysler Imperial</th><td>14.7</td></tr>
	<tr><th scope=row>Fiat 128</th><td>32.4</td></tr>
	<tr><th scope=row>Honda Civic</th><td>30.4</td></tr>
	<tr><th scope=row>Toyota Corolla</th><td>33.9</td></tr>
	<tr><th scope=row>Toyota Corona</th><td>21.5</td></tr>
	<tr><th scope=row>Dodge Challenger</th><td>15.5</td></tr>
	<tr><th scope=row>AMC Javelin</th><td>15.2</td></tr>
	<tr><th scope=row>Camaro Z28</th><td>13.3</td></tr>
	<tr><th scope=row>Pontiac Firebird</th><td>19.2</td></tr>
	<tr><th scope=row>Fiat X1-9</th><td>27.3</td></tr>
	<tr><th scope=row>Porsche 914-2</th><td>26.0</td></tr>
	<tr><th scope=row>Lotus Europa</th><td>30.4</td></tr>
	<tr><th scope=row>Ford Pantera L</th><td>15.8</td></tr>
	<tr><th scope=row>Ferrari Dino</th><td>19.7</td></tr>
	<tr><th scope=row>Maserati Bora</th><td>15.0</td></tr>
	<tr><th scope=row>Volvo 142E</th><td>21.4</td></tr>
</tbody>
</table>




```R
head(mtcars)
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
mtcars[c('mpg', 'cyl')]
```


<table>
<thead><tr><th></th><th scope=col>mpg</th><th scope=col>cyl</th></tr></thead>
<tbody>
	<tr><th scope=row>Mazda RX4</th><td>21.0</td><td>6   </td></tr>
	<tr><th scope=row>Mazda RX4 Wag</th><td>21.0</td><td>6   </td></tr>
	<tr><th scope=row>Datsun 710</th><td>22.8</td><td>4   </td></tr>
	<tr><th scope=row>Hornet 4 Drive</th><td>21.4</td><td>6   </td></tr>
	<tr><th scope=row>Hornet Sportabout</th><td>18.7</td><td>8   </td></tr>
	<tr><th scope=row>Valiant</th><td>18.1</td><td>6   </td></tr>
	<tr><th scope=row>Duster 360</th><td>14.3</td><td>8   </td></tr>
	<tr><th scope=row>Merc 240D</th><td>24.4</td><td>4   </td></tr>
	<tr><th scope=row>Merc 230</th><td>22.8</td><td>4   </td></tr>
	<tr><th scope=row>Merc 280</th><td>19.2</td><td>6   </td></tr>
	<tr><th scope=row>Merc 280C</th><td>17.8</td><td>6   </td></tr>
	<tr><th scope=row>Merc 450SE</th><td>16.4</td><td>8   </td></tr>
	<tr><th scope=row>Merc 450SL</th><td>17.3</td><td>8   </td></tr>
	<tr><th scope=row>Merc 450SLC</th><td>15.2</td><td>8   </td></tr>
	<tr><th scope=row>Cadillac Fleetwood</th><td>10.4</td><td>8   </td></tr>
	<tr><th scope=row>Lincoln Continental</th><td>10.4</td><td>8   </td></tr>
	<tr><th scope=row>Chrysler Imperial</th><td>14.7</td><td>8   </td></tr>
	<tr><th scope=row>Fiat 128</th><td>32.4</td><td>4   </td></tr>
	<tr><th scope=row>Honda Civic</th><td>30.4</td><td>4   </td></tr>
	<tr><th scope=row>Toyota Corolla</th><td>33.9</td><td>4   </td></tr>
	<tr><th scope=row>Toyota Corona</th><td>21.5</td><td>4   </td></tr>
	<tr><th scope=row>Dodge Challenger</th><td>15.5</td><td>8   </td></tr>
	<tr><th scope=row>AMC Javelin</th><td>15.2</td><td>8   </td></tr>
	<tr><th scope=row>Camaro Z28</th><td>13.3</td><td>8   </td></tr>
	<tr><th scope=row>Pontiac Firebird</th><td>19.2</td><td>8   </td></tr>
	<tr><th scope=row>Fiat X1-9</th><td>27.3</td><td>4   </td></tr>
	<tr><th scope=row>Porsche 914-2</th><td>26.0</td><td>4   </td></tr>
	<tr><th scope=row>Lotus Europa</th><td>30.4</td><td>4   </td></tr>
	<tr><th scope=row>Ford Pantera L</th><td>15.8</td><td>8   </td></tr>
	<tr><th scope=row>Ferrari Dino</th><td>19.7</td><td>6   </td></tr>
	<tr><th scope=row>Maserati Bora</th><td>15.0</td><td>8   </td></tr>
	<tr><th scope=row>Volvo 142E</th><td>21.4</td><td>4   </td></tr>
</tbody>
</table>



### Menambahkan baris dan kolom


```R
c1 <- c(10,20,30,40,50)
c2 <- letters[c(1:5)]
df <- data.frame(kol1=c1,kol2=c2)
df
```


<table>
<thead><tr><th scope=col>kol1</th><th scope=col>kol2</th></tr></thead>
<tbody>
	<tr><td>10</td><td>a </td></tr>
	<tr><td>20</td><td>b </td></tr>
	<tr><td>30</td><td>c </td></tr>
	<tr><td>40</td><td>d </td></tr>
	<tr><td>50</td><td>e </td></tr>
</tbody>
</table>




```R
df1 <- data.frame(kol1=128,kol2='Meteorologi')
df1
```


<table>
<thead><tr><th scope=col>kol1</th><th scope=col>kol2</th></tr></thead>
<tbody>
	<tr><td>128        </td><td>Meteorologi</td></tr>
</tbody>
</table>




```R
# menambahkan df1 ke df
df <- rbind(df,df1)
df
```


<table>
<thead><tr><th scope=col>kol1</th><th scope=col>kol2</th></tr></thead>
<tbody>
	<tr><td> 10        </td><td>a          </td></tr>
	<tr><td> 20        </td><td>b          </td></tr>
	<tr><td> 30        </td><td>c          </td></tr>
	<tr><td> 40        </td><td>d          </td></tr>
	<tr><td> 50        </td><td>e          </td></tr>
	<tr><td>128        </td><td>Meteorologi</td></tr>
</tbody>
</table>




```R
c3 <- c(11:16)
c3
```


<ol class=list-inline>
	<li>11</li>
	<li>12</li>
	<li>13</li>
	<li>14</li>
	<li>15</li>
	<li>16</li>
</ol>




```R
# menambahkan kolom ke df
df <- cbind(df,kol3=c3)
df
```


<table>
<thead><tr><th scope=col>kol1</th><th scope=col>kol2</th><th scope=col>kol3</th></tr></thead>
<tbody>
	<tr><td> 10        </td><td>a          </td><td>11         </td></tr>
	<tr><td> 20        </td><td>b          </td><td>12         </td></tr>
	<tr><td> 30        </td><td>c          </td><td>13         </td></tr>
	<tr><td> 40        </td><td>d          </td><td>14         </td></tr>
	<tr><td> 50        </td><td>e          </td><td>15         </td></tr>
	<tr><td>128        </td><td>Meteorologi</td><td>16         </td></tr>
</tbody>
</table>




```R
df$kol4 <- c(20,25,30,35,40,45)
df
```


<table>
<thead><tr><th scope=col>kol1</th><th scope=col>kol2</th><th scope=col>kol3</th><th scope=col>kol4</th></tr></thead>
<tbody>
	<tr><td> 10        </td><td>a          </td><td>11         </td><td>20         </td></tr>
	<tr><td> 20        </td><td>b          </td><td>12         </td><td>25         </td></tr>
	<tr><td> 30        </td><td>c          </td><td>13         </td><td>30         </td></tr>
	<tr><td> 40        </td><td>d          </td><td>14         </td><td>35         </td></tr>
	<tr><td> 50        </td><td>e          </td><td>15         </td><td>40         </td></tr>
	<tr><td>128        </td><td>Meteorologi</td><td>16         </td><td>45         </td></tr>
</tbody>
</table>




```R
df$kol5 <- df$kol1 * 2
df
```


<table>
<thead><tr><th scope=col>kol1</th><th scope=col>kol2</th><th scope=col>kol3</th><th scope=col>kol4</th><th scope=col>kol5</th></tr></thead>
<tbody>
	<tr><td> 10        </td><td>a          </td><td>11         </td><td>20         </td><td> 20        </td></tr>
	<tr><td> 20        </td><td>b          </td><td>12         </td><td>25         </td><td> 40        </td></tr>
	<tr><td> 30        </td><td>c          </td><td>13         </td><td>30         </td><td> 60        </td></tr>
	<tr><td> 40        </td><td>d          </td><td>14         </td><td>35         </td><td> 80        </td></tr>
	<tr><td> 50        </td><td>e          </td><td>15         </td><td>40         </td><td>100        </td></tr>
	<tr><td>128        </td><td>Meteorologi</td><td>16         </td><td>45         </td><td>256        </td></tr>
</tbody>
</table>



### Mengatur penamaan kolom


```R
colnames(df) # mengetahui nama kolom
```


<ol class=list-inline>
	<li>'kol1'</li>
	<li>'kol2'</li>
	<li>'kol3'</li>
	<li>'kol4'</li>
	<li>'kol5'</li>
</ol>




```R
colnames(df) <- c('A', 'B', 'C', 'D', 'E') # penamaan ulang nama kolom
df
```


<table>
<thead><tr><th scope=col>A</th><th scope=col>B</th><th scope=col>C</th><th scope=col>D</th><th scope=col>E</th></tr></thead>
<tbody>
	<tr><td> 10        </td><td>a          </td><td>11         </td><td>20         </td><td> 20        </td></tr>
	<tr><td> 20        </td><td>b          </td><td>12         </td><td>25         </td><td> 40        </td></tr>
	<tr><td> 30        </td><td>c          </td><td>13         </td><td>30         </td><td> 60        </td></tr>
	<tr><td> 40        </td><td>d          </td><td>14         </td><td>35         </td><td> 80        </td></tr>
	<tr><td> 50        </td><td>e          </td><td>15         </td><td>40         </td><td>100        </td></tr>
	<tr><td>128        </td><td>Meteorologi</td><td>16         </td><td>45         </td><td>256        </td></tr>
</tbody>
</table>




```R
colnames(df)[1] <- 'X' # penamaan ulang kolom secara individual
df
```


<table>
<thead><tr><th scope=col>X</th><th scope=col>B</th><th scope=col>C</th><th scope=col>D</th><th scope=col>E</th></tr></thead>
<tbody>
	<tr><td> 10        </td><td>a          </td><td>11         </td><td>20         </td><td> 20        </td></tr>
	<tr><td> 20        </td><td>b          </td><td>12         </td><td>25         </td><td> 40        </td></tr>
	<tr><td> 30        </td><td>c          </td><td>13         </td><td>30         </td><td> 60        </td></tr>
	<tr><td> 40        </td><td>d          </td><td>14         </td><td>35         </td><td> 80        </td></tr>
	<tr><td> 50        </td><td>e          </td><td>15         </td><td>40         </td><td>100        </td></tr>
	<tr><td>128        </td><td>Meteorologi</td><td>16         </td><td>45         </td><td>256        </td></tr>
</tbody>
</table>




```R
colnames(df)[c(2,3)] <- c('Y','Z')
df
```


<table>
<thead><tr><th scope=col>X</th><th scope=col>Y</th><th scope=col>Z</th><th scope=col>D</th><th scope=col>E</th></tr></thead>
<tbody>
	<tr><td> 10        </td><td>a          </td><td>11         </td><td>20         </td><td> 20        </td></tr>
	<tr><td> 20        </td><td>b          </td><td>12         </td><td>25         </td><td> 40        </td></tr>
	<tr><td> 30        </td><td>c          </td><td>13         </td><td>30         </td><td> 60        </td></tr>
	<tr><td> 40        </td><td>d          </td><td>14         </td><td>35         </td><td> 80        </td></tr>
	<tr><td> 50        </td><td>e          </td><td>15         </td><td>40         </td><td>100        </td></tr>
	<tr><td>128        </td><td>Meteorologi</td><td>16         </td><td>45         </td><td>256        </td></tr>
</tbody>
</table>



### Menyeleksi banyak baris dan kolom


```R
df[1:3,]
```


<table>
<thead><tr><th scope=col>X</th><th scope=col>Y</th><th scope=col>Z</th><th scope=col>D</th><th scope=col>E</th></tr></thead>
<tbody>
	<tr><td>10</td><td>a </td><td>11</td><td>20</td><td>20</td></tr>
	<tr><td>20</td><td>b </td><td>12</td><td>25</td><td>40</td></tr>
	<tr><td>30</td><td>c </td><td>13</td><td>30</td><td>60</td></tr>
</tbody>
</table>




```R
# menyeleksi seluruh baris, kecuali no 3
df[-3,]
```


<table>
<thead><tr><th></th><th scope=col>X</th><th scope=col>Y</th><th scope=col>Z</th><th scope=col>D</th><th scope=col>E</th></tr></thead>
<tbody>
	<tr><th scope=row>1</th><td> 10        </td><td>a          </td><td>11         </td><td>20         </td><td> 20        </td></tr>
	<tr><th scope=row>2</th><td> 20        </td><td>b          </td><td>12         </td><td>25         </td><td> 40        </td></tr>
	<tr><th scope=row>4</th><td> 40        </td><td>d          </td><td>14         </td><td>35         </td><td> 80        </td></tr>
	<tr><th scope=row>5</th><td> 50        </td><td>e          </td><td>15         </td><td>40         </td><td>100        </td></tr>
	<tr><th scope=row>6</th><td>128        </td><td>Meteorologi</td><td>16         </td><td>45         </td><td>256        </td></tr>
</tbody>
</table>




```R
# penyeleksian kondisional
head(mtcars)
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
mtcars[mtcars$mpg > 20,]
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
mtcars[mtcars$mpg > 20 & mtcars$cyl == 6,]
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
mtcars[mtcars$mpg > 20 & mtcars$cyl == 6, c('mpg', 'cyl','hp')]
```


<table>
<thead><tr><th></th><th scope=col>mpg</th><th scope=col>cyl</th><th scope=col>hp</th></tr></thead>
<tbody>
	<tr><th scope=row>Mazda RX4</th><td>21.0</td><td>6   </td><td>110 </td></tr>
	<tr><th scope=row>Mazda RX4 Wag</th><td>21.0</td><td>6   </td><td>110 </td></tr>
	<tr><th scope=row>Hornet 4 Drive</th><td>21.4</td><td>6   </td><td>110 </td></tr>
</tbody>
</table>




```R
subset(mtcars, mpg > 20 & cyl == 6) # pakai built-in subset function
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
df[,1:3]
```


<table>
<thead><tr><th scope=col>X</th><th scope=col>Y</th><th scope=col>Z</th></tr></thead>
<tbody>
	<tr><td> 10        </td><td>a          </td><td>11         </td></tr>
	<tr><td> 20        </td><td>b          </td><td>12         </td></tr>
	<tr><td> 30        </td><td>c          </td><td>13         </td></tr>
	<tr><td> 40        </td><td>d          </td><td>14         </td></tr>
	<tr><td> 50        </td><td>e          </td><td>15         </td></tr>
	<tr><td>128        </td><td>Meteorologi</td><td>16         </td></tr>
</tbody>
</table>




```R
df[,c(3,5)]
```


<table>
<thead><tr><th scope=col>Z</th><th scope=col>E</th></tr></thead>
<tbody>
	<tr><td>11 </td><td> 20</td></tr>
	<tr><td>12 </td><td> 40</td></tr>
	<tr><td>13 </td><td> 60</td></tr>
	<tr><td>14 </td><td> 80</td></tr>
	<tr><td>15 </td><td>100</td></tr>
	<tr><td>16 </td><td>256</td></tr>
</tbody>
</table>




```R
df[,c('Z', 'E')]
```


<table>
<thead><tr><th scope=col>Z</th><th scope=col>E</th></tr></thead>
<tbody>
	<tr><td>11 </td><td> 20</td></tr>
	<tr><td>12 </td><td> 40</td></tr>
	<tr><td>13 </td><td> 60</td></tr>
	<tr><td>14 </td><td> 80</td></tr>
	<tr><td>15 </td><td>100</td></tr>
	<tr><td>16 </td><td>256</td></tr>
</tbody>
</table>



### Menangani data kosong


```R
df
```


<table>
<thead><tr><th scope=col>X</th><th scope=col>Y</th><th scope=col>Z</th><th scope=col>D</th><th scope=col>E</th></tr></thead>
<tbody>
	<tr><td> 10        </td><td>a          </td><td>11         </td><td>20         </td><td> 20        </td></tr>
	<tr><td> 20        </td><td>b          </td><td>12         </td><td>25         </td><td> 40        </td></tr>
	<tr><td> 30        </td><td>c          </td><td>13         </td><td>30         </td><td> 60        </td></tr>
	<tr><td> 40        </td><td>d          </td><td>14         </td><td>35         </td><td> 80        </td></tr>
	<tr><td> 50        </td><td>e          </td><td>15         </td><td>40         </td><td>100        </td></tr>
	<tr><td>128        </td><td>Meteorologi</td><td>16         </td><td>45         </td><td>256        </td></tr>
</tbody>
</table>




```R
is.na(df) # cek data kosong
```


<table>
<thead><tr><th scope=col>X</th><th scope=col>Y</th><th scope=col>Z</th><th scope=col>D</th><th scope=col>E</th></tr></thead>
<tbody>
	<tr><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td></tr>
	<tr><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td></tr>
	<tr><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td></tr>
	<tr><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td></tr>
	<tr><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td></tr>
	<tr><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td></tr>
</tbody>
</table>




```R
any(is.na(df))
```


FALSE



```R
any(is.na(df$X))
```


FALSE



```R
# Membuat na jadi 0
any(is.na(df)) <- 0.5 # error karena ga ada na
```


    Error in any(is.na(df)) <- 0.5: could not find function "any<-"
    Traceback:




```R
any(is.na(df$D)) <- mean(df$D)  # error karena ga ada na
```


    Error in any(is.na(df$D)) <- mean(df$D): could not find function "any<-"
    Traceback:


