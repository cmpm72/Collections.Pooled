``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=3.0.100-preview-010184
  [Host] : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT
  Core   : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT

Job=Core  Runtime=Core  InvocationCount=1  
UnrollFactor=1  

```
|              Method |     N |       Mean |     Error |    StdDev |     Median | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|-------------------- |------ |-----------:|----------:|----------:|-----------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|      **ListRemove_Int** |  **3000** |   **2.696 ms** | **0.0758 ms** | **0.2186 ms** |   **2.611 ms** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
|    PooledRemove_Int |  3000 |   2.630 ms | 0.0469 ms | 0.0626 ms |   2.633 ms |  0.98 |    0.09 |           - |           - |           - |                   - |
|   ListRemove_String |  3000 |  23.502 ms | 0.4683 ms | 0.9022 ms |  23.483 ms |  8.64 |    0.83 |           - |           - |           - |                   - |
| PooledRemove_String |  3000 |  23.471 ms | 0.4502 ms | 0.5694 ms |  23.478 ms |  8.76 |    0.86 |           - |           - |           - |                   - |
|                     |       |            |           |           |            |       |         |             |             |             |                     |
|      **ListRemove_Int** | **10000** |  **25.591 ms** | **0.4891 ms** | **0.5632 ms** |  **25.528 ms** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
|    PooledRemove_Int | 10000 |  25.624 ms | 0.4670 ms | 0.3899 ms |  25.672 ms |  1.00 |    0.03 |           - |           - |           - |                   - |
|   ListRemove_String | 10000 | 252.440 ms | 3.0045 ms | 2.8104 ms | 252.206 ms |  9.85 |    0.24 |           - |           - |           - |                   - |
| PooledRemove_String | 10000 | 256.044 ms | 2.5814 ms | 2.4146 ms | 255.403 ms |  9.99 |    0.25 |           - |           - |           - |                   - |
