# Matriks

## Mendefinisikan matriks


```R
b <- 1:10
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
matrix(b) # 10 x 1
```


<table>
<tbody>
	<tr><td> 1</td></tr>
	<tr><td> 2</td></tr>
	<tr><td> 3</td></tr>
	<tr><td> 4</td></tr>
	<tr><td> 5</td></tr>
	<tr><td> 6</td></tr>
	<tr><td> 7</td></tr>
	<tr><td> 8</td></tr>
	<tr><td> 9</td></tr>
	<tr><td>10</td></tr>
</tbody>
</table>




```R
matrix(b, nrow=2, ncol= 5) # by column
```


<table>
<tbody>
	<tr><td>1 </td><td>3 </td><td>5 </td><td>7 </td><td> 9</td></tr>
	<tr><td>2 </td><td>4 </td><td>6 </td><td>8 </td><td>10</td></tr>
</tbody>
</table>




```R
matrix(b, nrow=2, ncol= 5, byrow = T) # by row
```


<table>
<tbody>
	<tr><td>1 </td><td>2 </td><td>3 </td><td>4 </td><td> 5</td></tr>
	<tr><td>6 </td><td>7 </td><td>8 </td><td>9 </td><td>10</td></tr>
</tbody>
</table>




```R
matrix(1:12, nrow = 4, byrow=TRUE) # 4 x 3 by row
```


<table>
<tbody>
	<tr><td> 1</td><td> 2</td><td> 3</td></tr>
	<tr><td> 4</td><td> 5</td><td> 6</td></tr>
	<tr><td> 7</td><td> 8</td><td> 9</td></tr>
	<tr><td>10</td><td>11</td><td>12</td></tr>
</tbody>
</table>




```R
# Mendefinisikan matriks dari vektor
fb <- c(250,255,260,263,265) # bayangkan sebagai harga saham
ms <- c(455,460,465,479, 470)
```


```R
saham <- c(fb, ms)
saham
```


<ol class=list-inline>
	<li>250</li>
	<li>255</li>
	<li>260</li>
	<li>263</li>
	<li>265</li>
	<li>455</li>
	<li>460</li>
	<li>465</li>
	<li>479</li>
	<li>470</li>
</ol>




```R
matriks.saham <- matrix(saham, nrow=2, byrow=T)
matriks.saham
```


<table>
<tbody>
	<tr><td>250</td><td>255</td><td>260</td><td>263</td><td>265</td></tr>
	<tr><td>455</td><td>460</td><td>465</td><td>479</td><td>470</td></tr>
</tbody>
</table>




```R
# Menamakan baris dan kolom
```


```R
hari <- c('sen', 'sel', 'rab', 'kam', 'jum')
perusahaan <- c('fb', 'ms')
```


```R
colnames(matriks.saham) <- hari
rownames(matriks.saham) <- perusahaan
```


```R
matriks.saham
```


<table>
<thead><tr><th></th><th scope=col>sen</th><th scope=col>sel</th><th scope=col>rab</th><th scope=col>kam</th><th scope=col>jum</th></tr></thead>
<tbody>
	<tr><th scope=row>fb</th><td>250</td><td>255</td><td>260</td><td>263</td><td>265</td></tr>
	<tr><th scope=row>ms</th><td>455</td><td>460</td><td>465</td><td>479</td><td>470</td></tr>
</tbody>
</table>



## Aritmatika matriks


```R
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
mat * mat # element-by-element
```


<table>
<tbody>
	<tr><td>  1</td><td>  4</td><td>  9</td><td> 16</td><td> 25</td></tr>
	<tr><td> 36</td><td> 49</td><td> 64</td><td> 81</td><td>100</td></tr>
	<tr><td>121</td><td>144</td><td>169</td><td>196</td><td>225</td></tr>
	<tr><td>256</td><td>289</td><td>324</td><td>361</td><td>400</td></tr>
	<tr><td>441</td><td>484</td><td>529</td><td>576</td><td>625</td></tr>
</tbody>
</table>




```R
mat / mat
```


<table>
<tbody>
	<tr><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr>
	<tr><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr>
	<tr><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr>
	<tr><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr>
	<tr><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr>
</tbody>
</table>




```R
mat^2
```


<table>
<tbody>
	<tr><td>  1</td><td>  4</td><td>  9</td><td> 16</td><td> 25</td></tr>
	<tr><td> 36</td><td> 49</td><td> 64</td><td> 81</td><td>100</td></tr>
	<tr><td>121</td><td>144</td><td>169</td><td>196</td><td>225</td></tr>
	<tr><td>256</td><td>289</td><td>324</td><td>361</td><td>400</td></tr>
	<tr><td>441</td><td>484</td><td>529</td><td>576</td><td>625</td></tr>
</tbody>
</table>




```R
1 / mat
```


