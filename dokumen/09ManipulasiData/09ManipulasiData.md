# Manipulasi data

## dplyr


```R
library(dplyr)
library(nycflights13)
```


    Attaching package: ‘dplyr’
    
    The following objects are masked from ‘package:stats’:
    
        filter, lag
    
    The following objects are masked from ‘package:base’:
    
        intersect, setdiff, setequal, union




```R
head(flights)
```


<table>
<thead><tr><th scope=col>year</th><th scope=col>month</th><th scope=col>day</th><th scope=col>dep_time</th><th scope=col>sched_dep_time</th><th scope=col>dep_delay</th><th scope=col>arr_time</th><th scope=col>sched_arr_time</th><th scope=col>arr_delay</th><th scope=col>carrier</th><th scope=col>flight</th><th scope=col>tailnum</th><th scope=col>origin</th><th scope=col>dest</th><th scope=col>air_time</th><th scope=col>distance</th><th scope=col>hour</th><th scope=col>minute</th><th scope=col>time_hour</th></tr></thead>
<tbody>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>517                </td><td>515                </td><td> 2                 </td><td> 830               </td><td> 819               </td><td> 11                </td><td>UA                 </td><td>1545               </td><td>N14228             </td><td>EWR                </td><td>IAH                </td><td>227                </td><td>1400               </td><td>5                  </td><td>15                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>533                </td><td>529                </td><td> 4                 </td><td> 850               </td><td> 830               </td><td> 20                </td><td>UA                 </td><td>1714               </td><td>N24211             </td><td>LGA                </td><td>IAH                </td><td>227                </td><td>1416               </td><td>5                  </td><td>29                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>542                </td><td>540                </td><td> 2                 </td><td> 923               </td><td> 850               </td><td> 33                </td><td>AA                 </td><td>1141               </td><td>N619AA             </td><td>JFK                </td><td>MIA                </td><td>160                </td><td>1089               </td><td>5                  </td><td>40                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>544                </td><td>545                </td><td>-1                 </td><td>1004               </td><td>1022               </td><td>-18                </td><td>B6                 </td><td> 725               </td><td>N804JB             </td><td>JFK                </td><td>BQN                </td><td>183                </td><td>1576               </td><td>5                  </td><td>45                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>554                </td><td>600                </td><td>-6                 </td><td> 812               </td><td> 837               </td><td>-25                </td><td>DL                 </td><td> 461               </td><td>N668DN             </td><td>LGA                </td><td>ATL                </td><td>116                </td><td> 762               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>554                </td><td>558                </td><td>-4                 </td><td> 740               </td><td> 728               </td><td> 12                </td><td>UA                 </td><td>1696               </td><td>N39463             </td><td>EWR                </td><td>ORD                </td><td>150                </td><td> 719               </td><td>5                  </td><td>58                 </td><td>2013-01-01 05:00:00</td></tr>
</tbody>
</table>



### `filter()`


```R
head(filter(flights,month == 5, day == 2, carrier == 'AA'))
```


<table>
<thead><tr><th scope=col>year</th><th scope=col>month</th><th scope=col>day</th><th scope=col>dep_time</th><th scope=col>sched_dep_time</th><th scope=col>dep_delay</th><th scope=col>arr_time</th><th scope=col>sched_arr_time</th><th scope=col>arr_delay</th><th scope=col>carrier</th><th scope=col>flight</th><th scope=col>tailnum</th><th scope=col>origin</th><th scope=col>dest</th><th scope=col>air_time</th><th scope=col>distance</th><th scope=col>hour</th><th scope=col>minute</th><th scope=col>time_hour</th></tr></thead>
<tbody>
	<tr><td>2013               </td><td>5                  </td><td>2                  </td><td>539                </td><td>540                </td><td> -1                </td><td>850                </td><td>840                </td><td> 10                </td><td>AA                 </td><td> 701               </td><td>N5DYAA             </td><td>JFK                </td><td>MIA                </td><td>149                </td><td>1089               </td><td>5                  </td><td>40                 </td><td>2013-05-02 05:00:00</td></tr>
	<tr><td>2013               </td><td>5                  </td><td>2                  </td><td>549                </td><td>600                </td><td>-11                </td><td>823                </td><td>850                </td><td>-27                </td><td>AA                 </td><td> 707               </td><td>N3ANAA             </td><td>LGA                </td><td>DFW                </td><td>191                </td><td>1389               </td><td>6                  </td><td> 0                 </td><td>2013-05-02 06:00:00</td></tr>
	<tr><td>2013               </td><td>5                  </td><td>2                  </td><td>558                </td><td>605                </td><td> -7                </td><td>855                </td><td>910                </td><td>-15                </td><td>AA                 </td><td>1837               </td><td>N3FRAA             </td><td>LGA                </td><td>MIA                </td><td>149                </td><td>1096               </td><td>6                  </td><td> 5                 </td><td>2013-05-02 06:00:00</td></tr>
	<tr><td>2013               </td><td>5                  </td><td>2                  </td><td>603                </td><td>610                </td><td> -7                </td><td>729                </td><td>745                </td><td>-16                </td><td>AA                 </td><td> 301               </td><td>N4YJAA             </td><td>LGA                </td><td>ORD                </td><td>109                </td><td> 733               </td><td>6                  </td><td>10                 </td><td>2013-05-02 06:00:00</td></tr>
	<tr><td>2013               </td><td>5                  </td><td>2                  </td><td>611                </td><td>615                </td><td> -4                </td><td>900                </td><td>915                </td><td>-15                </td><td>AA                 </td><td>1895               </td><td>N3HEAA             </td><td>EWR                </td><td>MIA                </td><td>146                </td><td>1085               </td><td>6                  </td><td>15                 </td><td>2013-05-02 06:00:00</td></tr>
	<tr><td>2013               </td><td>5                  </td><td>2                  </td><td>627                </td><td>630                </td><td> -3                </td><td>736                </td><td>805                </td><td>-29                </td><td>AA                 </td><td> 303               </td><td>N200AA             </td><td>LGA                </td><td>ORD                </td><td>112                </td><td> 733               </td><td>6                  </td><td>30                 </td><td>2013-05-02 06:00:00</td></tr>
</tbody>
</table>




```R
head(flights[flights$month == 5 & flights$day == 2 & flights$carrier == 'AA',]) # ribet
```


<table>
<thead><tr><th scope=col>year</th><th scope=col>month</th><th scope=col>day</th><th scope=col>dep_time</th><th scope=col>sched_dep_time</th><th scope=col>dep_delay</th><th scope=col>arr_time</th><th scope=col>sched_arr_time</th><th scope=col>arr_delay</th><th scope=col>carrier</th><th scope=col>flight</th><th scope=col>tailnum</th><th scope=col>origin</th><th scope=col>dest</th><th scope=col>air_time</th><th scope=col>distance</th><th scope=col>hour</th><th scope=col>minute</th><th scope=col>time_hour</th></tr></thead>
<tbody>
	<tr><td>2013               </td><td>5                  </td><td>2                  </td><td>539                </td><td>540                </td><td> -1                </td><td>850                </td><td>840                </td><td> 10                </td><td>AA                 </td><td> 701               </td><td>N5DYAA             </td><td>JFK                </td><td>MIA                </td><td>149                </td><td>1089               </td><td>5                  </td><td>40                 </td><td>2013-05-02 05:00:00</td></tr>
	<tr><td>2013               </td><td>5                  </td><td>2                  </td><td>549                </td><td>600                </td><td>-11                </td><td>823                </td><td>850                </td><td>-27                </td><td>AA                 </td><td> 707               </td><td>N3ANAA             </td><td>LGA                </td><td>DFW                </td><td>191                </td><td>1389               </td><td>6                  </td><td> 0                 </td><td>2013-05-02 06:00:00</td></tr>
	<tr><td>2013               </td><td>5                  </td><td>2                  </td><td>558                </td><td>605                </td><td> -7                </td><td>855                </td><td>910                </td><td>-15                </td><td>AA                 </td><td>1837               </td><td>N3FRAA             </td><td>LGA                </td><td>MIA                </td><td>149                </td><td>1096               </td><td>6                  </td><td> 5                 </td><td>2013-05-02 06:00:00</td></tr>
	<tr><td>2013               </td><td>5                  </td><td>2                  </td><td>603                </td><td>610                </td><td> -7                </td><td>729                </td><td>745                </td><td>-16                </td><td>AA                 </td><td> 301               </td><td>N4YJAA             </td><td>LGA                </td><td>ORD                </td><td>109                </td><td> 733               </td><td>6                  </td><td>10                 </td><td>2013-05-02 06:00:00</td></tr>
	<tr><td>2013               </td><td>5                  </td><td>2                  </td><td>611                </td><td>615                </td><td> -4                </td><td>900                </td><td>915                </td><td>-15                </td><td>AA                 </td><td>1895               </td><td>N3HEAA             </td><td>EWR                </td><td>MIA                </td><td>146                </td><td>1085               </td><td>6                  </td><td>15                 </td><td>2013-05-02 06:00:00</td></tr>
	<tr><td>2013               </td><td>5                  </td><td>2                  </td><td>627                </td><td>630                </td><td> -3                </td><td>736                </td><td>805                </td><td>-29                </td><td>AA                 </td><td> 303               </td><td>N200AA             </td><td>LGA                </td><td>ORD                </td><td>112                </td><td> 733               </td><td>6                  </td><td>30                 </td><td>2013-05-02 06:00:00</td></tr>
</tbody>
</table>



### `slice()`


```R
slice(flights, 1:10) # menyeleksi 10 baris pertama
```


<table>
<thead><tr><th scope=col>year</th><th scope=col>month</th><th scope=col>day</th><th scope=col>dep_time</th><th scope=col>sched_dep_time</th><th scope=col>dep_delay</th><th scope=col>arr_time</th><th scope=col>sched_arr_time</th><th scope=col>arr_delay</th><th scope=col>carrier</th><th scope=col>flight</th><th scope=col>tailnum</th><th scope=col>origin</th><th scope=col>dest</th><th scope=col>air_time</th><th scope=col>distance</th><th scope=col>hour</th><th scope=col>minute</th><th scope=col>time_hour</th></tr></thead>
<tbody>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>517                </td><td>515                </td><td> 2                 </td><td> 830               </td><td> 819               </td><td> 11                </td><td>UA                 </td><td>1545               </td><td>N14228             </td><td>EWR                </td><td>IAH                </td><td>227                </td><td>1400               </td><td>5                  </td><td>15                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>533                </td><td>529                </td><td> 4                 </td><td> 850               </td><td> 830               </td><td> 20                </td><td>UA                 </td><td>1714               </td><td>N24211             </td><td>LGA                </td><td>IAH                </td><td>227                </td><td>1416               </td><td>5                  </td><td>29                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>542                </td><td>540                </td><td> 2                 </td><td> 923               </td><td> 850               </td><td> 33                </td><td>AA                 </td><td>1141               </td><td>N619AA             </td><td>JFK                </td><td>MIA                </td><td>160                </td><td>1089               </td><td>5                  </td><td>40                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>544                </td><td>545                </td><td>-1                 </td><td>1004               </td><td>1022               </td><td>-18                </td><td>B6                 </td><td> 725               </td><td>N804JB             </td><td>JFK                </td><td>BQN                </td><td>183                </td><td>1576               </td><td>5                  </td><td>45                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>554                </td><td>600                </td><td>-6                 </td><td> 812               </td><td> 837               </td><td>-25                </td><td>DL                 </td><td> 461               </td><td>N668DN             </td><td>LGA                </td><td>ATL                </td><td>116                </td><td> 762               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>554                </td><td>558                </td><td>-4                 </td><td> 740               </td><td> 728               </td><td> 12                </td><td>UA                 </td><td>1696               </td><td>N39463             </td><td>EWR                </td><td>ORD                </td><td>150                </td><td> 719               </td><td>5                  </td><td>58                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>555                </td><td>600                </td><td>-5                 </td><td> 913               </td><td> 854               </td><td> 19                </td><td>B6                 </td><td> 507               </td><td>N516JB             </td><td>EWR                </td><td>FLL                </td><td>158                </td><td>1065               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>557                </td><td>600                </td><td>-3                 </td><td> 709               </td><td> 723               </td><td>-14                </td><td>EV                 </td><td>5708               </td><td>N829AS             </td><td>LGA                </td><td>IAD                </td><td> 53                </td><td> 229               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>557                </td><td>600                </td><td>-3                 </td><td> 838               </td><td> 846               </td><td> -8                </td><td>B6                 </td><td>  79               </td><td>N593JB             </td><td>JFK                </td><td>MCO                </td><td>140                </td><td> 944               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>558                </td><td>600                </td><td>-2                 </td><td> 753               </td><td> 745               </td><td>  8                </td><td>AA                 </td><td> 301               </td><td>N3ALAA             </td><td>LGA                </td><td>ORD                </td><td>138                </td><td> 733               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
</tbody>
</table>



### `arrange()`


```R
head(arrange(flights, year, month, day, arr_time))
# mengatur urutan sesuai kolomnya
```


<table>
<thead><tr><th scope=col>year</th><th scope=col>month</th><th scope=col>day</th><th scope=col>dep_time</th><th scope=col>sched_dep_time</th><th scope=col>dep_delay</th><th scope=col>arr_time</th><th scope=col>sched_arr_time</th><th scope=col>arr_delay</th><th scope=col>carrier</th><th scope=col>flight</th><th scope=col>tailnum</th><th scope=col>origin</th><th scope=col>dest</th><th scope=col>air_time</th><th scope=col>distance</th><th scope=col>hour</th><th scope=col>minute</th><th scope=col>time_hour</th></tr></thead>
<tbody>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>1929               </td><td>1920               </td><td>  9                </td><td> 3                 </td><td>   7               </td><td> -4                </td><td>UA                 </td><td>1071               </td><td>N27205             </td><td>EWR                </td><td>BQN                </td><td>192                </td><td>1585               </td><td>19                 </td><td>20                 </td><td>2013-01-01 19:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>2121               </td><td>2040               </td><td> 41                </td><td> 6                 </td><td>2323               </td><td> 43                </td><td>B6                 </td><td> 227               </td><td>N307JB             </td><td>EWR                </td><td>MCO                </td><td>143                </td><td> 937               </td><td>20                 </td><td>40                 </td><td>2013-01-01 20:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>2058               </td><td>2100               </td><td> -2                </td><td> 8                 </td><td>2359               </td><td>  9                </td><td>UA                 </td><td>1241               </td><td>N27724             </td><td>EWR                </td><td>TPA                </td><td>159                </td><td> 997               </td><td>21                 </td><td> 0                 </td><td>2013-01-01 21:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>2120               </td><td>2130               </td><td>-10                </td><td>16                 </td><td>  18               </td><td> -2                </td><td>B6                 </td><td> 383               </td><td>N603JB             </td><td>LGA                </td><td>FLL                </td><td>160                </td><td>1076               </td><td>21                 </td><td>30                 </td><td>2013-01-01 21:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>2134               </td><td>2045               </td><td> 49                </td><td>20                 </td><td>2352               </td><td> 28                </td><td>UA                 </td><td>1106               </td><td>N27733             </td><td>EWR                </td><td>FLL                </td><td>152                </td><td>1065               </td><td>20                 </td><td>45                 </td><td>2013-01-01 20:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>2312               </td><td>2000               </td><td>192                </td><td>21                 </td><td>2110               </td><td>191                </td><td>EV                 </td><td>4312               </td><td>N13958             </td><td>EWR                </td><td>DCA                </td><td> 44                </td><td> 199               </td><td>20                 </td><td> 0                 </td><td>2013-01-01 20:00:00</td></tr>
</tbody>
</table>



