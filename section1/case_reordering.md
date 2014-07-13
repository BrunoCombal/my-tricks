## Re-ordering tabulated values
 colleague sent me a CSV file, formatted as a rectangular array:

|       | Y 1 | Y 2 | ... | Y 180 |
| --    | :--:  | :--:  | :--: | :--: |
| X 1   |     |     |    |    |
| X 2   |     |     |    |    |
| ...   |     |     |    |    |
| X 360 |     |     |    |   &nbsp; |

I needed to export this array into a shapefile.
The classical strategy consists in having the data formatted as a CSV, with 3 fields, like:

| lon | lat | value |
| :--: | :--: | :--: |
| -179.5 | 89.5 | 1.1 |
| -178.5 | 88.5 | 0.7 |

Then use a software (gdal/ogr command line, QuantumGIS) to convert the CSV into a shapefile, a raster, etc.

Here, the difficulty is to reformat the original file.
The basic idea is the following

    lat=90
    lon=-180
    for each row
        lat = lat - 0.5
        for each column
            lon=lon+0.5
            echo $lat $lon $val

The concept is simple, but the difficulty is to get the individual values along a line.

    lat=90
    res=0.5
    cat file.txt | while read line
      do
        values=$($(echo ${line}))
        lon=-180
        for val in ${values}
        do
          echo $lat $lon $val
          lon=$(echo "scale=12; ${lon}+${res}" | bc)
        done
        lat=$(echo "scale=12;${lat} - ${res}" | bc)
    done



