## ncl-color-tables
### color tables for and by NCAR NCL

This nice collection of color tables is provided at http://ncl.ucar.edu/Document/Graphics/color_tables.shtml

The repository is for use of the tables with D3 and x3dom.
Let's think about the json which most directly maps to d3.scale
It would be d3.scale.linear().domain(cmap.domain).range(cmap.range)
If domain would be normalized to [0,1[ it would make the scale easier to use but d3.range(0,1,1/steps) has floating point problems. This means, users of the not normalized scale function would need to scale their input to scale.domain.length which is somewhat inconvenient.

d3 lib/colorbrewer uses 
var ncl_color_maps = 
{"colormap1_name": ["#rgb1", "#rgb2" ..],
 "colormap2_name": ["#rgb1", "#rgb2" ..],
 ..
 }
one could include a function to return a default scale and uses range(0,maps.name.length) for the domain.



From the source:

### Acknowledgments

Several people have contributed color tables to NCL over the years:

- Adam Phillips, NCAR
- Nicolas Barrier, Laboratoire de Physique des Oceans
- Professor Patrick J. Bartlein, Dept. of Geography, University of Oregon
- Melissa Bukovsky, NCAR
- John Fasullo, NCAR
- Oliver Fuhrer, MeteoSwiss
- Joe Grim, NCAR
- Andrea Hahmann
- Matthew Long, NCAR
- Dennis Shea, NCAR
- Emilie Vanvye, NAR