### `select()`


```R
head(select(flights, arr_time)) # seleksi kolom arr_time
```


<table>
<thead><tr><th scope=col>arr_time</th></tr></thead>
<tbody>
	<tr><td> 830</td></tr>
	<tr><td> 850</td></tr>
	<tr><td> 923</td></tr>
	<tr><td>1004</td></tr>
	<tr><td> 812</td></tr>
	<tr><td> 740</td></tr>
</tbody>
</table>




```R
head(select(flights,carrier)) # seleksi kolom carrier
```


<table>
<thead><tr><th scope=col>carrier</th></tr></thead>
<tbody>
	<tr><td>UA</td></tr>
	<tr><td>UA</td></tr>
	<tr><td>AA</td></tr>
	<tr><td>B6</td></tr>
	<tr><td>DL</td></tr>
	<tr><td>UA</td></tr>
</tbody>
</table>




```R
head(select(flights, arr_time, carrier, month)) # seleksi 3 kolom
```


<table>
<thead><tr><th scope=col>arr_time</th><th scope=col>carrier</th><th scope=col>month</th></tr></thead>
<tbody>
	<tr><td> 830</td><td>UA  </td><td>1   </td></tr>
	<tr><td> 850</td><td>UA  </td><td>1   </td></tr>
	<tr><td> 923</td><td>AA  </td><td>1   </td></tr>
	<tr><td>1004</td><td>B6  </td><td>1   </td></tr>
	<tr><td> 812</td><td>DL  </td><td>1   </td></tr>
	<tr><td> 740</td><td>UA  </td><td>1   </td></tr>
</tbody>
</table>



### `rename()`:


```R
head(flights)
```


<table>
<thead><tr><th scope=col>year</th><th scope=col>month</th><th scope=col>day</th><th scope=col>dep_time</th><th scope=col>sched_dep_time</th><th scope=col>dep_delay</th><th scope=col>arr_time</th><th scope=col>sched_arr_time</th><th scope=col>arr_delay</th><th scope=col>carrier</th><th scope=col>flight</th><th scope=col>tailnum</th><th scope=col>origin</th><th scope=col>dest</th><th scope=col>air_time</th><th scope=col>distance</th><th scope=col>hour</th><th scope=col>minute</th><th scope=col>time_hour</th></tr></thead>
<tbody>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>517                </td><td>515                </td><td> 2                 </td><td> 830               </td><td> 819               </td><td> 11                </td><td>UA                 </td><td>1545               </td><td>N14228             </td><td>EWR                </td><td>IAH                </td><td>227                </td><td>1400               </td><td>5                  </td><td>15                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>533                </td><td>529                </td><td> 4                 </td><td> 850               </td><td> 830               </td><td> 20                </td><td>UA                 </td><td>1714               </td><td>N24211             </td><td>LGA                </td><td>IAH                </td><td>227                </td><td>1416               </td><td>5                  </td><td>29                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>542                </td><td>540                </td><td> 2                 </td><td> 923               </td><td> 850               </td><td> 33                </td><td>AA                 </td><td>1141               </td><td>N619AA             </td><td>JFK                </td><td>MIA                </td><td>160                </td><td>1089               </td><td>5                  </td><td>40                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>544                </td><td>545                </td><td>-1                 </td><td>1004               </td><td>1022               </td><td>-18                </td><td>B6                 </td><td> 725               </td><td>N804JB             </td><td>JFK                </td><td>BQN                </td><td>183                </td><td>1576               </td><td>5                  </td><td>45                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>554                </td><td>600                </td><td>-6                 </td><td> 812               </td><td> 837               </td><td>-25                </td><td>DL                 </td><td> 461               </td><td>N668DN             </td><td>LGA                </td><td>ATL                </td><td>116                </td><td> 762               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>554                </td><td>558                </td><td>-4                 </td><td> 740               </td><td> 728               </td><td> 12                </td><td>UA                 </td><td>1696               </td><td>N39463             </td><td>EWR                </td><td>ORD                </td><td>150                </td><td> 719               </td><td>5                  </td><td>58                 </td><td>2013-01-01 05:00:00</td></tr>
</tbody>
</table>




```R
rename(flights,new_arr_time = arr_time) # mengubah nama kolom
```


<table>
<thead><tr><th scope=col>year</th><th scope=col>month</th><th scope=col>day</th><th scope=col>dep_time</th><th scope=col>sched_dep_time</th><th scope=col>dep_delay</th><th scope=col>new_arr_time</th><th scope=col>sched_arr_time</th><th scope=col>arr_delay</th><th scope=col>carrier</th><th scope=col>flight</th><th scope=col>tailnum</th><th scope=col>origin</th><th scope=col>dest</th><th scope=col>air_time</th><th scope=col>distance</th><th scope=col>hour</th><th scope=col>minute</th><th scope=col>time_hour</th></tr></thead>
<tbody>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>517                </td><td>515                </td><td> 2                 </td><td> 830               </td><td> 819               </td><td> 11                </td><td>UA                 </td><td>1545               </td><td>N14228             </td><td>EWR                </td><td>IAH                </td><td>227                </td><td>1400               </td><td>5                  </td><td>15                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>533                </td><td>529                </td><td> 4                 </td><td> 850               </td><td> 830               </td><td> 20                </td><td>UA                 </td><td>1714               </td><td>N24211             </td><td>LGA                </td><td>IAH                </td><td>227                </td><td>1416               </td><td>5                  </td><td>29                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>542                </td><td>540                </td><td> 2                 </td><td> 923               </td><td> 850               </td><td> 33                </td><td>AA                 </td><td>1141               </td><td>N619AA             </td><td>JFK                </td><td>MIA                </td><td>160                </td><td>1089               </td><td>5                  </td><td>40                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>544                </td><td>545                </td><td>-1                 </td><td>1004               </td><td>1022               </td><td>-18                </td><td>B6                 </td><td> 725               </td><td>N804JB             </td><td>JFK                </td><td>BQN                </td><td>183                </td><td>1576               </td><td>5                  </td><td>45                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>554                </td><td>600                </td><td>-6                 </td><td> 812               </td><td> 837               </td><td>-25                </td><td>DL                 </td><td> 461               </td><td>N668DN             </td><td>LGA                </td><td>ATL                </td><td>116                </td><td> 762               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>554                </td><td>558                </td><td>-4                 </td><td> 740               </td><td> 728               </td><td> 12                </td><td>UA                 </td><td>1696               </td><td>N39463             </td><td>EWR                </td><td>ORD                </td><td>150                </td><td> 719               </td><td>5                  </td><td>58                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>555                </td><td>600                </td><td>-5                 </td><td> 913               </td><td> 854               </td><td> 19                </td><td>B6                 </td><td> 507               </td><td>N516JB             </td><td>EWR                </td><td>FLL                </td><td>158                </td><td>1065               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>557                </td><td>600                </td><td>-3                 </td><td> 709               </td><td> 723               </td><td>-14                </td><td>EV                 </td><td>5708               </td><td>N829AS             </td><td>LGA                </td><td>IAD                </td><td> 53                </td><td> 229               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>557                </td><td>600                </td><td>-3                 </td><td> 838               </td><td> 846               </td><td> -8                </td><td>B6                 </td><td>  79               </td><td>N593JB             </td><td>JFK                </td><td>MCO                </td><td>140                </td><td> 944               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>558                </td><td>600                </td><td>-2                 </td><td> 753               </td><td> 745               </td><td>  8                </td><td>AA                 </td><td> 301               </td><td>N3ALAA             </td><td>LGA                </td><td>ORD                </td><td>138                </td><td> 733               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>558                </td><td>600                </td><td>-2                 </td><td> 849               </td><td> 851               </td><td> -2                </td><td>B6                 </td><td>  49               </td><td>N793JB             </td><td>JFK                </td><td>PBI                </td><td>149                </td><td>1028               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>558                </td><td>600                </td><td>-2                 </td><td> 853               </td><td> 856               </td><td> -3                </td><td>B6                 </td><td>  71               </td><td>N657JB             </td><td>JFK                </td><td>TPA                </td><td>158                </td><td>1005               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>558                </td><td>600                </td><td>-2                 </td><td> 924               </td><td> 917               </td><td>  7                </td><td>UA                 </td><td> 194               </td><td>N29129             </td><td>JFK                </td><td>LAX                </td><td>345                </td><td>2475               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>558                </td><td>600                </td><td>-2                 </td><td> 923               </td><td> 937               </td><td>-14                </td><td>UA                 </td><td>1124               </td><td>N53441             </td><td>EWR                </td><td>SFO                </td><td>361                </td><td>2565               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>559                </td><td>600                </td><td>-1                 </td><td> 941               </td><td> 910               </td><td> 31                </td><td>AA                 </td><td> 707               </td><td>N3DUAA             </td><td>LGA                </td><td>DFW                </td><td>257                </td><td>1389               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>559                </td><td>559                </td><td> 0                 </td><td> 702               </td><td> 706               </td><td> -4                </td><td>B6                 </td><td>1806               </td><td>N708JB             </td><td>JFK                </td><td>BOS                </td><td> 44                </td><td> 187               </td><td>5                  </td><td>59                 </td><td>2013-01-01 05:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>559                </td><td>600                </td><td>-1                 </td><td> 854               </td><td> 902               </td><td> -8                </td><td>UA                 </td><td>1187               </td><td>N76515             </td><td>EWR                </td><td>LAS                </td><td>337                </td><td>2227               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>600                </td><td>600                </td><td> 0                 </td><td> 851               </td><td> 858               </td><td> -7                </td><td>B6                 </td><td> 371               </td><td>N595JB             </td><td>LGA                </td><td>FLL                </td><td>152                </td><td>1076               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>600                </td><td>600                </td><td> 0                 </td><td> 837               </td><td> 825               </td><td> 12                </td><td>MQ                 </td><td>4650               </td><td>N542MQ             </td><td>LGA                </td><td>ATL                </td><td>134                </td><td> 762               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>601                </td><td>600                </td><td> 1                 </td><td> 844               </td><td> 850               </td><td> -6                </td><td>B6                 </td><td> 343               </td><td>N644JB             </td><td>EWR                </td><td>PBI                </td><td>147                </td><td>1023               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>602                </td><td>610                </td><td>-8                 </td><td> 812               </td><td> 820               </td><td> -8                </td><td>DL                 </td><td>1919               </td><td>N971DL             </td><td>LGA                </td><td>MSP                </td><td>170                </td><td>1020               </td><td>6                  </td><td>10                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>602                </td><td>605                </td><td>-3                 </td><td> 821               </td><td> 805               </td><td> 16                </td><td>MQ                 </td><td>4401               </td><td>N730MQ             </td><td>LGA                </td><td>DTW                </td><td>105                </td><td> 502               </td><td>6                  </td><td> 5                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>606                </td><td>610                </td><td>-4                 </td><td> 858               </td><td> 910               </td><td>-12                </td><td>AA                 </td><td>1895               </td><td>N633AA             </td><td>EWR                </td><td>MIA                </td><td>152                </td><td>1085               </td><td>6                  </td><td>10                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>606                </td><td>610                </td><td>-4                 </td><td> 837               </td><td> 845               </td><td> -8                </td><td>DL                 </td><td>1743               </td><td>N3739P             </td><td>JFK                </td><td>ATL                </td><td>128                </td><td> 760               </td><td>6                  </td><td>10                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>607                </td><td>607                </td><td> 0                 </td><td> 858               </td><td> 915               </td><td>-17                </td><td>UA                 </td><td>1077               </td><td>N53442             </td><td>EWR                </td><td>MIA                </td><td>157                </td><td>1085               </td><td>6                  </td><td> 7                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>608                </td><td>600                </td><td> 8                 </td><td> 807               </td><td> 735               </td><td> 32                </td><td>MQ                 </td><td>3768               </td><td>N9EAMQ             </td><td>EWR                </td><td>ORD                </td><td>139                </td><td> 719               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>611                </td><td>600                </td><td>11                 </td><td> 945               </td><td> 931               </td><td> 14                </td><td>UA                 </td><td> 303               </td><td>N532UA             </td><td>JFK                </td><td>SFO                </td><td>366                </td><td>2586               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>613                </td><td>610                </td><td> 3                 </td><td> 925               </td><td> 921               </td><td>  4                </td><td>B6                 </td><td> 135               </td><td>N635JB             </td><td>JFK                </td><td>RSW                </td><td>175                </td><td>1074               </td><td>6                  </td><td>10                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>615                </td><td>615                </td><td> 0                 </td><td>1039               </td><td>1100               </td><td>-21                </td><td>B6                 </td><td> 709               </td><td>N794JB             </td><td>JFK                </td><td>SJU                </td><td>182                </td><td>1598               </td><td>6                  </td><td>15                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>615                </td><td>615                </td><td> 0                 </td><td> 833               </td><td> 842               </td><td> -9                </td><td>DL                 </td><td> 575               </td><td>N326NB             </td><td>EWR                </td><td>ATL                </td><td>120                </td><td> 746               </td><td>6                  </td><td>15                 </td><td>2013-01-01 06:00:00</td></tr>
	<tr><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2123               </td><td>2125               </td><td> -2                </td><td>2223               </td><td>2247               </td><td>-24                </td><td>EV                 </td><td>5489               </td><td>N712EV             </td><td>LGA                </td><td>CHO                </td><td> 45                </td><td> 305               </td><td>21                 </td><td>25                 </td><td>2013-09-30 21:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2127               </td><td>2129               </td><td> -2                </td><td>2314               </td><td>2323               </td><td> -9                </td><td>EV                 </td><td>3833               </td><td>N16546             </td><td>EWR                </td><td>CLT                </td><td> 72                </td><td> 529               </td><td>21                 </td><td>29                 </td><td>2013-09-30 21:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2128               </td><td>2130               </td><td> -2                </td><td>2328               </td><td>2359               </td><td>-31                </td><td>B6                 </td><td>  97               </td><td>N807JB             </td><td>JFK                </td><td>DEN                </td><td>213                </td><td>1626               </td><td>21                 </td><td>30                 </td><td>2013-09-30 21:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2129               </td><td>2059               </td><td> 30                </td><td>2230               </td><td>2232               </td><td> -2                </td><td>EV                 </td><td>5048               </td><td>N751EV             </td><td>LGA                </td><td>RIC                </td><td> 45                </td><td> 292               </td><td>20                 </td><td>59                 </td><td>2013-09-30 20:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2131               </td><td>2140               </td><td> -9                </td><td>2225               </td><td>2255               </td><td>-30                </td><td>MQ                 </td><td>3621               </td><td>N807MQ             </td><td>JFK                </td><td>DCA                </td><td> 36                </td><td> 213               </td><td>21                 </td><td>40                 </td><td>2013-09-30 21:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2140               </td><td>2140               </td><td>  0                </td><td>  10               </td><td>  40               </td><td>-30                </td><td>AA                 </td><td> 185               </td><td>N335AA             </td><td>JFK                </td><td>LAX                </td><td>298                </td><td>2475               </td><td>21                 </td><td>40                 </td><td>2013-09-30 21:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2142               </td><td>2129               </td><td> 13                </td><td>2250               </td><td>2239               </td><td> 11                </td><td>EV                 </td><td>4509               </td><td>N12957             </td><td>EWR                </td><td>PWM                </td><td> 47                </td><td> 284               </td><td>21                 </td><td>29                 </td><td>2013-09-30 21:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2145               </td><td>2145               </td><td>  0                </td><td> 115               </td><td> 140               </td><td>-25                </td><td>B6                 </td><td>1103               </td><td>N633JB             </td><td>JFK                </td><td>SJU                </td><td>192                </td><td>1598               </td><td>21                 </td><td>45                 </td><td>2013-09-30 21:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2147               </td><td>2137               </td><td> 10                </td><td>  30               </td><td>  27               </td><td>  3                </td><td>B6                 </td><td>1371               </td><td>N627JB             </td><td>LGA                </td><td>FLL                </td><td>139                </td><td>1076               </td><td>21                 </td><td>37                 </td><td>2013-09-30 21:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2149               </td><td>2156               </td><td> -7                </td><td>2245               </td><td>2308               </td><td>-23                </td><td>UA                 </td><td> 523               </td><td>N813UA             </td><td>EWR                </td><td>BOS                </td><td> 37                </td><td> 200               </td><td>21                 </td><td>56                 </td><td>2013-09-30 21:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2150               </td><td>2159               </td><td> -9                </td><td>2250               </td><td>2306               </td><td>-16                </td><td>EV                 </td><td>3842               </td><td>N10575             </td><td>EWR                </td><td>MHT                </td><td> 39                </td><td> 209               </td><td>21                 </td><td>59                 </td><td>2013-09-30 21:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2159               </td><td>1845               </td><td>194                </td><td>2344               </td><td>2030               </td><td>194                </td><td>9E                 </td><td>3320               </td><td>N906XJ             </td><td>JFK                </td><td>BUF                </td><td> 50                </td><td> 301               </td><td>18                 </td><td>45                 </td><td>2013-09-30 18:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2203               </td><td>2205               </td><td> -2                </td><td>2339               </td><td>2331               </td><td>  8                </td><td>EV                 </td><td>5311               </td><td>N722EV             </td><td>LGA                </td><td>BGR                </td><td> 61                </td><td> 378               </td><td>22                 </td><td> 5                 </td><td>2013-09-30 22:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2207               </td><td>2140               </td><td> 27                </td><td>2257               </td><td>2250               </td><td>  7                </td><td>MQ                 </td><td>3660               </td><td>N532MQ             </td><td>LGA                </td><td>BNA                </td><td> 97                </td><td> 764               </td><td>21                 </td><td>40                 </td><td>2013-09-30 21:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2211               </td><td>2059               </td><td> 72                </td><td>2339               </td><td>2242               </td><td> 57                </td><td>EV                 </td><td>4672               </td><td>N12145             </td><td>EWR                </td><td>STL                </td><td>120                </td><td> 872               </td><td>20                 </td><td>59                 </td><td>2013-09-30 20:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2231               </td><td>2245               </td><td>-14                </td><td>2335               </td><td>2356               </td><td>-21                </td><td>B6                 </td><td> 108               </td><td>N193JB             </td><td>JFK                </td><td>PWM                </td><td> 48                </td><td> 273               </td><td>22                 </td><td>45                 </td><td>2013-09-30 22:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2233               </td><td>2113               </td><td> 80                </td><td> 112               </td><td>  30               </td><td> 42                </td><td>UA                 </td><td> 471               </td><td>N578UA             </td><td>EWR                </td><td>SFO                </td><td>318                </td><td>2565               </td><td>21                 </td><td>13                 </td><td>2013-09-30 21:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2235               </td><td>2001               </td><td>154                </td><td>  59               </td><td>2249               </td><td>130                </td><td>B6                 </td><td>1083               </td><td>N804JB             </td><td>JFK                </td><td>MCO                </td><td>123                </td><td> 944               </td><td>20                 </td><td> 1                 </td><td>2013-09-30 20:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2237               </td><td>2245               </td><td> -8                </td><td>2345               </td><td>2353               </td><td> -8                </td><td>B6                 </td><td> 234               </td><td>N318JB             </td><td>JFK                </td><td>BTV                </td><td> 43                </td><td> 266               </td><td>22                 </td><td>45                 </td><td>2013-09-30 22:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2240               </td><td>2245               </td><td> -5                </td><td>2334               </td><td>2351               </td><td>-17                </td><td>B6                 </td><td>1816               </td><td>N354JB             </td><td>JFK                </td><td>SYR                </td><td> 41                </td><td> 209               </td><td>22                 </td><td>45                 </td><td>2013-09-30 22:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2240               </td><td>2250               </td><td>-10                </td><td>2347               </td><td>   7               </td><td>-20                </td><td>B6                 </td><td>2002               </td><td>N281JB             </td><td>JFK                </td><td>BUF                </td><td> 52                </td><td> 301               </td><td>22                 </td><td>50                 </td><td>2013-09-30 22:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2241               </td><td>2246               </td><td> -5                </td><td>2345               </td><td>   1               </td><td>-16                </td><td>B6                 </td><td> 486               </td><td>N346JB             </td><td>JFK                </td><td>ROC                </td><td> 47                </td><td> 264               </td><td>22                 </td><td>46                 </td><td>2013-09-30 22:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2307               </td><td>2255               </td><td> 12                </td><td>2359               </td><td>2358               </td><td>  1                </td><td>B6                 </td><td> 718               </td><td>N565JB             </td><td>JFK                </td><td>BOS                </td><td> 33                </td><td> 187               </td><td>22                 </td><td>55                 </td><td>2013-09-30 22:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2349               </td><td>2359               </td><td>-10                </td><td> 325               </td><td> 350               </td><td>-25                </td><td>B6                 </td><td> 745               </td><td>N516JB             </td><td>JFK                </td><td>PSE                </td><td>196                </td><td>1617               </td><td>23                 </td><td>59                 </td><td>2013-09-30 23:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>  NA               </td><td>1842               </td><td> NA                </td><td>  NA               </td><td>2019               </td><td> NA                </td><td>EV                 </td><td>5274               </td><td>N740EV             </td><td>LGA                </td><td>BNA                </td><td> NA                </td><td> 764               </td><td>18                 </td><td>42                 </td><td>2013-09-30 18:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>  NA               </td><td>1455               </td><td> NA                </td><td>  NA               </td><td>1634               </td><td> NA                </td><td>9E                 </td><td>3393               </td><td>NA                 </td><td>JFK                </td><td>DCA                </td><td> NA                </td><td> 213               </td><td>14                 </td><td>55                 </td><td>2013-09-30 14:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>  NA               </td><td>2200               </td><td> NA                </td><td>  NA               </td><td>2312               </td><td> NA                </td><td>9E                 </td><td>3525               </td><td>NA                 </td><td>LGA                </td><td>SYR                </td><td> NA                </td><td> 198               </td><td>22                 </td><td> 0                 </td><td>2013-09-30 22:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>  NA               </td><td>1210               </td><td> NA                </td><td>  NA               </td><td>1330               </td><td> NA                </td><td>MQ                 </td><td>3461               </td><td>N535MQ             </td><td>LGA                </td><td>BNA                </td><td> NA                </td><td> 764               </td><td>12                 </td><td>10                 </td><td>2013-09-30 12:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>  NA               </td><td>1159               </td><td> NA                </td><td>  NA               </td><td>1344               </td><td> NA                </td><td>MQ                 </td><td>3572               </td><td>N511MQ             </td><td>LGA                </td><td>CLE                </td><td> NA                </td><td> 419               </td><td>11                 </td><td>59                 </td><td>2013-09-30 11:00:00</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>  NA               </td><td> 840               </td><td> NA                </td><td>  NA               </td><td>1020               </td><td> NA                </td><td>MQ                 </td><td>3531               </td><td>N839MQ             </td><td>LGA                </td><td>RDU                </td><td> NA                </td><td> 431               </td><td> 8                 </td><td>40                 </td><td>2013-09-30 08:00:00</td></tr>
