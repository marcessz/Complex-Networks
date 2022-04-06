This folder contains all the networks that we studied in our paper.

The graphs are collected from the following sources: 
* [Network Repository](http://networkrepository.com), 
* [The Colorado Index of Complex Networks (ICON)](http://networkrepository.com), 
* [NeuroData's Graph DataBase](http://openconnecto.me/graph-services/download/), 
* [KONECT - The Koblenz Network Collection](http://konect.uni-koblenz.de/), 
* [Interaction Web Database (IWDB)](https://www.nceas.ucsb.edu/interactionweb/resources.html), 
* [Transportation Networks for Research](https://github.com/bstabler/TransportationNetworks),
* [Centre for Water Systems](http://emps.exeter.ac.uk/engineering/research/cws/resources/benchmarks/)


The edge lists can be loaded with this function: 
```python

from glob import glob
import os
import networkx as nx

def network_import_nx(directory):
    paths=glob(os.path.join(directory,'*.*'))
    file_names=os.listdir(directory)
    graphs_and_names=[]
    for index,file in enumerate(paths):
        edge_data=open(file,'r', encoding = "ISO-8859-1")
        edge_lines=edge_data.readlines()
        edge_data.close()
        if '.inp' not in file_names[index]:
            edge_list=[' '.join(str.split(lines)[0:2]) for lines in edge_lines]
        else:
            edge_list=[' '.join(str.split(lines)[1:3]) for lines in edge_lines]
            
        graphs_and_names += [(file_names[index], nx.convert_node_labels_to_integers(nx.parse_edgelist(edge_list, comments='%')))]
        
    return(graphs_and_names)
```
   
For example:
```python
chems_nx = network_import_nx("./Cheminformatics")
```


The adjacency matrices (some of the food webs) can be imported with this function:

```python

def network_matrix_import(directory):
    def g_from_mat(matrix_list_of_list):
        m=np.array(matrix_list_of_list)
        dim=list(m.shape)
        edges=[]
        index_of_horizontal_nodes=list(range(dim[0],np.sum(dim)))
        for i in range(dim[0]):
            for j in range(dim[1]):
                if m[i][j] > 0:
                    edges +=[(i,index_of_horizontal_nodes[j])]
        g=nx.Graph()  
        g.add_edges_from(edges)
        return(g)

    paths=glob(os.path.join(directory,'*.*'))
    file_names=os.listdir(directory)
    graphs_and_names=[]
    for index,file in enumerate(paths):
        matrix_data=open(file,'r')
        matrix_lines=matrix_data.readlines()
        matrix_data.close()
        matrix=[str.split(lines) for lines in matrix_lines]
        array=np.array(matrix).astype(np.float)
        graphs_and_names += [(file_names[index], g_from_mat(array))]
    return(graphs_and_names)
```

Food network can be imported as follows:
```python
food = network_import_nx("./foodweb/edgelist")
food += network_matrix_import("./foodweb/adj")
```
