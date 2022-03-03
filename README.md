# tesspy


## Introduction 
A package for urban and suburban area tessellations. 

## Installation
You can install ``tesspy`` from PyPI using pip (**Not Recommended**):
```
pip install tesspy
```

and from conda:
```
conda install -c conda-forge tesspy
```



## Creating a new environment for tesspy

`tesspy` depends on `geopandas`, which could make the installation sometimes tricky because of the conflicts with the current packages. Therefore, we recommend creating a new clean environment and installing the dependencies from the conda-forge channel.


Create a new environment:
```shell
conda create -n tesspy_env -c conda-forge
```

Activate this environment:
```shell
conda activate tesspy_env
```

Install tesspy from conda-forge channel:
```shell
conda install -c conda-forge tesspy
```


## Documentation
The official documentation is hosted on **[ReadTheDocs](https://tesspy.readthedocs.io)**


## Examples
The city of "Frankfurt am Main" in Germany is used to showcase different tessellation methods. This is how a tessellation objest is built and diffrent methods are called. For the tessellation methods which are based on Points of Interests (adaptive squares, Voronoi polygons, and City Blocks), we use `amenty` data from the OpenStreetMap.
```python
from tesspy import Tessellation
ffm= Tessellation('Frankfurt am Main')
```


### Squares 
```python
ffm_sqruares = ffm.squares(resolution=15)
```
<p align="left">
  <img src="docs/readme_pics/Squares.png">
</p>

![Squares_tessellation](docs/readme_pics/https://github.com/siavash-saki/tesspy/blob/7a6f6bc8bab709b14c64827ae875d0dc8abcd332/docs/readme_pics/Squares.png.png)


### Hexagons
```python
ffm_hex_8 = ffm.hexagons(resolution=8)
```
![hexagon_tessellation](docs/readme_pics/Hexagons.png)
### Adaptive Squares
```python
ffm_asq = ffm.adaptive_squares(start_resolution=14, threshold=100, poi_categories=['amenity'])
```
![hexagon_tessellation](docs/readme_pics/Adaptive_Squares.png)

### Voronoi Polygons
```python
ffm_voronoi = ffm.voronoi(poi_categories=['amenity'], n_polygons=500)
```
![Voronoi_tessellation](docs/readme_pics/Voronoi.png)

### City Blocks
```python
ffm_city_blocks = ffm.city_blocks(n_polygons=500)
```
![city_blocks_tessellation](docs/readme_pics/CB.png)

## Contributing to tesspy
Contribution is welcome!

## Acknowledgements
`tesspy` is the result of the research project [ClusterMobil](https://www.frankfurt-university.de/de/hochschule/fachbereich-1-architektur-bauingenieurwesen-geomatik/forschungsinstitut-ffin/fachgruppen-des-ffin/fg-neue-mobilitat/relut/forschungsprojekte-relut/clustermobil/) conducted by the [Research Lab for Urban Transport](https://www.frankfurt-university.de/en/about-us/faculty-1-architecture-civil-engineering-geomatics/research-institute-ffin/specialist-groups-of-the-ffin/specialist-group-new-mobility/relut/). This research project is funded by the state of Hesse and [HOLM](https://frankfurt-holm.de/) funding under the “Innovations in Logistics and Mobility” measure of the Hessian Ministry of Economics, Energy, Transport and Housing. [HA Project No.: 1017/21-19]