</tbody>
</table>



### `distinct()`

Untuk menyeleksi nilai - nilai unik


```R
distinct(select(flights, carrier)) # nilai - nilai unik pada kolom carrier
```


<table>
<thead><tr><th scope=col>carrier</th></tr></thead>
<tbody>
	<tr><td>UA</td></tr>
	<tr><td>AA</td></tr>
	<tr><td>B6</td></tr>
	<tr><td>DL</td></tr>
	<tr><td>EV</td></tr>
	<tr><td>MQ</td></tr>
	<tr><td>US</td></tr>
	<tr><td>WN</td></tr>
	<tr><td>VX</td></tr>
	<tr><td>FL</td></tr>
	<tr><td>AS</td></tr>
	<tr><td>9E</td></tr>
	<tr><td>F9</td></tr>
	<tr><td>HA</td></tr>
	<tr><td>YV</td></tr>
	<tr><td>OO</td></tr>
</tbody>
</table>




```R
distinct(select(flights,month))
```


<table>
<thead><tr><th scope=col>month</th></tr></thead>
<tbody>
	<tr><td> 1</td></tr>
	<tr><td>10</td></tr>
	<tr><td>11</td></tr>
	<tr><td>12</td></tr>
	<tr><td> 2</td></tr>
	<tr><td> 3</td></tr>
	<tr><td> 4</td></tr>
	<tr><td> 5</td></tr>
	<tr><td> 6</td></tr>
	<tr><td> 7</td></tr>
	<tr><td> 8</td></tr>
	<tr><td> 9</td></tr>
</tbody>
</table>



### `mutate()`

Menambahkan kolom baru di data frame


```R
mutate(flights, kol_baru = arr_delay - dep_delay)
```


