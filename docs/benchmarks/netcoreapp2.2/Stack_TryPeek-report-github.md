``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=3.0.100-preview-010184
  [Host] : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT
  Core   : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT

Job=Core  Runtime=Core  InvocationCount=1  
UnrollFactor=1  

```
|        Method |       N |   Type | EmptyStack |        Mean |       Error |        StdDev |      Median | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|-------------- |-------- |------- |----------- |------------:|------------:|--------------:|------------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|  **StackTryPeek** |   **10000** |    **Int** |      **False** |    **70.81 us** |   **3.7419 us** |    **10.6153 us** |    **73.94 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledTryPeek |   10000 |    Int |      False |    68.31 us |   4.2100 us |    11.7357 us |    65.93 us |  0.99 |    0.24 |           - |           - |           - |                   - |
|               |         |        |            |             |             |               |             |       |         |             |             |             |                     |
|  **StackTryPeek** |   **10000** |    **Int** |       **True** |    **49.65 us** |   **0.0542 us** |     **0.0507 us** |    **49.61 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledTryPeek |   10000 |    Int |       True |    55.49 us |   3.0806 us |     8.6384 us |    49.72 us |  1.14 |    0.18 |           - |           - |           - |                   - |
|               |         |        |            |             |             |               |             |       |         |             |             |             |                     |
|  **StackTryPeek** |   **10000** | **String** |      **False** |    **46.86 us** |   **0.8069 us** |     **0.6738 us** |    **47.30 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledTryPeek |   10000 | String |      False |    75.96 us |   5.6803 us |    16.5698 us |    74.83 us |  1.57 |    0.42 |           - |           - |           - |                   - |
|               |         |        |            |             |             |               |             |       |         |             |             |             |                     |
|  **StackTryPeek** |   **10000** | **String** |       **True** |    **28.44 us** |   **0.0450 us** |     **0.0376 us** |    **28.42 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledTryPeek |   10000 | String |       True |    49.66 us |   0.0729 us |     0.0646 us |    49.66 us |  1.75 |    0.00 |           - |           - |           - |                   - |
|               |         |        |            |             |             |               |             |       |         |             |             |             |                     |
|  **StackTryPeek** |  **100000** |    **Int** |      **False** |   **619.16 us** |  **17.3660 us** |    **49.2645 us** |   **596.12 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledTryPeek |  100000 |    Int |      False |   620.49 us |  12.9043 us |    33.0787 us |   609.23 us |  1.01 |    0.10 |           - |           - |           - |                   - |
|               |         |        |            |             |             |               |             |       |         |             |             |             |                     |
|  **StackTryPeek** |  **100000** |    **Int** |       **True** |   **504.90 us** |  **12.8850 us** |    **12.0526 us** |   **508.23 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledTryPeek |  100000 |    Int |       True |   512.97 us |  10.1755 us |    18.3485 us |   507.95 us |  1.01 |    0.04 |           - |           - |           - |                   - |
|               |         |        |            |             |             |               |             |       |         |             |             |             |                     |
|  **StackTryPeek** |  **100000** | **String** |      **False** |   **461.14 us** |   **8.7866 us** |     **9.0232 us** |   **456.59 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledTryPeek |  100000 | String |      False |   607.76 us |  21.8786 us |    20.4653 us |   598.10 us |  1.32 |    0.06 |           - |           - |           - |                   - |
|               |         |        |            |             |             |               |             |       |         |             |             |             |                     |
|  **StackTryPeek** |  **100000** | **String** |       **True** |   **273.77 us** |   **6.5994 us** |     **9.2514 us** |   **274.04 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledTryPeek |  100000 | String |       True |   476.00 us |   8.9172 us |     9.1573 us |   479.23 us |  1.74 |    0.06 |           - |           - |           - |                   - |
|               |         |        |            |             |             |               |             |       |         |             |             |             |                     |
|  **StackTryPeek** | **1000000** |    **Int** |      **False** | **2,297.65 us** | **315.1847 us** |   **841.2918 us** | **2,595.60 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledTryPeek | 1000000 |    Int |      False | 2,167.01 us | 282.7427 us |   749.7936 us | 2,466.70 us |  0.95 |    0.11 |           - |           - |           - |                   - |
|               |         |        |            |             |             |               |             |       |         |             |             |             |                     |
|  **StackTryPeek** | **1000000** |    **Int** |       **True** | **3,373.16 us** | **671.6372 us** | **1,980.3376 us** | **2,652.74 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledTryPeek | 1000000 |    Int |       True | 3,400.75 us | 605.7062 us | 1,785.9383 us | 2,877.71 us |  1.11 |    0.49 |           - |           - |           - |                   - |
|               |         |        |            |             |             |               |             |       |         |             |             |             |                     |
|  **StackTryPeek** | **1000000** | **String** |      **False** | **3,510.69 us** |  **52.1640 us** |    **48.7943 us** | **3,485.00 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledTryPeek | 1000000 | String |      False | 4,121.89 us |  81.0317 us |   102.4792 us | 4,060.93 us |  1.18 |    0.04 |           - |           - |           - |                   - |
|               |         |        |            |             |             |               |             |       |         |             |             |             |                     |
|  **StackTryPeek** | **1000000** | **String** |       **True** | **1,403.65 us** | **172.3244 us** |   **508.1025 us** | **1,138.87 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledTryPeek | 1000000 | String |       True | 1,493.78 us | 156.4176 us |   461.2008 us | 1,140.73 us |  1.11 |    0.32 |           - |           - |           - |                   - |
