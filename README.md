# Maximum Defective Clique Computation

This project implements several algorithms for exact maximum k-defective clique computation

## Compilation

```sh
$ make clean
$ make
```
It generates an executable `kDC`.

## Execution

To run the program, use the following command:
```sh
$ ./kDC -t -g {path_to_graph} -k {k_value}
```

An example of computing the maximum 3-defective clique for the dataset CA-GrQc is as follows
```sh
$ ./kDC -t -g datasets/CA-GrQc -k 3
```

### Parameters:
-   `-g {path_to_graph}`: Specifies the path to the input graph file.
-   `-k {k_value}`: Defines the value k.
-   `-t`: Whether use the two-stage framework or not
-   `-b`: This is optional. Once set, the graph will be loaded from the two binary files (see below for more information on the data format.

### Different variants of the algorithm can be run as follows.

#### 1. Run the algorithm kDC2+RR3

```sh
$ ./kDC -t -g {path_to_graph} -k {k_value}
```

#### 2. Run the algorithm kDC+R

```sh
$ ./kDC -g {path_to_graph} -k {k_value}
```

#### 3. Run the algorithms kDC-two and kDC

Comment out #define _RR_OPT_ in Utility.h, and then recompile the code

Run kDC-two
```sh
$ ./kDC -t -g {path_to_graph} -k {k_value}
```

Run kDC
```sh
$ ./kDC -g {path_to_graph} -k {k_value}
```

## Data format
Two data formats are supported. The default data format is "edges.txt", which contains a list of undirected edges represented as vertex pairs. The first line contains two numbers n and m, representing the number of vertices and the number of undirected edges, respectively. Note that, the vertex ids must be between 0 and n-1.

## Get datasets
Real-world graphs collection: http://lcs.ios.ac.cn/~caisw/Resource/realworld%20graphs.tar.gz

Facebook graphs collection: https://networkrepository.com/socfb.php