<table>
<thead><tr><th scope=col>year</th><th scope=col>month</th><th scope=col>day</th><th scope=col>dep_time</th><th scope=col>sched_dep_time</th><th scope=col>dep_delay</th><th scope=col>arr_time</th><th scope=col>sched_arr_time</th><th scope=col>arr_delay</th><th scope=col>carrier</th><th scope=col>flight</th><th scope=col>tailnum</th><th scope=col>origin</th><th scope=col>dest</th><th scope=col>air_time</th><th scope=col>distance</th><th scope=col>hour</th><th scope=col>minute</th><th scope=col>time_hour</th><th scope=col>kol_baru</th></tr></thead>
<tbody>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>517                </td><td>515                </td><td> 2                 </td><td> 830               </td><td> 819               </td><td> 11                </td><td>UA                 </td><td>1545               </td><td>N14228             </td><td>EWR                </td><td>IAH                </td><td>227                </td><td>1400               </td><td>5                  </td><td>15                 </td><td>2013-01-01 05:00:00</td><td>  9                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>533                </td><td>529                </td><td> 4                 </td><td> 850               </td><td> 830               </td><td> 20                </td><td>UA                 </td><td>1714               </td><td>N24211             </td><td>LGA                </td><td>IAH                </td><td>227                </td><td>1416               </td><td>5                  </td><td>29                 </td><td>2013-01-01 05:00:00</td><td> 16                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>542                </td><td>540                </td><td> 2                 </td><td> 923               </td><td> 850               </td><td> 33                </td><td>AA                 </td><td>1141               </td><td>N619AA             </td><td>JFK                </td><td>MIA                </td><td>160                </td><td>1089               </td><td>5                  </td><td>40                 </td><td>2013-01-01 05:00:00</td><td> 31                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>544                </td><td>545                </td><td>-1                 </td><td>1004               </td><td>1022               </td><td>-18                </td><td>B6                 </td><td> 725               </td><td>N804JB             </td><td>JFK                </td><td>BQN                </td><td>183                </td><td>1576               </td><td>5                  </td><td>45                 </td><td>2013-01-01 05:00:00</td><td>-17                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>554                </td><td>600                </td><td>-6                 </td><td> 812               </td><td> 837               </td><td>-25                </td><td>DL                 </td><td> 461               </td><td>N668DN             </td><td>LGA                </td><td>ATL                </td><td>116                </td><td> 762               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td>-19                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>554                </td><td>558                </td><td>-4                 </td><td> 740               </td><td> 728               </td><td> 12                </td><td>UA                 </td><td>1696               </td><td>N39463             </td><td>EWR                </td><td>ORD                </td><td>150                </td><td> 719               </td><td>5                  </td><td>58                 </td><td>2013-01-01 05:00:00</td><td> 16                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>555                </td><td>600                </td><td>-5                 </td><td> 913               </td><td> 854               </td><td> 19                </td><td>B6                 </td><td> 507               </td><td>N516JB             </td><td>EWR                </td><td>FLL                </td><td>158                </td><td>1065               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td> 24                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>557                </td><td>600                </td><td>-3                 </td><td> 709               </td><td> 723               </td><td>-14                </td><td>EV                 </td><td>5708               </td><td>N829AS             </td><td>LGA                </td><td>IAD                </td><td> 53                </td><td> 229               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td>-11                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>557                </td><td>600                </td><td>-3                 </td><td> 838               </td><td> 846               </td><td> -8                </td><td>B6                 </td><td>  79               </td><td>N593JB             </td><td>JFK                </td><td>MCO                </td><td>140                </td><td> 944               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td> -5                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>558                </td><td>600                </td><td>-2                 </td><td> 753               </td><td> 745               </td><td>  8                </td><td>AA                 </td><td> 301               </td><td>N3ALAA             </td><td>LGA                </td><td>ORD                </td><td>138                </td><td> 733               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td> 10                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>558                </td><td>600                </td><td>-2                 </td><td> 849               </td><td> 851               </td><td> -2                </td><td>B6                 </td><td>  49               </td><td>N793JB             </td><td>JFK                </td><td>PBI                </td><td>149                </td><td>1028               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td>  0                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>558                </td><td>600                </td><td>-2                 </td><td> 853               </td><td> 856               </td><td> -3                </td><td>B6                 </td><td>  71               </td><td>N657JB             </td><td>JFK                </td><td>TPA                </td><td>158                </td><td>1005               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td> -1                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>558                </td><td>600                </td><td>-2                 </td><td> 924               </td><td> 917               </td><td>  7                </td><td>UA                 </td><td> 194               </td><td>N29129             </td><td>JFK                </td><td>LAX                </td><td>345                </td><td>2475               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td>  9                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>558                </td><td>600                </td><td>-2                 </td><td> 923               </td><td> 937               </td><td>-14                </td><td>UA                 </td><td>1124               </td><td>N53441             </td><td>EWR                </td><td>SFO                </td><td>361                </td><td>2565               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td>-12                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>559                </td><td>600                </td><td>-1                 </td><td> 941               </td><td> 910               </td><td> 31                </td><td>AA                 </td><td> 707               </td><td>N3DUAA             </td><td>LGA                </td><td>DFW                </td><td>257                </td><td>1389               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td> 32                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>559                </td><td>559                </td><td> 0                 </td><td> 702               </td><td> 706               </td><td> -4                </td><td>B6                 </td><td>1806               </td><td>N708JB             </td><td>JFK                </td><td>BOS                </td><td> 44                </td><td> 187               </td><td>5                  </td><td>59                 </td><td>2013-01-01 05:00:00</td><td> -4                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>559                </td><td>600                </td><td>-1                 </td><td> 854               </td><td> 902               </td><td> -8                </td><td>UA                 </td><td>1187               </td><td>N76515             </td><td>EWR                </td><td>LAS                </td><td>337                </td><td>2227               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td> -7                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>600                </td><td>600                </td><td> 0                 </td><td> 851               </td><td> 858               </td><td> -7                </td><td>B6                 </td><td> 371               </td><td>N595JB             </td><td>LGA                </td><td>FLL                </td><td>152                </td><td>1076               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td> -7                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>600                </td><td>600                </td><td> 0                 </td><td> 837               </td><td> 825               </td><td> 12                </td><td>MQ                 </td><td>4650               </td><td>N542MQ             </td><td>LGA                </td><td>ATL                </td><td>134                </td><td> 762               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td> 12                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>601                </td><td>600                </td><td> 1                 </td><td> 844               </td><td> 850               </td><td> -6                </td><td>B6                 </td><td> 343               </td><td>N644JB             </td><td>EWR                </td><td>PBI                </td><td>147                </td><td>1023               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td> -7                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>602                </td><td>610                </td><td>-8                 </td><td> 812               </td><td> 820               </td><td> -8                </td><td>DL                 </td><td>1919               </td><td>N971DL             </td><td>LGA                </td><td>MSP                </td><td>170                </td><td>1020               </td><td>6                  </td><td>10                 </td><td>2013-01-01 06:00:00</td><td>  0                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>602                </td><td>605                </td><td>-3                 </td><td> 821               </td><td> 805               </td><td> 16                </td><td>MQ                 </td><td>4401               </td><td>N730MQ             </td><td>LGA                </td><td>DTW                </td><td>105                </td><td> 502               </td><td>6                  </td><td> 5                 </td><td>2013-01-01 06:00:00</td><td> 19                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>606                </td><td>610                </td><td>-4                 </td><td> 858               </td><td> 910               </td><td>-12                </td><td>AA                 </td><td>1895               </td><td>N633AA             </td><td>EWR                </td><td>MIA                </td><td>152                </td><td>1085               </td><td>6                  </td><td>10                 </td><td>2013-01-01 06:00:00</td><td> -8                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>606                </td><td>610                </td><td>-4                 </td><td> 837               </td><td> 845               </td><td> -8                </td><td>DL                 </td><td>1743               </td><td>N3739P             </td><td>JFK                </td><td>ATL                </td><td>128                </td><td> 760               </td><td>6                  </td><td>10                 </td><td>2013-01-01 06:00:00</td><td> -4                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>607                </td><td>607                </td><td> 0                 </td><td> 858               </td><td> 915               </td><td>-17                </td><td>UA                 </td><td>1077               </td><td>N53442             </td><td>EWR                </td><td>MIA                </td><td>157                </td><td>1085               </td><td>6                  </td><td> 7                 </td><td>2013-01-01 06:00:00</td><td>-17                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>608                </td><td>600                </td><td> 8                 </td><td> 807               </td><td> 735               </td><td> 32                </td><td>MQ                 </td><td>3768               </td><td>N9EAMQ             </td><td>EWR                </td><td>ORD                </td><td>139                </td><td> 719               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td> 24                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>611                </td><td>600                </td><td>11                 </td><td> 945               </td><td> 931               </td><td> 14                </td><td>UA                 </td><td> 303               </td><td>N532UA             </td><td>JFK                </td><td>SFO                </td><td>366                </td><td>2586               </td><td>6                  </td><td> 0                 </td><td>2013-01-01 06:00:00</td><td>  3                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>613                </td><td>610                </td><td> 3                 </td><td> 925               </td><td> 921               </td><td>  4                </td><td>B6                 </td><td> 135               </td><td>N635JB             </td><td>JFK                </td><td>RSW                </td><td>175                </td><td>1074               </td><td>6                  </td><td>10                 </td><td>2013-01-01 06:00:00</td><td>  1                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>615                </td><td>615                </td><td> 0                 </td><td>1039               </td><td>1100               </td><td>-21                </td><td>B6                 </td><td> 709               </td><td>N794JB             </td><td>JFK                </td><td>SJU                </td><td>182                </td><td>1598               </td><td>6                  </td><td>15                 </td><td>2013-01-01 06:00:00</td><td>-21                </td></tr>
	<tr><td>2013               </td><td>1                  </td><td>1                  </td><td>615                </td><td>615                </td><td> 0                 </td><td> 833               </td><td> 842               </td><td> -9                </td><td>DL                 </td><td> 575               </td><td>N326NB             </td><td>EWR                </td><td>ATL                </td><td>120                </td><td> 746               </td><td>6                  </td><td>15                 </td><td>2013-01-01 06:00:00</td><td> -9                </td></tr>
	<tr><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2123               </td><td>2125               </td><td> -2                </td><td>2223               </td><td>2247               </td><td>-24                </td><td>EV                 </td><td>5489               </td><td>N712EV             </td><td>LGA                </td><td>CHO                </td><td> 45                </td><td> 305               </td><td>21                 </td><td>25                 </td><td>2013-09-30 21:00:00</td><td>-22                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2127               </td><td>2129               </td><td> -2                </td><td>2314               </td><td>2323               </td><td> -9                </td><td>EV                 </td><td>3833               </td><td>N16546             </td><td>EWR                </td><td>CLT                </td><td> 72                </td><td> 529               </td><td>21                 </td><td>29                 </td><td>2013-09-30 21:00:00</td><td> -7                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2128               </td><td>2130               </td><td> -2                </td><td>2328               </td><td>2359               </td><td>-31                </td><td>B6                 </td><td>  97               </td><td>N807JB             </td><td>JFK                </td><td>DEN                </td><td>213                </td><td>1626               </td><td>21                 </td><td>30                 </td><td>2013-09-30 21:00:00</td><td>-29                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2129               </td><td>2059               </td><td> 30                </td><td>2230               </td><td>2232               </td><td> -2                </td><td>EV                 </td><td>5048               </td><td>N751EV             </td><td>LGA                </td><td>RIC                </td><td> 45                </td><td> 292               </td><td>20                 </td><td>59                 </td><td>2013-09-30 20:00:00</td><td>-32                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2131               </td><td>2140               </td><td> -9                </td><td>2225               </td><td>2255               </td><td>-30                </td><td>MQ                 </td><td>3621               </td><td>N807MQ             </td><td>JFK                </td><td>DCA                </td><td> 36                </td><td> 213               </td><td>21                 </td><td>40                 </td><td>2013-09-30 21:00:00</td><td>-21                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2140               </td><td>2140               </td><td>  0                </td><td>  10               </td><td>  40               </td><td>-30                </td><td>AA                 </td><td> 185               </td><td>N335AA             </td><td>JFK                </td><td>LAX                </td><td>298                </td><td>2475               </td><td>21                 </td><td>40                 </td><td>2013-09-30 21:00:00</td><td>-30                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2142               </td><td>2129               </td><td> 13                </td><td>2250               </td><td>2239               </td><td> 11                </td><td>EV                 </td><td>4509               </td><td>N12957             </td><td>EWR                </td><td>PWM                </td><td> 47                </td><td> 284               </td><td>21                 </td><td>29                 </td><td>2013-09-30 21:00:00</td><td> -2                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2145               </td><td>2145               </td><td>  0                </td><td> 115               </td><td> 140               </td><td>-25                </td><td>B6                 </td><td>1103               </td><td>N633JB             </td><td>JFK                </td><td>SJU                </td><td>192                </td><td>1598               </td><td>21                 </td><td>45                 </td><td>2013-09-30 21:00:00</td><td>-25                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2147               </td><td>2137               </td><td> 10                </td><td>  30               </td><td>  27               </td><td>  3                </td><td>B6                 </td><td>1371               </td><td>N627JB             </td><td>LGA                </td><td>FLL                </td><td>139                </td><td>1076               </td><td>21                 </td><td>37                 </td><td>2013-09-30 21:00:00</td><td> -7                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2149               </td><td>2156               </td><td> -7                </td><td>2245               </td><td>2308               </td><td>-23                </td><td>UA                 </td><td> 523               </td><td>N813UA             </td><td>EWR                </td><td>BOS                </td><td> 37                </td><td> 200               </td><td>21                 </td><td>56                 </td><td>2013-09-30 21:00:00</td><td>-16                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2150               </td><td>2159               </td><td> -9                </td><td>2250               </td><td>2306               </td><td>-16                </td><td>EV                 </td><td>3842               </td><td>N10575             </td><td>EWR                </td><td>MHT                </td><td> 39                </td><td> 209               </td><td>21                 </td><td>59                 </td><td>2013-09-30 21:00:00</td><td> -7                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2159               </td><td>1845               </td><td>194                </td><td>2344               </td><td>2030               </td><td>194                </td><td>9E                 </td><td>3320               </td><td>N906XJ             </td><td>JFK                </td><td>BUF                </td><td> 50                </td><td> 301               </td><td>18                 </td><td>45                 </td><td>2013-09-30 18:00:00</td><td>  0                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2203               </td><td>2205               </td><td> -2                </td><td>2339               </td><td>2331               </td><td>  8                </td><td>EV                 </td><td>5311               </td><td>N722EV             </td><td>LGA                </td><td>BGR                </td><td> 61                </td><td> 378               </td><td>22                 </td><td> 5                 </td><td>2013-09-30 22:00:00</td><td> 10                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2207               </td><td>2140               </td><td> 27                </td><td>2257               </td><td>2250               </td><td>  7                </td><td>MQ                 </td><td>3660               </td><td>N532MQ             </td><td>LGA                </td><td>BNA                </td><td> 97                </td><td> 764               </td><td>21                 </td><td>40                 </td><td>2013-09-30 21:00:00</td><td>-20                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2211               </td><td>2059               </td><td> 72                </td><td>2339               </td><td>2242               </td><td> 57                </td><td>EV                 </td><td>4672               </td><td>N12145             </td><td>EWR                </td><td>STL                </td><td>120                </td><td> 872               </td><td>20                 </td><td>59                 </td><td>2013-09-30 20:00:00</td><td>-15                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2231               </td><td>2245               </td><td>-14                </td><td>2335               </td><td>2356               </td><td>-21                </td><td>B6                 </td><td> 108               </td><td>N193JB             </td><td>JFK                </td><td>PWM                </td><td> 48                </td><td> 273               </td><td>22                 </td><td>45                 </td><td>2013-09-30 22:00:00</td><td> -7                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2233               </td><td>2113               </td><td> 80                </td><td> 112               </td><td>  30               </td><td> 42                </td><td>UA                 </td><td> 471               </td><td>N578UA             </td><td>EWR                </td><td>SFO                </td><td>318                </td><td>2565               </td><td>21                 </td><td>13                 </td><td>2013-09-30 21:00:00</td><td>-38                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2235               </td><td>2001               </td><td>154                </td><td>  59               </td><td>2249               </td><td>130                </td><td>B6                 </td><td>1083               </td><td>N804JB             </td><td>JFK                </td><td>MCO                </td><td>123                </td><td> 944               </td><td>20                 </td><td> 1                 </td><td>2013-09-30 20:00:00</td><td>-24                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2237               </td><td>2245               </td><td> -8                </td><td>2345               </td><td>2353               </td><td> -8                </td><td>B6                 </td><td> 234               </td><td>N318JB             </td><td>JFK                </td><td>BTV                </td><td> 43                </td><td> 266               </td><td>22                 </td><td>45                 </td><td>2013-09-30 22:00:00</td><td>  0                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2240               </td><td>2245               </td><td> -5                </td><td>2334               </td><td>2351               </td><td>-17                </td><td>B6                 </td><td>1816               </td><td>N354JB             </td><td>JFK                </td><td>SYR                </td><td> 41                </td><td> 209               </td><td>22                 </td><td>45                 </td><td>2013-09-30 22:00:00</td><td>-12                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2240               </td><td>2250               </td><td>-10                </td><td>2347               </td><td>   7               </td><td>-20                </td><td>B6                 </td><td>2002               </td><td>N281JB             </td><td>JFK                </td><td>BUF                </td><td> 52                </td><td> 301               </td><td>22                 </td><td>50                 </td><td>2013-09-30 22:00:00</td><td>-10                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2241               </td><td>2246               </td><td> -5                </td><td>2345               </td><td>   1               </td><td>-16                </td><td>B6                 </td><td> 486               </td><td>N346JB             </td><td>JFK                </td><td>ROC                </td><td> 47                </td><td> 264               </td><td>22                 </td><td>46                 </td><td>2013-09-30 22:00:00</td><td>-11                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2307               </td><td>2255               </td><td> 12                </td><td>2359               </td><td>2358               </td><td>  1                </td><td>B6                 </td><td> 718               </td><td>N565JB             </td><td>JFK                </td><td>BOS                </td><td> 33                </td><td> 187               </td><td>22                 </td><td>55                 </td><td>2013-09-30 22:00:00</td><td>-11                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>2349               </td><td>2359               </td><td>-10                </td><td> 325               </td><td> 350               </td><td>-25                </td><td>B6                 </td><td> 745               </td><td>N516JB             </td><td>JFK                </td><td>PSE                </td><td>196                </td><td>1617               </td><td>23                 </td><td>59                 </td><td>2013-09-30 23:00:00</td><td>-15                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>  NA               </td><td>1842               </td><td> NA                </td><td>  NA               </td><td>2019               </td><td> NA                </td><td>EV                 </td><td>5274               </td><td>N740EV             </td><td>LGA                </td><td>BNA                </td><td> NA                </td><td> 764               </td><td>18                 </td><td>42                 </td><td>2013-09-30 18:00:00</td><td> NA                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>  NA               </td><td>1455               </td><td> NA                </td><td>  NA               </td><td>1634               </td><td> NA                </td><td>9E                 </td><td>3393               </td><td>NA                 </td><td>JFK                </td><td>DCA                </td><td> NA                </td><td> 213               </td><td>14                 </td><td>55                 </td><td>2013-09-30 14:00:00</td><td> NA                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>  NA               </td><td>2200               </td><td> NA                </td><td>  NA               </td><td>2312               </td><td> NA                </td><td>9E                 </td><td>3525               </td><td>NA                 </td><td>LGA                </td><td>SYR                </td><td> NA                </td><td> 198               </td><td>22                 </td><td> 0                 </td><td>2013-09-30 22:00:00</td><td> NA                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>  NA               </td><td>1210               </td><td> NA                </td><td>  NA               </td><td>1330               </td><td> NA                </td><td>MQ                 </td><td>3461               </td><td>N535MQ             </td><td>LGA                </td><td>BNA                </td><td> NA                </td><td> 764               </td><td>12                 </td><td>10                 </td><td>2013-09-30 12:00:00</td><td> NA                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>  NA               </td><td>1159               </td><td> NA                </td><td>  NA               </td><td>1344               </td><td> NA                </td><td>MQ                 </td><td>3572               </td><td>N511MQ             </td><td>LGA                </td><td>CLE                </td><td> NA                </td><td> 419               </td><td>11                 </td><td>59                 </td><td>2013-09-30 11:00:00</td><td> NA                </td></tr>
	<tr><td>2013               </td><td>9                  </td><td>30                 </td><td>  NA               </td><td> 840               </td><td> NA                </td><td>  NA               </td><td>1020               </td><td> NA                </td><td>MQ                 </td><td>3531               </td><td>N839MQ             </td><td>LGA                </td><td>RDU                </td><td> NA                </td><td> 431               </td><td> 8                 </td><td>40                 </td><td>2013-09-30 08:00:00</td><td> NA                </td></tr>
