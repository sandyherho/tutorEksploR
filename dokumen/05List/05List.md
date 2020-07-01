# List

Kumpulan berbagai macam tipe data di R


```R
v <- c(1,2,3,4,5)
M <- matrix(1:10, nrow=2)
c1 <- c('Ignatius', 'Laynez', 'Faber', 'Xaverius', 'Kanisius')
c2 <- c(42,37,28,45,43)
```


```R
df <- data.frame(Nama = c1, ID = c2)
df
```


<table>
<thead><tr><th scope=col>Nama</th><th scope=col>ID</th></tr></thead>
<tbody>
	<tr><td>Ignatius</td><td>42      </td></tr>
	<tr><td>Laynez  </td><td>37      </td></tr>
	<tr><td>Faber   </td><td>28      </td></tr>
	<tr><td>Xaverius</td><td>45      </td></tr>
	<tr><td>Kanisius</td><td>43      </td></tr>
</tbody>
</table>




```R
# Pendefinisian list
l <- list(v,M,df)
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
<tbody>
	<tr><td>1 </td><td>3 </td><td>5 </td><td>7 </td><td> 9</td></tr>
	<tr><td>2 </td><td>4 </td><td>6 </td><td>8 </td><td>10</td></tr>
</tbody>
</table>
</li>
	<li><table>
<thead><tr><th scope=col>Nama</th><th scope=col>ID</th></tr></thead>
<tbody>
	<tr><td>Ignatius</td><td>42      </td></tr>
	<tr><td>Laynez  </td><td>37      </td></tr>
	<tr><td>Faber   </td><td>28      </td></tr>
	<tr><td>Xaverius</td><td>45      </td></tr>
	<tr><td>Kanisius</td><td>43      </td></tr>
</tbody>
</table>
</li>
</ol>




```R
# penamaaan ulang indeks list

l2 <- list(sampel_vektor = v, sampel_matriks = M, sample_data_frame = df)
l2
```


<dl>
	<dt>$sampel_vektor</dt>
		<dd><ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>
</dd>
	<dt>$sampel_matriks</dt>
		<dd><table>
<tbody>
	<tr><td>1 </td><td>3 </td><td>5 </td><td>7 </td><td> 9</td></tr>
	<tr><td>2 </td><td>4 </td><td>6 </td><td>8 </td><td>10</td></tr>
</tbody>
</table>
</dd>
	<dt>$sample_data_frame</dt>
		<dd><table>
<thead><tr><th scope=col>Nama</th><th scope=col>ID</th></tr></thead>
<tbody>
	<tr><td>Ignatius</td><td>42      </td></tr>
	<tr><td>Laynez  </td><td>37      </td></tr>
	<tr><td>Faber   </td><td>28      </td></tr>
	<tr><td>Xaverius</td><td>45      </td></tr>
	<tr><td>Kanisius</td><td>43      </td></tr>
</tbody>
</table>
</dd>
</dl>




```R
l2[1]
```


<strong>$sampel_vektor</strong> = <ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>




```R
l2['sampel_vektor']
```


<strong>$sampel_vektor</strong> = <ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>




```R
l2$sampel_vektor
```


<ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>




```R
l2[['sampel_vektor']]
```


<ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>




```R
print(class(l2['sampel_vektor']))
print(class(l2[1]))
```

    [1] "list"
    [1] "list"



```R
print(class(l2$sampel_vektor))
print(class(l2[['sampel_vektor']]))
```

    [1] "numeric"
    [1] "numeric"



```R
# Mengombinasikan dua list
l3 <- c(l,l2)
l3
```


<dl>
	<dt>[[1]]</dt>
		<dd><ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>
</dd>
	<dt>[[2]]</dt>
		<dd><table>
<tbody>
	<tr><td>1 </td><td>3 </td><td>5 </td><td>7 </td><td> 9</td></tr>
	<tr><td>2 </td><td>4 </td><td>6 </td><td>8 </td><td>10</td></tr>
</tbody>
</table>
</dd>
	<dt>[[3]]</dt>
		<dd><table>
<thead><tr><th scope=col>Nama</th><th scope=col>ID</th></tr></thead>
<tbody>
	<tr><td>Ignatius</td><td>42      </td></tr>
	<tr><td>Laynez  </td><td>37      </td></tr>
	<tr><td>Faber   </td><td>28      </td></tr>
	<tr><td>Xaverius</td><td>45      </td></tr>
	<tr><td>Kanisius</td><td>43      </td></tr>
</tbody>
</table>
</dd>
	<dt>$sampel_vektor</dt>
		<dd><ol class=list-inline>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ol>
</dd>
	<dt>$sampel_matriks</dt>
		<dd><table>
<tbody>
	<tr><td>1 </td><td>3 </td><td>5 </td><td>7 </td><td> 9</td></tr>
	<tr><td>2 </td><td>4 </td><td>6 </td><td>8 </td><td>10</td></tr>
</tbody>
</table>
</dd>
	<dt>$sample_data_frame</dt>
		<dd><table>
<thead><tr><th scope=col>Nama</th><th scope=col>ID</th></tr></thead>
<tbody>
	<tr><td>Ignatius</td><td>42      </td></tr>
	<tr><td>Laynez  </td><td>37      </td></tr>
	<tr><td>Faber   </td><td>28      </td></tr>
	<tr><td>Xaverius</td><td>45      </td></tr>
	<tr><td>Kanisius</td><td>43      </td></tr>
</tbody>
</table>
</dd>
</dl>




```R
str(l2)
```

    List of 3
     $ sampel_vektor    : num [1:5] 1 2 3 4 5
     $ sampel_matriks   : int [1:2, 1:5] 1 2 3 4 5 6 7 8 9 10
     $ sample_data_frame:'data.frame':	5 obs. of  2 variables:
      ..$ Nama: Factor w/ 5 levels "Faber","Ignatius",..: 2 4 1 5 3
      ..$ ID  : num [1:5] 42 37 28 45 43



```R
summary(l2)
```


                      Length Class      Mode   
    sampel_vektor      5     -none-     numeric
    sampel_matriks    10     -none-     numeric
    sample_data_frame  2     data.frame list   

