# CVSD_QR-Decomposition

Overview:
MIMO(multiple input, multiple output) is an antenna technology for wireless communications, the encode flow is as follows:
![image](https://github.com/J-WTY/CVSD_QR-Decomposition/assets/76650384/0c1f67f6-0006-448a-a036-809ce4d5136b)

System Model:
![image](https://github.com/J-WTY/CVSD_QR-Decomposition/assets/76650384/83f2a540-6520-4d07-92a9-d31a096029da)

Our algorithm is mainly based on the concept of modified
 Gram-Schmidt and some adjustments have been made. For each of
 resource elements, we divide the algorithm into four processes. And
 in each process, we separate several computations accordingly. As
 the picture of our algorithm flow shown below, we have PROC1,
 PROC2, PROC3, PROC4, and in each process, we have SQUARE,
 SQRT, DIVIDE, INNER_PRODUCT (not in the PROC4),
 PROJECTION.
 First, in SQUARE and SQRT, the norm of h1
 (0), h2
 (1), h3
 (2), h4
 (3),
 namely R11, R22, R33, R44, is computed for each process, respectively.
 Next, in DIVIDE, e1, e2, e3, e4 is computed for each process,
 respectively. Then, in INNER_PRODUCT, R12, R13, R14 is computed
 for PROC1, R23, R24, ŷ1 
for PROC2, and R34, ŷ3 
for PROC3. At last,
 in PROJECTION, h2
 (1), h3
 (1), h4
 (1) is computed for PROC1, h3
 (2), h4
 (3),
 ŷ2 
for PROC2, h4
 (3)for PROC3, and ŷ3 
for PROC4.
 The adjustment we make to modified Gram-Schmidt is that we
 separate the computation of 4 elements of ŷ into different stages and
 compute them earlier.