</tbody>
</table>



### `transmute()`

Sama seperti `mutate()`, namu hanya mengeluarkan *output* kolom baru yang dihasilkan.


```R
transmute(flights, kol_baru = arr_delay - dep_delay)
```


<table>
<thead><tr><th scope=col>kol_baru</th></tr></thead>
<tbody>
	<tr><td>  9</td></tr>
	<tr><td> 16</td></tr>
	<tr><td> 31</td></tr>
	<tr><td>-17</td></tr>
	<tr><td>-19</td></tr>
	<tr><td> 16</td></tr>
	<tr><td> 24</td></tr>
	<tr><td>-11</td></tr>
	<tr><td> -5</td></tr>
	<tr><td> 10</td></tr>
	<tr><td>  0</td></tr>
	<tr><td> -1</td></tr>
	<tr><td>  9</td></tr>
	<tr><td>-12</td></tr>
	<tr><td> 32</td></tr>
	<tr><td> -4</td></tr>
	<tr><td> -7</td></tr>
	<tr><td> -7</td></tr>
	<tr><td> 12</td></tr>
	<tr><td> -7</td></tr>
	<tr><td>  0</td></tr>
	<tr><td> 19</td></tr>
	<tr><td> -8</td></tr>
	<tr><td> -4</td></tr>
	<tr><td>-17</td></tr>
	<tr><td> 24</td></tr>
	<tr><td>  3</td></tr>
	<tr><td>  1</td></tr>
	<tr><td>-21</td></tr>
	<tr><td> -9</td></tr>
	<tr><td>...</td></tr>
	<tr><td>-22</td></tr>
	<tr><td> -7</td></tr>
	<tr><td>-29</td></tr>
	<tr><td>-32</td></tr>
	<tr><td>-21</td></tr>
	<tr><td>-30</td></tr>
	<tr><td> -2</td></tr>
	<tr><td>-25</td></tr>
	<tr><td> -7</td></tr>
	<tr><td>-16</td></tr>
	<tr><td> -7</td></tr>
	<tr><td>  0</td></tr>
	<tr><td> 10</td></tr>
	<tr><td>-20</td></tr>
	<tr><td>-15</td></tr>
	<tr><td> -7</td></tr>
	<tr><td>-38</td></tr>
	<tr><td>-24</td></tr>
	<tr><td>  0</td></tr>
	<tr><td>-12</td></tr>
	<tr><td>-10</td></tr>
	<tr><td>-11</td></tr>
	<tr><td>-11</td></tr>
	<tr><td>-15</td></tr>
	<tr><td> NA</td></tr>
	<tr><td> NA</td></tr>
	<tr><td> NA</td></tr>
	<tr><td> NA</td></tr>
	<tr><td> NA</td></tr>
	<tr><td> NA</td></tr>
</tbody>
</table>



### `summarise()`


```R
summarise(flights, rata2wktTerbang = mean(air_time, na.rm = T)) 
# sama seperti fungsi agregate di R
```


<table>
<thead><tr><th scope=col>rata2wktTerbang</th></tr></thead>
<tbody>
	<tr><td>150.6865</td></tr>
</tbody>
</table>




```R
summarise(flights, JmlhwktTerbang = sum(air_time, na.rm = T)) 
```


<table>
<thead><tr><th scope=col>JmlhwktTerbang</th></tr></thead>
<tbody>
	<tr><td>49326610</td></tr>
</tbody>
</table>



### `sample_n()` dan `sample_frac()`


```R
sample_n(flights, 3) # mensampel 3 baris acak
```


<table>
<thead><tr><th scope=col>year</th><th scope=col>month</th><th scope=col>day</th><th scope=col>dep_time</th><th scope=col>sched_dep_time</th><th scope=col>dep_delay</th><th scope=col>arr_time</th><th scope=col>sched_arr_time</th><th scope=col>arr_delay</th><th scope=col>carrier</th><th scope=col>flight</th><th scope=col>tailnum</th><th scope=col>origin</th><th scope=col>dest</th><th scope=col>air_time</th><th scope=col>distance</th><th scope=col>hour</th><th scope=col>minute</th><th scope=col>time_hour</th></tr></thead>
<tbody>
	<tr><td>2013               </td><td> 8                 </td><td>22                 </td><td> 552               </td><td> 600               </td><td>-8                 </td><td> 647               </td><td> 700               </td><td>-13                </td><td>US                 </td><td>2134               </td><td>N765US             </td><td>LGA                </td><td>BOS                </td><td> 37                </td><td> 184               </td><td> 6                 </td><td> 0                 </td><td>2013-08-22 06:00:00</td></tr>
	<tr><td>2013               </td><td> 4                 </td><td> 5                 </td><td>1433               </td><td>1345               </td><td>48                 </td><td>1813               </td><td>1700               </td><td> 73                </td><td>AA                 </td><td>1073               </td><td>N3FMAA             </td><td>LGA                </td><td>MIA                </td><td>186                </td><td>1096               </td><td>13                 </td><td>45                 </td><td>2013-04-05 13:00:00</td></tr>
	<tr><td>2013               </td><td>10                 </td><td>29                 </td><td> 836               </td><td> 835               </td><td> 1                 </td><td>1100               </td><td>1050               </td><td> 10                </td><td>EV                 </td><td>4419               </td><td>N11119             </td><td>EWR                </td><td>XNA                </td><td>178                </td><td>1131               </td><td> 8                 </td><td>35                 </td><td>2013-10-29 08:00:00</td></tr>
</tbody>
</table>




```R
sample_frac(flights, 0.01) # mensampel 1 % dari seluruh baris
```


