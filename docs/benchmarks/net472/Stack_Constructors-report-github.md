``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3324.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3324.0

Job=Clr  Runtime=Clr  

```
|                       Method |      N |   Type |           Mean |        Error |       StdDev | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|----------------------------- |------- |------- |---------------:|-------------:|-------------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|  **StackICollectionConstructor** |   **1000** |    **Int** |       **258.8 us** |     **4.292 us** |     **4.014 us** |  **1.00** |    **0.00** |   **1290.0391** |           **-** |           **-** |          **3968.97 KB** |
| PooledICollectionConstructor |   1000 |    Int |     1,072.6 us |     7.363 us |     6.149 us |  4.15 |    0.06 |     17.5781 |           - |           - |            54.69 KB |
|  StackIEnumerableConstructor |   1000 |    Int |     7,514.1 us |    61.807 us |    57.815 us | 29.04 |    0.48 |   2687.5000 |           - |           - |          8274.57 KB |
| PooledIEnumerableConstructor |   1000 |    Int |     9,732.3 us |    76.893 us |    68.164 us | 37.60 |    0.65 |     46.8750 |           - |           - |            148.5 KB |
|                              |        |        |                |              |              |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |   **1000** | **String** |       **735.3 us** |     **9.098 us** |     **8.511 us** |  **1.00** |    **0.00** |   **2556.6406** |           **-** |           **-** |          **7876.88 KB** |
| PooledICollectionConstructor |   1000 | String |     2,737.9 us |    26.384 us |    24.680 us |  3.72 |    0.06 |     15.6250 |           - |           - |            54.69 KB |
|  StackIEnumerableConstructor |   1000 | String |    12,878.5 us |    92.945 us |    86.941 us | 17.52 |    0.25 |   5281.2500 |           - |           - |         16271.19 KB |
| PooledIEnumerableConstructor |   1000 | String |    18,857.1 us |   177.109 us |   165.668 us | 25.65 |    0.37 |     31.2500 |           - |           - |           156.25 KB |
|                              |        |        |                |              |              |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |  **10000** |    **Int** |     **2,591.8 us** |    **28.661 us** |    **26.810 us** |  **1.00** |    **0.00** |  **12656.2500** |           **-** |           **-** |         **39210.66 KB** |
| PooledICollectionConstructor |  10000 |    Int |    14,488.7 us |    92.115 us |    86.165 us |  5.59 |    0.08 |     15.6250 |           - |           - |            54.75 KB |
|  StackIEnumerableConstructor |  10000 |    Int |    75,263.4 us |   757.745 us |   708.795 us | 29.04 |    0.39 |  41571.4286 |           - |           - |        128520.07 KB |
| PooledIEnumerableConstructor |  10000 |    Int |   104,666.7 us | 1,268.889 us | 1,186.920 us | 40.39 |    0.71 |           - |           - |           - |            148.8 KB |
|                              |        |        |                |              |              |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |  **10000** | **String** |     **7,202.6 us** |    **33.474 us** |    **26.135 us** |  **1.00** |    **0.00** |  **24984.3750** |           **-** |           **-** |         **78371.88 KB** |
| PooledICollectionConstructor |  10000 | String |    36,633.8 us |   287.739 us |   269.151 us |  5.09 |    0.04 |           - |           - |           - |            54.86 KB |
|  StackIEnumerableConstructor |  10000 | String |   189,430.1 us | 2,355.470 us | 2,203.308 us | 26.29 |    0.31 |  41333.3333 |  41333.3333 |  41333.3333 |        256378.94 KB |
| PooledIEnumerableConstructor |  10000 | String |   211,815.7 us | 1,580.451 us | 1,478.355 us | 29.41 |    0.24 |           - |           - |           - |           157.33 KB |
|                              |        |        |                |              |              |       |         |             |             |             |                     |
|  **StackICollectionConstructor** | **100000** |    **Int** |    **63,639.2 us** |   **932.899 us** |   **826.991 us** |  **1.00** |    **0.00** |  **23375.0000** |  **23125.0000** |  **23125.0000** |        **390890.45 KB** |
| PooledICollectionConstructor | 100000 |    Int |   122,104.7 us |   696.091 us |   651.124 us |  1.92 |    0.03 |           - |           - |           - |            55.21 KB |
|  StackIEnumerableConstructor | 100000 |    Int |   848,638.6 us | 5,291.542 us | 4,949.711 us | 13.34 |    0.21 | 187000.0000 | 145000.0000 | 145000.0000 |       1027380.69 KB |
| PooledIEnumerableConstructor | 100000 |    Int |   959,725.6 us | 9,165.078 us | 7,653.255 us | 15.09 |    0.23 |           - |           - |           - |              152 KB |
|                              |        |        |                |              |              |       |         |             |             |             |                     |
|  **StackICollectionConstructor** | **100000** | **String** |   **481,057.3 us** | **3,011.940 us** | **2,670.007 us** |  **1.00** |    **0.00** |  **27000.0000** |  **27000.0000** |  **27000.0000** |        **781546.76 KB** |
| PooledICollectionConstructor | 100000 | String |   314,192.2 us |   837.710 us |   654.029 us |  0.65 |    0.00 |           - |           - |           - |               56 KB |
|  StackIEnumerableConstructor | 100000 | String | 1,688,251.5 us | 5,884.450 us | 5,216.412 us |  3.51 |    0.02 | 327000.0000 | 285000.0000 | 284000.0000 |       2053283.08 KB |
| PooledIEnumerableConstructor | 100000 | String | 1,931,643.2 us | 5,016.073 us | 4,446.618 us |  4.02 |    0.02 |           - |           - |           - |              160 KB |
