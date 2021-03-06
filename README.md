# Complex-Networks
Supplementary data for the paper *Data-driven Analysis of Complex Networks and their Model-generated Counterparts* - M. Nagy, R. Molontay (2019)
## How to Cite
```
@article{nagy2018data,
  title={Data-driven Analysis of Complex Networks and their Model-generated Counterparts},
  author={Nagy, Marcell and Molontay, Roland},
  journal={arXiv preprint arXiv:1810.08498},
  url={https://arxiv.org/abs/1810.08498},
  year={2018}
}
```


## Source
The graphs are collected from the following sources: 
* [Network Repository](http://networkrepository.com), 
* [The Colorado Index of Complex Networks (ICON)](http://networkrepository.com), 
* [NeuroData's Graph DataBase](http://openconnecto.me/graph-services/download/), 
* [KONECT - The Koblenz Network Collection](http://konect.uni-koblenz.de/), 
* [Interaction Web Database (IWDB)](https://www.nceas.ucsb.edu/interactionweb/resources.html), 
* [Transportation Networks for Research](https://github.com/bstabler/TransportationNetworks),
* [Centre for Water Systems](http://emps.exeter.ac.uk/engineering/research/cws/resources/benchmarks/)

## Summary of Networks


| Domain | Description | Range of network size | Number of networks |
|-----------------|--------------------------------------------------------------|:---------------------------------------:|:--------------:|
| Brain | Human and animal connectomes | 50-2,995 <br> (avg: 946) | 100 |
| Cheminformatics | Protein-protein (enzyme) interaction networks | 44-125 <br> (avg: 55) | 100 |
| Food | What-eats-what, consumer-resource networks | 19-1,500 <br> (avg: 118) | 100 |
| Infrastructural | Transportation (metro, bus, road, airline) and distribution networks (power and water) | 39-40K <br> (avg: 4,562) | 68 |
| Social | Facebook, Twitter and collaboration networks | 16-56K <br> (avg: 5,824) | 100 |
| Web | Pieces of the World Wide Web | 146-16K <br> (avg: 4,488) | 14 |



## Graph Measurements
The [data folder](./data) contains a spreadsheet that contains the calculated metrics of the 482 real networks. 

The calculated metrics are the following:
- assortativity, 
- average clustering coefficient, 
- average degree, 
- average path length, 
- density, 
- global clustering coefficient, 
- four interval degree probabilities introduced in [this paper](https://ieeexplore.ieee.org/abstract/document/7000748),
- largest eigenvector centrality, 
- maximum degree, 
- maximum edge betweenness centrality,
- maximum vertex betweenness centrality,
- number of edges,
- number of nodes, 
- pseudo diameter

A detailed description of the dataset and the metrics can be found in [*Data-driven Analysis of Complex Networks and their Model-generated Counterparts*](https://arxiv.org/abs/1810.08498)