<table>
<thead><tr><th scope=col>year</th><th scope=col>month</th><th scope=col>day</th><th scope=col>dep_time</th><th scope=col>sched_dep_time</th><th scope=col>dep_delay</th><th scope=col>arr_time</th><th scope=col>sched_arr_time</th><th scope=col>arr_delay</th><th scope=col>carrier</th><th scope=col>flight</th><th scope=col>tailnum</th><th scope=col>origin</th><th scope=col>dest</th><th scope=col>air_time</th><th scope=col>distance</th><th scope=col>hour</th><th scope=col>minute</th><th scope=col>time_hour</th></tr></thead>
<tbody>
	<tr><td>2013               </td><td> 8                 </td><td> 3                 </td><td> 745               </td><td> 752               </td><td> -7                </td><td> 856               </td><td> 913               </td><td>-17                </td><td>B6                 </td><td>2702               </td><td>N339JB             </td><td>JFK                </td><td>BUF                </td><td> 58                </td><td> 301               </td><td> 7                 </td><td>52                 </td><td>2013-08-03 07:00:00</td></tr>
	<tr><td>2013               </td><td>10                 </td><td>19                 </td><td> 653               </td><td> 700               </td><td> -7                </td><td> 953               </td><td>1003               </td><td>-10                </td><td>B6                 </td><td>  23               </td><td>N556JB             </td><td>JFK                </td><td>LAX                </td><td>339                </td><td>2475               </td><td> 7                 </td><td> 0                 </td><td>2013-10-19 07:00:00</td></tr>
	<tr><td>2013               </td><td> 7                 </td><td>17                 </td><td>2107               </td><td>2030               </td><td> 37                </td><td>2224               </td><td>2211               </td><td> 13                </td><td>9E                 </td><td>4127               </td><td>N8972E             </td><td>JFK                </td><td>IAD                </td><td> 43                </td><td> 228               </td><td>20                 </td><td>30                 </td><td>2013-07-17 20:00:00</td></tr>
	<tr><td>2013               </td><td> 4                 </td><td> 4                 </td><td>1059               </td><td> 930               </td><td> 89                </td><td>1421               </td><td>1255               </td><td> 86                </td><td>UA                 </td><td> 347               </td><td>N557UA             </td><td>JFK                </td><td>SFO                </td><td>348                </td><td>2586               </td><td> 9                 </td><td>30                 </td><td>2013-04-04 09:00:00</td></tr>
	<tr><td>2013               </td><td> 5                 </td><td>13                 </td><td>1825               </td><td>1829               </td><td> -4                </td><td>2042               </td><td>2031               </td><td> 11                </td><td>US                 </td><td>1973               </td><td>N162UW             </td><td>EWR                </td><td>CLT                </td><td> 79                </td><td> 529               </td><td>18                 </td><td>29                 </td><td>2013-05-13 18:00:00</td></tr>
	<tr><td>2013               </td><td> 9                 </td><td>15                 </td><td> 620               </td><td> 625               </td><td> -5                </td><td> 835               </td><td> 850               </td><td>-15                </td><td>MQ                 </td><td>3550               </td><td>N505MQ             </td><td>LGA                </td><td>ATL                </td><td>107                </td><td> 762               </td><td> 6                 </td><td>25                 </td><td>2013-09-15 06:00:00</td></tr>
	<tr><td>2013               </td><td> 5                 </td><td>25                 </td><td>1609               </td><td>1557               </td><td> 12                </td><td>1930               </td><td>1908               </td><td> 22                </td><td>DL                 </td><td>1043               </td><td>N650DL             </td><td>JFK                </td><td>SEA                </td><td>321                </td><td>2422               </td><td>15                 </td><td>57                 </td><td>2013-05-25 15:00:00</td></tr>
	<tr><td>2013               </td><td> 9                 </td><td> 1                 </td><td>1550               </td><td>1600               </td><td>-10                </td><td>1819               </td><td>1849               </td><td>-30                </td><td>B6                 </td><td> 543               </td><td>N657JB             </td><td>EWR                </td><td>PBI                </td><td>132                </td><td>1023               </td><td>16                 </td><td> 0                 </td><td>2013-09-01 16:00:00</td></tr>
	<tr><td>2013               </td><td> 3                 </td><td> 1                 </td><td> 703               </td><td> 650               </td><td> 13                </td><td> 846               </td><td> 858               </td><td>-12                </td><td>EV                 </td><td>4138               </td><td>N16149             </td><td>EWR                </td><td>MSP                </td><td>145                </td><td>1008               </td><td> 6                 </td><td>50                 </td><td>2013-03-01 06:00:00</td></tr>
	<tr><td>2013               </td><td> 5                 </td><td>30                 </td><td> 906               </td><td> 900               </td><td>  6                </td><td>1146               </td><td>1210               </td><td>-24                </td><td>UA                 </td><td>1192               </td><td>N38451             </td><td>EWR                </td><td>SEA                </td><td>296                </td><td>2402               </td><td> 9                 </td><td> 0                 </td><td>2013-05-30 09:00:00</td></tr>
	<tr><td>2013               </td><td>11                 </td><td>18                 </td><td> 955               </td><td>1000               </td><td> -5                </td><td>1326               </td><td>1333               </td><td> -7                </td><td>DL                 </td><td> 469               </td><td>N713TW             </td><td>JFK                </td><td>SFO                </td><td>366                </td><td>2586               </td><td>10                 </td><td> 0                 </td><td>2013-11-18 10:00:00</td></tr>
	<tr><td>2013               </td><td> 4                 </td><td>11                 </td><td>1415               </td><td>1415               </td><td>  0                </td><td>1611               </td><td>1610               </td><td>  1                </td><td>MQ                 </td><td>4588               </td><td>N504MQ             </td><td>LGA                </td><td>MSP                </td><td>153                </td><td>1020               </td><td>14                 </td><td>15                 </td><td>2013-04-11 14:00:00</td></tr>
	<tr><td>2013               </td><td> 9                 </td><td> 2                 </td><td> 603               </td><td> 611               </td><td> -8                </td><td> 714               </td><td> 722               </td><td> -8                </td><td>EV                 </td><td>4533               </td><td>N16963             </td><td>EWR                </td><td>BUF                </td><td> 50                </td><td> 282               </td><td> 6                 </td><td>11                 </td><td>2013-09-02 06:00:00</td></tr>
	<tr><td>2013               </td><td> 5                 </td><td> 6                 </td><td>1052               </td><td>1055               </td><td> -3                </td><td>1156               </td><td>1228               </td><td>-32                </td><td>UA                 </td><td>1210               </td><td>N23707             </td><td>EWR                </td><td>ORD                </td><td>104                </td><td> 719               </td><td>10                 </td><td>55                 </td><td>2013-05-06 10:00:00</td></tr>
	<tr><td>2013               </td><td>10                 </td><td>28                 </td><td>1823               </td><td>1725               </td><td> 58                </td><td>2050               </td><td>2019               </td><td> 31                </td><td>UA                 </td><td>1109               </td><td>N14102             </td><td>EWR                </td><td>MCO                </td><td>125                </td><td> 937               </td><td>17                 </td><td>25                 </td><td>2013-10-28 17:00:00</td></tr>
	<tr><td>2013               </td><td> 8                 </td><td> 9                 </td><td>2216               </td><td>2040               </td><td> 96                </td><td>2344               </td><td>2154               </td><td>110                </td><td>B6                 </td><td>2680               </td><td>N249JB             </td><td>EWR                </td><td>BOS                </td><td> 45                </td><td> 200               </td><td>20                 </td><td>40                 </td><td>2013-08-09 20:00:00</td></tr>
	<tr><td>2013               </td><td>10                 </td><td> 6                 </td><td>1747               </td><td>1732               </td><td> 15                </td><td>2035               </td><td>1959               </td><td> 36                </td><td>FL                 </td><td> 623               </td><td>N998AT             </td><td>LGA                </td><td>ATL                </td><td>146                </td><td> 762               </td><td>17                 </td><td>32                 </td><td>2013-10-06 17:00:00</td></tr>
	<tr><td>2013               </td><td> 2                 </td><td> 4                 </td><td>1624               </td><td>1630               </td><td> -6                </td><td>1836               </td><td>1838               </td><td> -2                </td><td>DL                 </td><td>2231               </td><td>N326NB             </td><td>LGA                </td><td>DTW                </td><td> 95                </td><td> 502               </td><td>16                 </td><td>30                 </td><td>2013-02-04 16:00:00</td></tr>
	<tr><td>2013               </td><td> 6                 </td><td>17                 </td><td>1956               </td><td>1959               </td><td> -3                </td><td>2123               </td><td>2140               </td><td>-17                </td><td>DL                 </td><td> 975               </td><td>N952DL             </td><td>LGA                </td><td>PIT                </td><td> 56                </td><td> 335               </td><td>19                 </td><td>59                 </td><td>2013-06-17 19:00:00</td></tr>
	<tr><td>2013               </td><td>10                 </td><td>29                 </td><td>1321               </td><td>1257               </td><td> 24                </td><td>1425               </td><td>1414               </td><td> 11                </td><td>EV                 </td><td>6054               </td><td>N13995             </td><td>EWR                </td><td>IAD                </td><td> 46                </td><td> 212               </td><td>12                 </td><td>57                 </td><td>2013-10-29 12:00:00</td></tr>
	<tr><td>2013               </td><td>12                 </td><td>24                 </td><td> 941               </td><td> 945               </td><td> -4                </td><td>1153               </td><td>1202               </td><td> -9                </td><td>EV                 </td><td>4714               </td><td>N33182             </td><td>EWR                </td><td>CLT                </td><td>100                </td><td> 529               </td><td> 9                 </td><td>45                 </td><td>2013-12-24 09:00:00</td></tr>
	<tr><td>2013               </td><td> 4                 </td><td>29                 </td><td>2146               </td><td>2130               </td><td> 16                </td><td>  35               </td><td>  16               </td><td> 19                </td><td>B6                 </td><td> 383               </td><td>N729JB             </td><td>LGA                </td><td>FLL                </td><td>153                </td><td>1076               </td><td>21                 </td><td>30                 </td><td>2013-04-29 21:00:00</td></tr>
	<tr><td>2013               </td><td> 3                 </td><td> 4                 </td><td>1647               </td><td>1630               </td><td> 17                </td><td>1953               </td><td>1954               </td><td> -1                </td><td>B6                 </td><td> 675               </td><td>N627JB             </td><td>JFK                </td><td>LAX                </td><td>344                </td><td>2475               </td><td>16                 </td><td>30                 </td><td>2013-03-04 16:00:00</td></tr>
	<tr><td>2013               </td><td> 7                 </td><td>17                 </td><td>1920               </td><td>1930               </td><td>-10                </td><td>2044               </td><td>2051               </td><td> -7                </td><td>EV                 </td><td>5769               </td><td>N830AS             </td><td>LGA                </td><td>IAD                </td><td> 46                </td><td> 229               </td><td>19                 </td><td>30                 </td><td>2013-07-17 19:00:00</td></tr>
	<tr><td>2013               </td><td> 1                 </td><td>15                 </td><td>  NA               </td><td>1359               </td><td> NA                </td><td>  NA               </td><td>1656               </td><td> NA                </td><td>UA                 </td><td> 424               </td><td>NA                 </td><td>EWR                </td><td>PBI                </td><td> NA                </td><td>1023               </td><td>13                 </td><td>59                 </td><td>2013-01-15 13:00:00</td></tr>
	<tr><td>2013               </td><td> 2                 </td><td> 5                 </td><td>1453               </td><td>1500               </td><td> -7                </td><td>1711               </td><td>1655               </td><td> 16                </td><td>MQ                 </td><td>4429               </td><td>N722MQ             </td><td>LGA                </td><td>CMH                </td><td> 91                </td><td> 479               </td><td>15                 </td><td> 0                 </td><td>2013-02-05 15:00:00</td></tr>
	<tr><td>2013               </td><td> 1                 </td><td>11                 </td><td>1557               </td><td>1600               </td><td> -3                </td><td>1720               </td><td>1712               </td><td>  8                </td><td>US                 </td><td>2134               </td><td>N952UW             </td><td>LGA                </td><td>BOS                </td><td> 41                </td><td> 184               </td><td>16                 </td><td> 0                 </td><td>2013-01-11 16:00:00</td></tr>
	<tr><td>2013               </td><td>11                 </td><td>16                 </td><td>2108               </td><td>2059               </td><td>  9                </td><td>2237               </td><td>2238               </td><td> -1                </td><td>EV                 </td><td>4348               </td><td>N12569             </td><td>EWR                </td><td>CLE                </td><td> 65                </td><td> 404               </td><td>20                 </td><td>59                 </td><td>2013-11-16 20:00:00</td></tr>
	<tr><td>2013               </td><td> 6                 </td><td>11                 </td><td>2013               </td><td>2015               </td><td> -2                </td><td>2240               </td><td>2308               </td><td>-28                </td><td>B6                 </td><td>  43               </td><td>N608JB             </td><td>JFK                </td><td>MCO                </td><td>124                </td><td> 944               </td><td>20                 </td><td>15                 </td><td>2013-06-11 20:00:00</td></tr>
	<tr><td>2013               </td><td> 5                 </td><td>24                 </td><td> 758               </td><td> 759               </td><td> -1                </td><td> 956               </td><td>1020               </td><td>-24                </td><td>EV                 </td><td>4991               </td><td>N716EV             </td><td>LGA                </td><td>MCI                </td><td>147                </td><td>1107               </td><td> 7                 </td><td>59                 </td><td>2013-05-24 07:00:00</td></tr>
	<tr><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td></tr>
	<tr><td>2013               </td><td> 7                 </td><td>14                 </td><td> 825               </td><td> 830               </td><td> -5                </td><td>1008               </td><td>1028               </td><td>-20                </td><td>EV                 </td><td>4297               </td><td>N12567             </td><td>EWR                </td><td>DTW                </td><td> 75                </td><td> 488               </td><td> 8                 </td><td>30                 </td><td>2013-07-14 08:00:00</td></tr>
	<tr><td>2013               </td><td> 3                 </td><td>28                 </td><td>1535               </td><td>1540               </td><td> -5                </td><td>1736               </td><td>1820               </td><td>-44                </td><td>DL                 </td><td>1344               </td><td>N361NB             </td><td>LGA                </td><td>MCI                </td><td>154                </td><td>1107               </td><td>15                 </td><td>40                 </td><td>2013-03-28 15:00:00</td></tr>
	<tr><td>2013               </td><td> 7                 </td><td>20                 </td><td>2008               </td><td>2005               </td><td>  3                </td><td>2317               </td><td>2300               </td><td> 17                </td><td>UA                 </td><td>1417               </td><td>N16703             </td><td>EWR                </td><td>PBI                </td><td>139                </td><td>1023               </td><td>20                 </td><td> 5                 </td><td>2013-07-20 20:00:00</td></tr>
	<tr><td>2013               </td><td> 3                 </td><td>29                 </td><td>1952               </td><td>1955               </td><td> -3                </td><td>2230               </td><td>2240               </td><td>-10                </td><td>EV                 </td><td>4204               </td><td>N11137             </td><td>EWR                </td><td>OKC                </td><td>192                </td><td>1325               </td><td>19                 </td><td>55                 </td><td>2013-03-29 19:00:00</td></tr>
	<tr><td>2013               </td><td> 9                 </td><td>22                 </td><td>1255               </td><td>1300               </td><td> -5                </td><td>1415               </td><td>1415               </td><td>  0                </td><td>US                 </td><td>2181               </td><td>N963UW             </td><td>LGA                </td><td>DCA                </td><td> 46                </td><td> 214               </td><td>13                 </td><td> 0                 </td><td>2013-09-22 13:00:00</td></tr>
	<tr><td>2013               </td><td>10                 </td><td> 6                 </td><td> 837               </td><td> 840               </td><td> -3                </td><td>1001               </td><td> 955               </td><td>  6                </td><td>UA                 </td><td>1437               </td><td>N24706             </td><td>EWR                </td><td>BOS                </td><td> 43                </td><td> 200               </td><td> 8                 </td><td>40                 </td><td>2013-10-06 08:00:00</td></tr>
	<tr><td>2013               </td><td> 9                 </td><td>24                 </td><td> 814               </td><td> 820               </td><td> -6                </td><td>1056               </td><td>1110               </td><td>-14                </td><td>B6                 </td><td> 281               </td><td>N328JB             </td><td>JFK                </td><td>HOU                </td><td>199                </td><td>1428               </td><td> 8                 </td><td>20                 </td><td>2013-09-24 08:00:00</td></tr>
	<tr><td>2013               </td><td> 2                 </td><td>17                 </td><td>1947               </td><td>1910               </td><td> 37                </td><td>2256               </td><td>2228               </td><td> 28                </td><td>B6                 </td><td>  87               </td><td>N558JB             </td><td>JFK                </td><td>SLC                </td><td>284                </td><td>1990               </td><td>19                 </td><td>10                 </td><td>2013-02-17 19:00:00</td></tr>
	<tr><td>2013               </td><td> 3                 </td><td>15                 </td><td>1514               </td><td>1456               </td><td> 18                </td><td>1813               </td><td>1759               </td><td> 14                </td><td>UA                 </td><td>1186               </td><td>N13716             </td><td>EWR                </td><td>MIA                </td><td>154                </td><td>1085               </td><td>14                 </td><td>56                 </td><td>2013-03-15 14:00:00</td></tr>
	<tr><td>2013               </td><td> 9                 </td><td>11                 </td><td>2334               </td><td>2125               </td><td>129                </td><td>  37               </td><td>2247               </td><td>110                </td><td>EV                 </td><td>5489               </td><td>N712EV             </td><td>LGA                </td><td>CHO                </td><td> 47                </td><td> 305               </td><td>21                 </td><td>25                 </td><td>2013-09-11 21:00:00</td></tr>
	<tr><td>2013               </td><td> 8                 </td><td>18                 </td><td> 839               </td><td> 843               </td><td> -4                </td><td>1126               </td><td>1135               </td><td> -9                </td><td>UA                 </td><td> 545               </td><td>N447UA             </td><td>LGA                </td><td>IAH                </td><td>195                </td><td>1416               </td><td> 8                 </td><td>43                 </td><td>2013-08-18 08:00:00</td></tr>
	<tr><td>2013               </td><td> 5                 </td><td>30                 </td><td>1651               </td><td>1529               </td><td> 82                </td><td>1857               </td><td>1740               </td><td> 77                </td><td>EV                 </td><td>4708               </td><td>N14972             </td><td>EWR                </td><td>SDF                </td><td>101                </td><td> 642               </td><td>15                 </td><td>29                 </td><td>2013-05-30 15:00:00</td></tr>
	<tr><td>2013               </td><td>10                 </td><td>17                 </td><td>1832               </td><td>1820               </td><td> 12                </td><td>2140               </td><td>2125               </td><td> 15                </td><td>UA                 </td><td> 726               </td><td>N453UA             </td><td>EWR                </td><td>FLL                </td><td>142                </td><td>1065               </td><td>18                 </td><td>20                 </td><td>2013-10-17 18:00:00</td></tr>
	<tr><td>2013               </td><td> 8                 </td><td>12                 </td><td>1859               </td><td>1827               </td><td> 32                </td><td>2047               </td><td>2033               </td><td> 14                </td><td>US                 </td><td> 425               </td><td>N547UW             </td><td>JFK                </td><td>CLT                </td><td> 83                </td><td> 541               </td><td>18                 </td><td>27                 </td><td>2013-08-12 18:00:00</td></tr>
	<tr><td>2013               </td><td> 2                 </td><td> 5                 </td><td>1342               </td><td>1330               </td><td> 12                </td><td>1658               </td><td>1616               </td><td> 42                </td><td>B6                 </td><td> 525               </td><td>N266JB             </td><td>EWR                </td><td>MCO                </td><td>148                </td><td> 937               </td><td>13                 </td><td>30                 </td><td>2013-02-05 13:00:00</td></tr>
	<tr><td>2013               </td><td> 4                 </td><td>10                 </td><td>1703               </td><td>1655               </td><td>  8                </td><td>2129               </td><td>2010               </td><td> 79                </td><td>AA                 </td><td> 773               </td><td>N554AA             </td><td>LGA                </td><td>DFW                </td><td>241                </td><td>1389               </td><td>16                 </td><td>55                 </td><td>2013-04-10 16:00:00</td></tr>
	<tr><td>2013               </td><td> 6                 </td><td>25                 </td><td>1336               </td><td>1100               </td><td>156                </td><td>1606               </td><td>1349               </td><td>137                </td><td>DL                 </td><td> 695               </td><td>N993DL             </td><td>JFK                </td><td>MCO                </td><td>125                </td><td> 944               </td><td>11                 </td><td> 0                 </td><td>2013-06-25 11:00:00</td></tr>
	<tr><td>2013               </td><td> 9                 </td><td> 3                 </td><td> 957               </td><td>1000               </td><td> -3                </td><td>1218               </td><td>1237               </td><td>-19                </td><td>DL                 </td><td>1847               </td><td>N926DL             </td><td>LGA                </td><td>ATL                </td><td>110                </td><td> 762               </td><td>10                 </td><td> 0                 </td><td>2013-09-03 10:00:00</td></tr>
	<tr><td>2013               </td><td> 7                 </td><td>25                 </td><td> 746               </td><td> 745               </td><td>  1                </td><td> 929               </td><td>1000               </td><td>-31                </td><td>9E                 </td><td>3353               </td><td>N600LR             </td><td>JFK                </td><td>DTW                </td><td> 78                </td><td> 509               </td><td> 7                 </td><td>45                 </td><td>2013-07-25 07:00:00</td></tr>
	<tr><td>2013               </td><td> 3                 </td><td>29                 </td><td>1815               </td><td>1815               </td><td>  0                </td><td>2123               </td><td>2147               </td><td>-24                </td><td>B6                 </td><td> 173               </td><td>N789JB             </td><td>JFK                </td><td>SJC                </td><td>354                </td><td>2569               </td><td>18                 </td><td>15                 </td><td>2013-03-29 18:00:00</td></tr>
	<tr><td>2013               </td><td> 5                 </td><td> 4                 </td><td>1403               </td><td>1359               </td><td>  4                </td><td>1509               </td><td>1515               </td><td> -6                </td><td>EV                 </td><td>4633               </td><td>N11539             </td><td>EWR                </td><td>BTV                </td><td> 46                </td><td> 266               </td><td>13                 </td><td>59                 </td><td>2013-05-04 13:00:00</td></tr>
	<tr><td>2013               </td><td> 4                 </td><td> 7                 </td><td>1556               </td><td>1600               </td><td> -4                </td><td>1829               </td><td>1847               </td><td>-18                </td><td>DL                 </td><td>1387               </td><td>N397DA             </td><td>JFK                </td><td>DEN                </td><td>232                </td><td>1626               </td><td>16                 </td><td> 0                 </td><td>2013-04-07 16:00:00</td></tr>
	<tr><td>2013               </td><td>11                 </td><td> 7                 </td><td>1557               </td><td>1610               </td><td>-13                </td><td>1810               </td><td>1819               </td><td> -9                </td><td>EV                 </td><td>4352               </td><td>N11547             </td><td>EWR                </td><td>CVG                </td><td>110                </td><td> 569               </td><td>16                 </td><td>10                 </td><td>2013-11-07 16:00:00</td></tr>
	<tr><td>2013               </td><td> 7                 </td><td>11                 </td><td> 801               </td><td> 800               </td><td>  1                </td><td>1044               </td><td>1104               </td><td>-20                </td><td>DL                 </td><td>1271               </td><td>N3747D             </td><td>JFK                </td><td>FLL                </td><td>138                </td><td>1069               </td><td> 8                 </td><td> 0                 </td><td>2013-07-11 08:00:00</td></tr>
	<tr><td>2013               </td><td> 6                 </td><td>18                 </td><td>1313               </td><td>1253               </td><td> 20                </td><td>1553               </td><td>1520               </td><td> 33                </td><td>UA                 </td><td> 353               </td><td>N818UA             </td><td>EWR                </td><td>ATL                </td><td>120                </td><td> 746               </td><td>12                 </td><td>53                 </td><td>2013-06-18 12:00:00</td></tr>
	<tr><td>2013               </td><td> 3                 </td><td> 5                 </td><td> 745               </td><td> 600               </td><td>105                </td><td>1006               </td><td> 825               </td><td>101                </td><td>MQ                 </td><td>4650               </td><td>N9EAMQ             </td><td>LGA                </td><td>ATL                </td><td>117                </td><td> 762               </td><td> 6                 </td><td> 0                 </td><td>2013-03-05 06:00:00</td></tr>
	<tr><td>2013               </td><td> 7                 </td><td> 2                 </td><td>1258               </td><td>1144               </td><td> 74                </td><td>1433               </td><td>1316               </td><td> 77                </td><td>EV                 </td><td>4212               </td><td>N14105             </td><td>EWR                </td><td>RDU                </td><td> 67                </td><td> 416               </td><td>11                 </td><td>44                 </td><td>2013-07-02 11:00:00</td></tr>
	<tr><td>2013               </td><td> 8                 </td><td>21                 </td><td>2144               </td><td>2152               </td><td> -8                </td><td>2240               </td><td>2258               </td><td>-18                </td><td>EV                 </td><td>4276               </td><td>N11119             </td><td>EWR                </td><td>BDL                </td><td> 23                </td><td> 116               </td><td>21                 </td><td>52                 </td><td>2013-08-21 21:00:00</td></tr>
	<tr><td>2013               </td><td>10                 </td><td>16                 </td><td> 752               </td><td> 746               </td><td>  6                </td><td>1027               </td><td>1021               </td><td>  6                </td><td>UA                 </td><td>1289               </td><td>N26215             </td><td>EWR                </td><td>LAS                </td><td>301                </td><td>2227               </td><td> 7                 </td><td>46                 </td><td>2013-10-16 07:00:00</td></tr>
	<tr><td>2013               </td><td> 4                 </td><td>30                 </td><td>2150               </td><td>2155               </td><td> -5                </td><td>2247               </td><td>2312               </td><td>-25                </td><td>UA                 </td><td>1142               </td><td>N18243             </td><td>EWR                </td><td>BOS                </td><td> 36                </td><td> 200               </td><td>21                 </td><td>55                 </td><td>2013-04-30 21:00:00</td></tr>
