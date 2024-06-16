# CVSD_QR-Decomposition

Overview:
MIMO(multiple input, multiple output) is an antenna technology for wireless communications, the encode flow is as follows:
![image](https://github.com/J-WTY/CVSD_QR-Decomposition/assets/76650384/0c1f67f6-0006-448a-a036-809ce4d5136b)


 In this project, we hope to achieve the part of QR decomposition
 Our algorithm is mainly based on the concept of modified Gram-Schmidt and some adjustments have been made. For each of resource elements, we divide the algorithm into four processes. And in each process, we separate several computations accordingly. As
 the picture of our algorithm flow shown below, we have PROC1, PROC2, PROC3, PROC4, and in each process, we have SQUARE, SQRT, DIVIDE, INNER_PRODUCT (not in the PROC4), PROJECTION.
 
 First, in SQUARE and SQRT, the norm of **h<sub>1</sub><sup>0</sup>**, **h<sub>2</sub><sup>1</sup>**, **h<sub>3</sub><sup>2</sup>**, **h<sub>4</sub><sup>3</sup>**,
 namely **R<sub>11</sub>**, **R<sub>22</sub>**, **R<sub>33</sub>**, **R<sub>44</sub>**, is computed for each process, respectively.
 
 Next, in DIVIDE, **e<sub>1</sub>**, **e<sub>2</sub>**, **e<sub>3</sub>**, **e<sub>4</sub>** is computed for each process,
 respectively. Then, in INNER_PRODUCT, **R<sub>12</sub>**, **R<sub>13</sub>**, **R<sub>14</sub>** is computed
 for PROC1, **R<sub>23</sub>**, **R<sub>24</sub>**, **ŷ<sub>1</sub>** for PROC2, and **R<sub>34</sub>**, **ŷ<sub>3</sub>** for PROC3. 
 At last,
 in PROJECTION, **h<sub>2</sub><sup>1</sup>**, **h<sub>3</sub><sup>1</sup>**, **h<sub>4</sub><sup>1</sup>** is computed for PROC1, **h<sub>3</sub><sup>2</sup>**, **h<sub>4</sub><sup>3</sup>**,
 ŷ2 
 for PROC2, **h<sub>4</sub><sup>3</sup>** for PROC3, and **ŷ<sub>3</sub>**
 for PROC4.
 The adjustment we make to modified Gram-Schmidt is that we
 separate the computation of 4 elements of ŷ into different stages and
 compute them earlier.

![image](https://github.com/J-WTY/CVSD_QR-Decomposition/assets/76650384/1c87f718-2e4b-41e9-b085-3e9255a8c09f)
