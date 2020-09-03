Plotting links.
Links and any other type of feature can be added to circos plots by modifying the circos conf.
I have already generated a file specifying links `BlacXPsoj.Ribbons.txt`.
```
$ head BlacXPsoj.Ribbons.txt
LG1     10001265        10003407        NW_009258116.1  5484170 5485969
LG1     10040648        10041469        NW_009258116.1  5420919 5421728
LG1     10042112        10043709        NW_009258116.1  5427849 5429407
LG1     10076827        10077255        NW_009258116.1  5424862 5425272
LG1     1008577 1011804 NW_009258116.1  11302113        11304212
LG1     10113464        10115787        NW_009258116.1  5267473 5269003
LG1     10114844        10116046        NW_009258116.1  5269164 5270042
LG1     1014153 1015235 NW_009258116.1  11295267        11296929
LG1     10226828        10231181        NW_009258116.1  5335444 5336649
LG1     10231235        10235254        NW_009258116.1  5351164 5355769
```

By specifying this file in the configuration file and running circos a plot will be generated with links all of the same color.
```
$ diff circos_2Karyotype.conf circos_Black.conf
11a12
> #angle_offset* = -90
17,18c18,22
< default = 1u
< break = 1u
---
> default = 10u
> break = 10u
33a38,47
>
> <links>
> <link>
> file = BlacXPsoj.Ribbons.txt
> color         = black_a5
> radius        = 0.95r
> bezier_radius = 0.1r
> thickness     = 1
> </link>
> </links>
```
Note that there is a new links block which defines the links. I have also modified some other values to make the plot neater.
```
circos -conf circos_Black.conf
```
![Black circos of Blac x Psoj](.circos_Black.png)