<table>
<tbody>
	<tr><td>1.00000000</td><td>0.50000000</td><td>0.33333333</td><td>0.25000000</td><td>0.20000000</td></tr>
	<tr><td>0.16666667</td><td>0.14285714</td><td>0.12500000</td><td>0.11111111</td><td>0.10000000</td></tr>
	<tr><td>0.09090909</td><td>0.08333333</td><td>0.07692308</td><td>0.07142857</td><td>0.06666667</td></tr>
	<tr><td>0.06250000</td><td>0.05882353</td><td>0.05555556</td><td>0.05263158</td><td>0.05000000</td></tr>
	<tr><td>0.04761905</td><td>0.04545455</td><td>0.04347826</td><td>0.04166667</td><td>0.04000000</td></tr>
</tbody>
</table>




```R
# Operator perbandingan di matriks
```


```R
mat > 10
```


<table>
<tbody>
	<tr><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td></tr>
	<tr><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td><td>FALSE</td></tr>
	<tr><td> TRUE</td><td> TRUE</td><td> TRUE</td><td> TRUE</td><td> TRUE</td></tr>
	<tr><td> TRUE</td><td> TRUE</td><td> TRUE</td><td> TRUE</td><td> TRUE</td></tr>
	<tr><td> TRUE</td><td> TRUE</td><td> TRUE</td><td> TRUE</td><td> TRUE</td></tr>
</tbody>
</table>




```R
mat[mat > 10]
```


<ol class=list-inline>
	<li>11</li>
	<li>16</li>
	<li>21</li>
	<li>12</li>
	<li>17</li>
	<li>22</li>
	<li>13</li>
	<li>18</li>
	<li>23</li>
	<li>14</li>
	<li>19</li>
	<li>24</li>
	<li>15</li>
	<li>20</li>
	<li>25</li>
</ol>




```R
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
# Perkalian matriks
mat %*% mat
```


<table>
<tbody>
	<tr><td> 215</td><td> 230</td><td> 245</td><td> 260</td><td> 275</td></tr>
	<tr><td> 490</td><td> 530</td><td> 570</td><td> 610</td><td> 650</td></tr>
	<tr><td> 765</td><td> 830</td><td> 895</td><td> 960</td><td>1025</td></tr>
	<tr><td>1040</td><td>1130</td><td>1220</td><td>1310</td><td>1400</td></tr>
	<tr><td>1315</td><td>1430</td><td>1545</td><td>1660</td><td>1775</td></tr>
</tbody>
</table>



## Operasi - operasi di matriks


```R
# Mendefinisikan matriks dari vektor
fb <- c(250,255,260,263,265)
ms <- c(455,460,465,479, 470)
saham <- c(fb, ms)
matriks.saham <- matrix(saham, nrow=2, byrow=T)
colnames(matriks.saham) <- c('sen', 'sel', 'rab', 'kam', 'jum')
rownames(matriks.saham) <-  c('fb', 'ms')
matriks.saham
```


<table>
<thead><tr><th></th><th scope=col>sen</th><th scope=col>sel</th><th scope=col>rab</th><th scope=col>kam</th><th scope=col>jum</th></tr></thead>
<tbody>
	<tr><th scope=row>fb</th><td>250</td><td>255</td><td>260</td><td>263</td><td>265</td></tr>
	<tr><th scope=row>ms</th><td>455</td><td>460</td><td>465</td><td>479</td><td>470</td></tr>
</tbody>
</table>




```R
colSums(matriks.saham) # penjumlahan pada kolom
```


<dl class=dl-horizontal>
	<dt>sen</dt>
		<dd>705</dd>
	<dt>sel</dt>
		<dd>715</dd>
	<dt>rab</dt>
		<dd>725</dd>
	<dt>kam</dt>
		<dd>742</dd>
	<dt>jum</dt>
		<dd>735</dd>
</dl>




```R
rowSums(matriks.saham)
```


<dl class=dl-horizontal>
	<dt>fb</dt>
		<dd>1293</dd>
	<dt>ms</dt>
		<dd>2329</dd>
</dl>




```R
rowMeans(matriks.saham)
```


<dl class=dl-horizontal>
	<dt>fb</dt>
		<dd>258.6</dd>
	<dt>ms</dt>
		<dd>465.8</dd>
</dl>




```R
colMeans(matriks.saham)
```


<dl class=dl-horizontal>
	<dt>sen</dt>
		<dd>352.5</dd>
	<dt>sel</dt>
		<dd>357.5</dd>
	<dt>rab</dt>
		<dd>362.5</dd>
	<dt>kam</dt>
		<dd>371</dd>
	<dt>jum</dt>
		<dd>367.5</dd>
</dl>




```R
# Menambahkan kolom dan baris ke matriks
```


```R
google <- c(175,180,185,195,190)
saham.int <- rbind(matriks.saham, google)
saham.int
```


