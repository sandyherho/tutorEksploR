# Penanganan data tabular

## Penanganan data csv


```R
getwd() # tahu di mana posisi kita saat ini
```


'/home/ronggolawe/coding_repo/tutorialStatdasR/notebooks'



```R
setwd("/home/ronggolawe/coding_repo/tutorialStatdasR/notebooks") # mengatur posisi kita
```


```R
getwd()
```


'/home/ronggolawe/coding_repo/tutorialStatdasR/notebooks'



```R
# Membaca csv
data <- read.csv("../data/gaji.csv")
data
```


<table>
<thead><tr><th scope=col>ID</th><th scope=col>NAMA</th><th scope=col>Gaji</th><th scope=col>Jurusan</th></tr></thead>
<tbody>
	<tr><td>1                 </td><td>Petrus            </td><td> 1000000          </td><td>Teologi           </td></tr>
	<tr><td>2                 </td><td>Matius            </td><td> 2000000          </td><td>Filsafat          </td></tr>
	<tr><td>3                 </td><td>Markus            </td><td> 5000000          </td><td>Meteorologi       </td></tr>
	<tr><td>4                 </td><td>Barnabas          </td><td>10000000          </td><td>Teknik Informatika</td></tr>
	<tr><td>5                 </td><td>Thomas            </td><td>20000000          </td><td>Sistem Informasi  </td></tr>
	<tr><td>6                 </td><td>Ignatius          </td><td>  500000          </td><td>Pendidikan Agama  </td></tr>
	<tr><td>7                 </td><td>Aisyah            </td><td>25000000          </td><td>Teknik Elektro    </td></tr>
	<tr><td>8                 </td><td>Supriyanto        </td><td> 1500000          </td><td>Ilmu Perpustakaan </td></tr>
</tbody>
</table>




```R
# menuliskan csv
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
write.csv(mtcars, file = "../data/tes.csv")
```


```R
class(data)
```


'data.frame'



```R
# menuliskan csv dari data frame
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
write.csv(df, file = '../data/tes2.csv')
```


```R
# Untuk mengetahui secara lebih lanjut, perintahkan:
# help(read.csv)
```

## Penanganan data excel


```R
library(readxl) # memuat pustaka readxl
```


```R
excel_sheets("../data/contoh.xlsx") 
```


<ol class=list-inline>
	<li>'Sheet1'</li>
	<li>'Sheet2'</li>
</ol>




```R
# membaca file excel
df <- read_excel("../data/contoh.xlsx", sheet = "Sheet1")
df
```


<table>
<thead><tr><th scope=col>No</th><th scope=col>Nama Depan</th><th scope=col>Nama Belakang</th><th scope=col>Jenis Kelamin</th><th scope=col>Negara</th><th scope=col>Usia</th><th scope=col>ID</th></tr></thead>
<tbody>
	<tr><td>1              </td><td>Fernando       </td><td>Sanchez        </td><td>Pria           </td><td>Meksiko        </td><td>28             </td><td>1562           </td></tr>
	<tr><td>2              </td><td>Sandy          </td><td>Herho          </td><td>Pria           </td><td>Indonesia      </td><td>27             </td><td>1582           </td></tr>
	<tr><td>3              </td><td>Mara           </td><td>Hashimoto      </td><td>Wanita         </td><td>Jepang         </td><td>25             </td><td>2587           </td></tr>
	<tr><td>4              </td><td>Philip         </td><td>Gent           </td><td>Pria           </td><td>Belgia         </td><td>32             </td><td>2468           </td></tr>
	<tr><td>5              </td><td>Satya          </td><td>Narendra       </td><td>Pria           </td><td>India          </td><td>42             </td><td>6548           </td></tr>
	<tr><td>6              </td><td>Vincenza       </td><td>Welland        </td><td>Wanita         </td><td>Amerika Serikat</td><td>40             </td><td>3598           </td></tr>
	<tr><td>7              </td><td>Rudy           </td><td>Salim          </td><td>Pria           </td><td>Indonesia      </td><td>65             </td><td>7865           </td></tr>
	<tr><td>8              </td><td>Gaston         </td><td>Brumm          </td><td>Pria           </td><td>Amerika Serikat</td><td>24             </td><td>2456           </td></tr>
	<tr><td>9              </td><td>Etta           </td><td>Hurn           </td><td>Wanita         </td><td>Britania Raya  </td><td>34             </td><td>1785           </td></tr>
</tbody>
</table>




```R
summary(df)
```


           No     Nama Depan        Nama Belakang      Jenis Kelamin     
     Min.   :1   Length:9           Length:9           Length:9          
     1st Qu.:3   Class :character   Class :character   Class :character  
     Median :5   Mode  :character   Mode  :character   Mode  :character  
     Mean   :5                                                           
     3rd Qu.:7                                                           
     Max.   :9                                                           
        Negara               Usia             ID      
     Length:9           Min.   :24.00   Min.   :1562  
     Class :character   1st Qu.:27.00   1st Qu.:1785  
     Mode  :character   Median :32.00   Median :2468  
                        Mean   :35.22   Mean   :3383  
                        3rd Qu.:40.00   3rd Qu.:3598  
                        Max.   :65.00   Max.   :7865  



```R
str(df)
```

    tibble [9 × 7] (S3: tbl_df/tbl/data.frame)
     $ No           : num [1:9] 1 2 3 4 5 6 7 8 9
     $ Nama Depan   : chr [1:9] "Fernando" "Sandy" "Mara" "Philip" ...
     $ Nama Belakang: chr [1:9] "Sanchez" "Herho" "Hashimoto" "Gent" ...
     $ Jenis Kelamin: chr [1:9] "Pria" "Pria" "Wanita" "Pria" ...
     $ Negara       : chr [1:9] "Meksiko" "Indonesia" "Jepang" "Belgia" ...
     $ Usia         : num [1:9] 28 27 25 32 42 40 65 24 34
     $ ID           : num [1:9] 1562 1582 2587 2468 6548 ...



```R
mean(df$Usia)
```


35.2222222222222



```R
df1 <- read_excel("../data/contoh.xlsx", sheet='Sheet2')
df1
```


<table>
<thead><tr><th scope=col>Bilangan</th><th scope=col>Kuadrat</th></tr></thead>
<tbody>
	<tr><td>1 </td><td> 1</td></tr>
	<tr><td>2 </td><td> 4</td></tr>
	<tr><td>3 </td><td> 9</td></tr>
	<tr><td>4 </td><td>16</td></tr>
	<tr><td>5 </td><td>25</td></tr>
</tbody>
</table>




```R
# menulis file excel
library(writexl)
```


```R
c1 <- c(1:5)
c2 <- 6:10
df2 <- data.frame(c1,c2)
df2
```


<table>
<thead><tr><th scope=col>c1</th><th scope=col>c2</th></tr></thead>
<tbody>
	<tr><td>1 </td><td> 6</td></tr>
	<tr><td>2 </td><td> 7</td></tr>
	<tr><td>3 </td><td> 8</td></tr>
	<tr><td>4 </td><td> 9</td></tr>
	<tr><td>5 </td><td>10</td></tr>
</tbody>
</table>




```R
write_xlsx(df2, "../data/tes.xlsx")
```