</tbody>
</table>



## Operator *pipe*


```R
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



### *Nesting*


```R
filter(df, mpg > 20)
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
sample_n(filter(df, mpg > 20), size = 5) # dua operasi secara bersamaan
```


<table>
<thead><tr><th></th><th scope=col>mpg</th><th scope=col>cyl</th><th scope=col>disp</th><th scope=col>hp</th><th scope=col>drat</th><th scope=col>wt</th><th scope=col>qsec</th><th scope=col>vs</th><th scope=col>am</th><th scope=col>gear</th><th scope=col>carb</th></tr></thead>
<tbody>
	<tr><th scope=row>Merc 230</th><td>22.8 </td><td>4    </td><td>140.8</td><td> 95  </td><td>3.92 </td><td>3.150</td><td>22.90</td><td>1    </td><td>0    </td><td>4    </td><td>2    </td></tr>
	<tr><th scope=row>Lotus Europa</th><td>30.4 </td><td>4    </td><td> 95.1</td><td>113  </td><td>3.77 </td><td>1.513</td><td>16.90</td><td>1    </td><td>1    </td><td>5    </td><td>2    </td></tr>
	<tr><th scope=row>Datsun 710</th><td>22.8 </td><td>4    </td><td>108.0</td><td> 93  </td><td>3.85 </td><td>2.320</td><td>18.61</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Volvo 142E</th><td>21.4 </td><td>4    </td><td>121.0</td><td>109  </td><td>4.11 </td><td>2.780</td><td>18.60</td><td>1    </td><td>1    </td><td>4    </td><td>2    </td></tr>
	<tr><th scope=row>Hornet 4 Drive</th><td>21.4 </td><td>6    </td><td>258.0</td><td>110  </td><td>3.08 </td><td>3.215</td><td>19.44</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
</tbody>
</table>




```R
hasil <- arrange(sample_n(filter(df, mpg > 20), size = 5), desc(mpg))
# memfilter df untuk mpg > 20
# mengambil 5 baris sampel acak
# mengurutkannya berdasarkan kolom mpg secara terbalik (descending order)
hasil
```


<table>
<thead><tr><th></th><th scope=col>mpg</th><th scope=col>cyl</th><th scope=col>disp</th><th scope=col>hp</th><th scope=col>drat</th><th scope=col>wt</th><th scope=col>qsec</th><th scope=col>vs</th><th scope=col>am</th><th scope=col>gear</th><th scope=col>carb</th></tr></thead>
<tbody>
	<tr><th scope=row>Honda Civic</th><td>30.4 </td><td>4    </td><td> 75.7</td><td> 52  </td><td>4.93 </td><td>1.615</td><td>18.52</td><td>1    </td><td>1    </td><td>4    </td><td>2    </td></tr>
	<tr><th scope=row>Fiat X1-9</th><td>27.3 </td><td>4    </td><td> 79.0</td><td> 66  </td><td>4.08 </td><td>1.935</td><td>18.90</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Toyota Corona</th><td>21.5 </td><td>4    </td><td>120.1</td><td> 97  </td><td>3.70 </td><td>2.465</td><td>20.01</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
	<tr><th scope=row>Hornet 4 Drive</th><td>21.4 </td><td>6    </td><td>258.0</td><td>110  </td><td>3.08 </td><td>3.215</td><td>19.44</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
	<tr><th scope=row>Mazda RX4 Wag</th><td>21.0 </td><td>6    </td><td>160.0</td><td>110  </td><td>3.90 </td><td>2.875</td><td>17.02</td><td>0    </td><td>1    </td><td>4    </td><td>4    </td></tr>
</tbody>
</table>




```R
# susah dibaca!!!
```

### Penugasan berganda


```R
a <- filter(df, mpg > 20)
b <- sample_n(a, size = 5)
hasil <- arrange(b, desc(mpg))
hasil
```


<table>
<thead><tr><th></th><th scope=col>mpg</th><th scope=col>cyl</th><th scope=col>disp</th><th scope=col>hp</th><th scope=col>drat</th><th scope=col>wt</th><th scope=col>qsec</th><th scope=col>vs</th><th scope=col>am</th><th scope=col>gear</th><th scope=col>carb</th></tr></thead>
<tbody>
	<tr><th scope=row>Toyota Corolla</th><td>33.9 </td><td>4    </td><td> 71.1</td><td>65   </td><td>4.22 </td><td>1.835</td><td>19.90</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Fiat 128</th><td>32.4 </td><td>4    </td><td> 78.7</td><td>66   </td><td>4.08 </td><td>2.200</td><td>19.47</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Honda Civic</th><td>30.4 </td><td>4    </td><td> 75.7</td><td>52   </td><td>4.93 </td><td>1.615</td><td>18.52</td><td>1    </td><td>1    </td><td>4    </td><td>2    </td></tr>
	<tr><th scope=row>Fiat X1-9</th><td>27.3 </td><td>4    </td><td> 79.0</td><td>66   </td><td>4.08 </td><td>1.935</td><td>18.90</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Toyota Corona</th><td>21.5 </td><td>4    </td><td>120.1</td><td>97   </td><td>3.70 </td><td>2.465</td><td>20.01</td><td>1    </td><td>0    </td><td>3    </td><td>1    </td></tr>
</tbody>
</table>



### Operator *pipe*


```R
hasil <- df %>% filter(mpg > 20) %>% sample_n(size = 5) %>% arrange(desc(mpg))
# lebih mudah diBACA!
hasil
```


<table>
<thead><tr><th></th><th scope=col>mpg</th><th scope=col>cyl</th><th scope=col>disp</th><th scope=col>hp</th><th scope=col>drat</th><th scope=col>wt</th><th scope=col>qsec</th><th scope=col>vs</th><th scope=col>am</th><th scope=col>gear</th><th scope=col>carb</th></tr></thead>
<tbody>
	<tr><th scope=row>Fiat 128</th><td>32.4 </td><td>4    </td><td> 78.7</td><td> 66  </td><td>4.08 </td><td>2.200</td><td>19.47</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Fiat X1-9</th><td>27.3 </td><td>4    </td><td> 79.0</td><td> 66  </td><td>4.08 </td><td>1.935</td><td>18.90</td><td>1    </td><td>1    </td><td>4    </td><td>1    </td></tr>
	<tr><th scope=row>Porsche 914-2</th><td>26.0 </td><td>4    </td><td>120.3</td><td> 91  </td><td>4.43 </td><td>2.140</td><td>16.70</td><td>0    </td><td>1    </td><td>5    </td><td>2    </td></tr>
	<tr><th scope=row>Merc 240D</th><td>24.4 </td><td>4    </td><td>146.7</td><td> 62  </td><td>3.69 </td><td>3.190</td><td>20.00</td><td>1    </td><td>0    </td><td>4    </td><td>2    </td></tr>
	<tr><th scope=row>Mazda RX4 Wag</th><td>21.0 </td><td>6    </td><td>160.0</td><td>110  </td><td>3.90 </td><td>2.875</td><td>17.02</td><td>0    </td><td>1    </td><td>4    </td><td>4    </td></tr>
</tbody>
</table>



## tidyr

 * dplyr $\rightarrow$ manipulasi data.
 * tidyr $\rightarrow$ pembersihan data.


```R
library(tidyr)
library(data.table) # punya kelebihan soal waktu eksekusi dibandingkan data frame
```


    Attaching package: ‘data.table’
    
    The following objects are masked from ‘package:dplyr’:
    
        between, first, last



### `gather()`

Membagi kolom menjadi pasangan *key*-*value*


```R
v <- c('A', 'B', 'C','A', 'B', 'C','A', 'B', 'C')
thn <- c(2020,2021,2022,2020,2021,2022,2020,2021,2022)

q1 <- runif(n = 9, min = 0, max = 100)
q2 <- runif(n = 9, min = 0, max = 100)
q3 <- runif(n = 9, min = 0, max = 100)
q4 <- runif(n = 9, min = 0, max = 100)

df <- data.frame(Perusahaan = v, Tahun = thn, q1, q2, q3, q4)
df
```


<table>
<thead><tr><th scope=col>Perusahaan</th><th scope=col>Tahun</th><th scope=col>q1</th><th scope=col>q2</th><th scope=col>q3</th><th scope=col>q4</th></tr></thead>
<tbody>
	<tr><td>A        </td><td>2020     </td><td>71.401874</td><td>34.04511 </td><td>75.01010 </td><td>35.93238 </td></tr>
	<tr><td>B        </td><td>2021     </td><td> 6.254729</td><td>37.22828 </td><td>58.15716 </td><td> 5.82554 </td></tr>
	<tr><td>C        </td><td>2022     </td><td>58.959634</td><td>87.88993 </td><td>43.93756 </td><td>14.01085 </td></tr>
	<tr><td>A        </td><td>2020     </td><td>60.140881</td><td>69.06750 </td><td>33.05298 </td><td>69.82548 </td></tr>
	<tr><td>B        </td><td>2021     </td><td>12.791612</td><td>76.31263 </td><td>66.74539 </td><td>73.95468 </td></tr>
	<tr><td>C        </td><td>2022     </td><td>77.511686</td><td>15.82185 </td><td>32.11450 </td><td>84.96146 </td></tr>
	<tr><td>A        </td><td>2020     </td><td>31.628151</td><td>45.47135 </td><td>77.67680 </td><td>77.78378 </td></tr>
	<tr><td>B        </td><td>2021     </td><td>87.868777</td><td>72.97178 </td><td>55.51417 </td><td>39.13752 </td></tr>
	<tr><td>C        </td><td>2022     </td><td>99.692759</td><td>15.36461 </td><td>73.52894 </td><td>42.38900 </td></tr>
</tbody>
</table>




```R
gather(data = df, key = 'Kuarter', value = 'Keuntungan', q1:q4)
# 4 kolom dibuat jadi 2 kolom
```


<table>
<thead><tr><th scope=col>Perusahaan</th><th scope=col>Tahun</th><th scope=col>Kuarter</th><th scope=col>Keuntungan</th></tr></thead>
<tbody>
	<tr><td>A        </td><td>2020     </td><td>q1       </td><td>71.401874</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q1       </td><td> 6.254729</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q1       </td><td>58.959634</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q1       </td><td>60.140881</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q1       </td><td>12.791612</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q1       </td><td>77.511686</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q1       </td><td>31.628151</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q1       </td><td>87.868777</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q1       </td><td>99.692759</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q2       </td><td>34.045112</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q2       </td><td>37.228278</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q2       </td><td>87.889935</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q2       </td><td>69.067497</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q2       </td><td>76.312626</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q2       </td><td>15.821849</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q2       </td><td>45.471355</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q2       </td><td>72.971783</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q2       </td><td>15.364613</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q3       </td><td>75.010101</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q3       </td><td>58.157156</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q3       </td><td>43.937558</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q3       </td><td>33.052977</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q3       </td><td>66.745387</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q3       </td><td>32.114503</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q3       </td><td>77.676802</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q3       </td><td>55.514168</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q3       </td><td>73.528938</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q4       </td><td>35.932385</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q4       </td><td> 5.825540</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q4       </td><td>14.010853</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q4       </td><td>69.825478</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q4       </td><td>73.954683</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q4       </td><td>84.961463</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q4       </td><td>77.783779</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q4       </td><td>39.137522</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q4       </td><td>42.389005</td></tr>
</tbody>
</table>




```R
# menggunakan fungsi gather() dengan menggunakan operator pipe

