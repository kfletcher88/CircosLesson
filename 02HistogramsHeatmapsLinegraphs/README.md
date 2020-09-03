## Introuction
Typically, when plotting this type of data one will break the genome up into bins and plot a value per bin. The size of the bins is dependent on the size of the genome assembly. Instructions for this will follow soon.

## Plotting.
Files for plotting should define the scaffold, start coordinate, end coordintate and value to plot in four columns:
```
#Scaffold	Start	End	Value
Pdest_CA_v0.1-1	0	20000	0.5437
Pdest_CA_v0.1-1	10000	30000	0.5194
Pdest_CA_v0.1-1	20000	40000	0.515
Pdest_CA_v0.1-1	30000	50000	0.51205
Pdest_CA_v0.1-1	40000	60000	0.50725
Pdest_CA_v0.1-1	50000	70000	0.5032
```
Note, the first line isn't required. It is ignored as it beings with a `#`.

## Karyotype.
The Karyotype is the same as previous, but as we are using a different, more fragmented assembly, I wanted to reintroduce it. This time, the colors in the final column alternate:
```
circos -conf Karyotype1.conf
```
![Backbone Karyotype](./images/Karyotpe1.png)
You will note that we have removed the labels, to prevent overplotting. Yu can compare `Karyotype1.conf` with previous configurations files to see how.
While this plot is adequatem it might be useful to have a break in the circle. This would allow space to add labels. This can be done by adding a `<pairwise>` block:
```
<pairwise Pdest_CA_v0.1-1 Pdest_CA_v0.1-823>
spacing=20u
</pairwise>
```

```
circos -conf Karyotype2.conf
```

![Karyotype with break](./images/Karyotype2.png)

## Heatmaps.
For this example we will plot an AT content heatmap. The frequency of AT bases is defined in the 4th column of `AT.txt`.\
Heatmaps, as well as line graphs and histograms are defined within the `<plots>` block:
```
<plots>
<plot>
#<<include R0R1.conf>>
color      = spectral-9-div
type       = heatmap
file = AT.txt
r0   = 0.955r  #Defines radial position of minimum
r1   = 0.995r  #Defines radial position of maximum
min  = 0.4     #Defines minimal y value to plot
max  = 0.6     #Defined maximal y value to plot
</plot>
</plots>
```

```
circos -conf AT_Heatmap.conf
```

![AT content heatmap](./images/Heatmap.png)