<table>
<thead><tr><th></th><th scope=col>sen</th><th scope=col>sel</th><th scope=col>rab</th><th scope=col>kam</th><th scope=col>jum</th></tr></thead>
<tbody>
	<tr><th scope=row>fb</th><td>250</td><td>255</td><td>260</td><td>263</td><td>265</td></tr>
	<tr><th scope=row>ms</th><td>455</td><td>460</td><td>465</td><td>479</td><td>470</td></tr>
	<tr><th scope=row>google</th><td>175</td><td>180</td><td>185</td><td>195</td><td>190</td></tr>
</tbody>
</table>




```R
# Menambahkan kolom ke matriks
rata2 <- rowMeans(saham.int)
rata2
```


<dl class=dl-horizontal>
	<dt>fb</dt>
		<dd>258.6</dd>
	<dt>ms</dt>
		<dd>465.8</dd>
	<dt>google</dt>
		<dd>185</dd>
</dl>




```R
saham.int <- cbind(saham.int, rata2)
saham.int
```


<table>
<thead><tr><th></th><th scope=col>sen</th><th scope=col>sel</th><th scope=col>rab</th><th scope=col>kam</th><th scope=col>jum</th><th scope=col>rata2</th></tr></thead>
<tbody>
	<tr><th scope=row>fb</th><td>250  </td><td>255  </td><td>260  </td><td>263  </td><td>265  </td><td>258.6</td></tr>
	<tr><th scope=row>ms</th><td>455  </td><td>460  </td><td>465  </td><td>479  </td><td>470  </td><td>465.8</td></tr>
	<tr><th scope=row>google</th><td>175  </td><td>180  </td><td>185  </td><td>195  </td><td>190  </td><td>185.0</td></tr>
</tbody>
</table>



## Seleksi dan pengindeksan matriks


```R
v <- c(10,20,30,40,50)
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
v[3]
```


30



```R
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
mat[1,] # baris 1, seluruh kolom
```


<ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>




```R
mat[2,3]
```


8



```R
mat[3,4]
```


14



```R
mat[,3]
```


<ol class=list-inline>
	<li>3</li>
	<li>8</li>
	<li>13</li>
	<li>18</li>
	<li>23</li>
</ol>




```R
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
mat[,5]
```


<ol class=list-inline>
	<li>5</li>
	<li>10</li>
	<li>15</li>
	<li>20</li>
	<li>25</li>
</ol>




```R
mat[1:3,] # baris 1 sampai 3
```


<table>
<tbody>
	<tr><td> 1</td><td> 2</td><td> 3</td><td> 4</td><td> 5</td></tr>
	<tr><td> 6</td><td> 7</td><td> 8</td><td> 9</td><td>10</td></tr>
	<tr><td>11</td><td>12</td><td>13</td><td>14</td><td>15</td></tr>
</tbody>
</table>




```R
mat[,4:5] # kolom 4 hingga 5
```


<table>
<tbody>
	<tr><td> 4</td><td> 5</td></tr>
	<tr><td> 9</td><td>10</td></tr>
	<tr><td>14</td><td>15</td></tr>
	<tr><td>19</td><td>20</td></tr>
	<tr><td>24</td><td>25</td></tr>
</tbody>
</table>




```R
mat[1:2, 1:3] # baris 1 sampai 2, kolom 1 sampai 3
```


<table>
<tbody>
	<tr><td>1</td><td>2</td><td>3</td></tr>
	<tr><td>6</td><td>7</td><td>8</td></tr>
</tbody>
</table>




```R
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
mat[3:5, 3:5]
```


<table>
<tbody>
	<tr><td>13</td><td>14</td><td>15</td></tr>
	<tr><td>18</td><td>19</td><td>20</td></tr>
	<tr><td>23</td><td>24</td><td>25</td></tr>
</tbody>
</table>



## Fungsi `factor()`


```R
vek.warna <- c('merah', 'hijau', 'biru', 'merah', 'merah', 'hijau', 'biru')
```


```R
vek.warna
```


<ol class=list-inline>
	<li>'merah'</li>
	<li>'hijau'</li>
	<li>'biru'</li>
	<li>'merah'</li>
	<li>'merah'</li>
	<li>'hijau'</li>
	<li>'biru'</li>
</ol>




```R
fact.warna <- factor(vek.warna, ordered=T, levels=c('merah', 'hijau', 'biru'))
fact.warna
```


<ol class=list-inline>
	<li>merah</li>
	<li>hijau</li>
	<li>biru</li>
	<li>merah</li>
	<li>merah</li>
	<li>hijau</li>
	<li>biru</li>
</ol>

<details>
	<summary style=display:list-item;cursor:pointer>
		<strong>Levels</strong>:
	</summary>
	<ol class=list-inline>
		<li>'merah'</li>
		<li>'hijau'</li>
		<li>'biru'</li>
	</ol>
</details>



```R
summary(fact.warna)
```


<dl class=dl-horizontal>
	<dt>merah</dt>
		<dd>3</dd>
	<dt>hijau</dt>
		<dd>2</dd>
	<dt>biru</dt>
		<dd>2</dd>
</dl>




```R
summary(vek.warna)
```


       Length     Class      Mode 
            7 character character 