df %>% gather(key = 'Kuarter', value = 'Keuntungan', q1:q4)
```


<table>
<thead><tr><th scope=col>Perusahaan</th><th scope=col>Tahun</th><th scope=col>Kuarter</th><th scope=col>Keuntungan</th></tr></thead>
<tbody>
	<tr><td>A        </td><td>2020     </td><td>q1       </td><td>71.401874</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q1       </td><td> 6.254729</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q1       </td><td>58.959634</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q1       </td><td>60.140881</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q1       </td><td>12.791612</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q1       </td><td>77.511686</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q1       </td><td>31.628151</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q1       </td><td>87.868777</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q1       </td><td>99.692759</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q2       </td><td>34.045112</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q2       </td><td>37.228278</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q2       </td><td>87.889935</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q2       </td><td>69.067497</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q2       </td><td>76.312626</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q2       </td><td>15.821849</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q2       </td><td>45.471355</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q2       </td><td>72.971783</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q2       </td><td>15.364613</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q3       </td><td>75.010101</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q3       </td><td>58.157156</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q3       </td><td>43.937558</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q3       </td><td>33.052977</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q3       </td><td>66.745387</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q3       </td><td>32.114503</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q3       </td><td>77.676802</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q3       </td><td>55.514168</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q3       </td><td>73.528938</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q4       </td><td>35.932385</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q4       </td><td> 5.825540</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q4       </td><td>14.010853</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q4       </td><td>69.825478</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q4       </td><td>73.954683</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q4       </td><td>84.961463</td></tr>
	<tr><td>A        </td><td>2020     </td><td>q4       </td><td>77.783779</td></tr>
	<tr><td>B        </td><td>2021     </td><td>q4       </td><td>39.137522</td></tr>
	<tr><td>C        </td><td>2022     </td><td>q4       </td><td>42.389005</td></tr>
</tbody>
</table>



### `spread()`


```R
saham <- data.frame(
    waktu = as.Date('2009-01-01') + 0:9,
    X = rnorm(10,0,1),
    Y = rnorm(10,0,2),
    Z = rnorm(10,0,4)
)
```


```R
saham
```


<table>
<thead><tr><th scope=col>waktu</th><th scope=col>X</th><th scope=col>Y</th><th scope=col>Z</th></tr></thead>
<tbody>
	<tr><td>2009-01-01 </td><td>-0.9984820 </td><td>-0.9431436 </td><td>-3.33749766</td></tr>
	<tr><td>2009-01-02 </td><td> 1.2059759 </td><td> 1.5118200 </td><td> 1.06892403</td></tr>
	<tr><td>2009-01-03 </td><td>-2.2298649 </td><td> 1.0133796 </td><td> 4.37434315</td></tr>
	<tr><td>2009-01-04 </td><td>-0.1377994 </td><td>-1.5819430 </td><td> 0.52897651</td></tr>
	<tr><td>2009-01-05 </td><td>-0.4644349 </td><td>-2.3425200 </td><td>-0.02850392</td></tr>
	<tr><td>2009-01-06 </td><td> 0.6431310 </td><td>-3.0102303 </td><td>-4.28047760</td></tr>
	<tr><td>2009-01-07 </td><td>-0.9540437 </td><td> 2.1494300 </td><td> 0.59964915</td></tr>
	<tr><td>2009-01-08 </td><td>-0.4403926 </td><td> 0.4593915 </td><td>-4.46067291</td></tr>
	<tr><td>2009-01-09 </td><td>-1.2862645 </td><td> 1.2761994 </td><td> 1.99288550</td></tr>
	<tr><td>2009-01-10 </td><td> 0.3102627 </td><td>-1.6672000 </td><td>10.22607936</td></tr>
</tbody>
</table>




```R
saham.gather <- gather(saham, key = saham, value = harga, X,Y,Z)
saham.gather
```


<table>
<thead><tr><th scope=col>waktu</th><th scope=col>saham</th><th scope=col>harga</th></tr></thead>
<tbody>
	<tr><td>2009-01-01 </td><td>X          </td><td>-0.99848196</td></tr>
	<tr><td>2009-01-02 </td><td>X          </td><td> 1.20597592</td></tr>
	<tr><td>2009-01-03 </td><td>X          </td><td>-2.22986494</td></tr>
	<tr><td>2009-01-04 </td><td>X          </td><td>-0.13779945</td></tr>
	<tr><td>2009-01-05 </td><td>X          </td><td>-0.46443485</td></tr>
	<tr><td>2009-01-06 </td><td>X          </td><td> 0.64313100</td></tr>
	<tr><td>2009-01-07 </td><td>X          </td><td>-0.95404366</td></tr>
	<tr><td>2009-01-08 </td><td>X          </td><td>-0.44039255</td></tr>
	<tr><td>2009-01-09 </td><td>X          </td><td>-1.28626448</td></tr>
	<tr><td>2009-01-10 </td><td>X          </td><td> 0.31026273</td></tr>
	<tr><td>2009-01-01 </td><td>Y          </td><td>-0.94314360</td></tr>
	<tr><td>2009-01-02 </td><td>Y          </td><td> 1.51182002</td></tr>
	<tr><td>2009-01-03 </td><td>Y          </td><td> 1.01337955</td></tr>
	<tr><td>2009-01-04 </td><td>Y          </td><td>-1.58194299</td></tr>
	<tr><td>2009-01-05 </td><td>Y          </td><td>-2.34251996</td></tr>
	<tr><td>2009-01-06 </td><td>Y          </td><td>-3.01023026</td></tr>
	<tr><td>2009-01-07 </td><td>Y          </td><td> 2.14943001</td></tr>
	<tr><td>2009-01-08 </td><td>Y          </td><td> 0.45939146</td></tr>
	<tr><td>2009-01-09 </td><td>Y          </td><td> 1.27619940</td></tr>
	<tr><td>2009-01-10 </td><td>Y          </td><td>-1.66720001</td></tr>
	<tr><td>2009-01-01 </td><td>Z          </td><td>-3.33749766</td></tr>
	<tr><td>2009-01-02 </td><td>Z          </td><td> 1.06892403</td></tr>
	<tr><td>2009-01-03 </td><td>Z          </td><td> 4.37434315</td></tr>
	<tr><td>2009-01-04 </td><td>Z          </td><td> 0.52897651</td></tr>
	<tr><td>2009-01-05 </td><td>Z          </td><td>-0.02850392</td></tr>
	<tr><td>2009-01-06 </td><td>Z          </td><td>-4.28047760</td></tr>
	<tr><td>2009-01-07 </td><td>Z          </td><td> 0.59964915</td></tr>
	<tr><td>2009-01-08 </td><td>Z          </td><td>-4.46067291</td></tr>
	<tr><td>2009-01-09 </td><td>Z          </td><td> 1.99288550</td></tr>
	<tr><td>2009-01-10 </td><td>Z          </td><td>10.22607936</td></tr>
</tbody>
</table>




```R
spread(data = saham.gather, key = 'saham', value = 'harga') 
# menyebar data hasil gather (kebalikan)
```


<table>
<thead><tr><th scope=col>waktu</th><th scope=col>X</th><th scope=col>Y</th><th scope=col>Z</th></tr></thead>
<tbody>
	<tr><td>2009-01-01 </td><td>-0.9984820 </td><td>-0.9431436 </td><td>-3.33749766</td></tr>
	<tr><td>2009-01-02 </td><td> 1.2059759 </td><td> 1.5118200 </td><td> 1.06892403</td></tr>
	<tr><td>2009-01-03 </td><td>-2.2298649 </td><td> 1.0133796 </td><td> 4.37434315</td></tr>
	<tr><td>2009-01-04 </td><td>-0.1377994 </td><td>-1.5819430 </td><td> 0.52897651</td></tr>
	<tr><td>2009-01-05 </td><td>-0.4644349 </td><td>-2.3425200 </td><td>-0.02850392</td></tr>
	<tr><td>2009-01-06 </td><td> 0.6431310 </td><td>-3.0102303 </td><td>-4.28047760</td></tr>
	<tr><td>2009-01-07 </td><td>-0.9540437 </td><td> 2.1494300 </td><td> 0.59964915</td></tr>
	<tr><td>2009-01-08 </td><td>-0.4403926 </td><td> 0.4593915 </td><td>-4.46067291</td></tr>
	<tr><td>2009-01-09 </td><td>-1.2862645 </td><td> 1.2761994 </td><td> 1.99288550</td></tr>
	<tr><td>2009-01-10 </td><td> 0.3102627 </td><td>-1.6672000 </td><td>10.22607936</td></tr>
</tbody>
</table>




```R
# menggunakan spread() dengan operator pipe
saham.gather %>% spread(key = 'saham', value = 'harga')
```


<table>
<thead><tr><th scope=col>waktu</th><th scope=col>X</th><th scope=col>Y</th><th scope=col>Z</th></tr></thead>
<tbody>
	<tr><td>2009-01-01 </td><td>-0.9984820 </td><td>-0.9431436 </td><td>-3.33749766</td></tr>
	<tr><td>2009-01-02 </td><td> 1.2059759 </td><td> 1.5118200 </td><td> 1.06892403</td></tr>
	<tr><td>2009-01-03 </td><td>-2.2298649 </td><td> 1.0133796 </td><td> 4.37434315</td></tr>
	<tr><td>2009-01-04 </td><td>-0.1377994 </td><td>-1.5819430 </td><td> 0.52897651</td></tr>
	<tr><td>2009-01-05 </td><td>-0.4644349 </td><td>-2.3425200 </td><td>-0.02850392</td></tr>
	<tr><td>2009-01-06 </td><td> 0.6431310 </td><td>-3.0102303 </td><td>-4.28047760</td></tr>
	<tr><td>2009-01-07 </td><td>-0.9540437 </td><td> 2.1494300 </td><td> 0.59964915</td></tr>
	<tr><td>2009-01-08 </td><td>-0.4403926 </td><td> 0.4593915 </td><td>-4.46067291</td></tr>
	<tr><td>2009-01-09 </td><td>-1.2862645 </td><td> 1.2761994 </td><td> 1.99288550</td></tr>
	<tr><td>2009-01-10 </td><td> 0.3102627 </td><td>-1.6672000 </td><td>10.22607936</td></tr>
</tbody>
</table>



### `separate()`

Memisahkan satu kolom ke banyak kolom.


```R
df <- data.frame(kol.baru = c('a.x', 'b.y', 'c.z'))
df
```


<table>
<thead><tr><th scope=col>kol.baru</th></tr></thead>
<tbody>
	<tr><td>a.x</td></tr>
	<tr><td>b.y</td></tr>
	<tr><td>c.z</td></tr>
</tbody>
</table>




```R
separate(df, kol.baru, c("ABC", "XYZ"))
```


<table>
<thead><tr><th scope=col>ABC</th><th scope=col>XYZ</th></tr></thead>
<tbody>
	<tr><td>a</td><td>x</td></tr>
	<tr><td>b</td><td>y</td></tr>
	<tr><td>c</td><td>z</td></tr>
</tbody>
</table>




```R
df <- data.frame(kol.baru = c('a-x', 'b-y', 'c-z'))
df
```


<table>
<thead><tr><th scope=col>kol.baru</th></tr></thead>
<tbody>
	<tr><td>a-x</td></tr>
	<tr><td>b-y</td></tr>
	<tr><td>c-z</td></tr>
</tbody>
</table>




```R
separate(df, kol.baru, c("ABC", "XYZ"))
```


<table>
<thead><tr><th scope=col>ABC</th><th scope=col>XYZ</th></tr></thead>
<tbody>
	<tr><td>a</td><td>x</td></tr>
	<tr><td>b</td><td>y</td></tr>
	<tr><td>c</td><td>z</td></tr>
</tbody>
</table>




```R
# Sintaks lengkapnya:
separate(data = df, col = kol.baru, c('Pertama', 'Kedua'), sep="-")
```


<table>
<thead><tr><th scope=col>Pertama</th><th scope=col>Kedua</th></tr></thead>
<tbody>
	<tr><td>a</td><td>x</td></tr>
	<tr><td>b</td><td>y</td></tr>
	<tr><td>c</td><td>z</td></tr>
</tbody>
</table>



### `unite()`

Merupakan kebalikan dari `separate()`. Digunakan untuk menggabungkan kolom.


```R
df1 <- separate(data = df, col = kol.baru, c('Pertama', 'Kedua'), sep="-")
df1
```


<table>
<thead><tr><th scope=col>Pertama</th><th scope=col>Kedua</th></tr></thead>
<tbody>
	<tr><td>a</td><td>x</td></tr>
	<tr><td>b</td><td>y</td></tr>
	<tr><td>c</td><td>z</td></tr>
</tbody>
</table>




```R
# menggabungkan jd 1 kolom
unite(df1, kol.gab.baru, Pertama, Kedua, sep = '-')
```


<table>
<thead><tr><th scope=col>kol.gab.baru</th></tr></thead>
<tbody>
	<tr><td>a-x</td></tr>
	<tr><td>b-y</td></tr>
	<tr><td>c-z</td></tr>
</tbody>
</table>
