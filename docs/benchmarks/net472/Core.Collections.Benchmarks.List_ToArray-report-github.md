``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.195 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3260.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3260.0

Job=Clr  Runtime=Clr  

```
|        Method |      N |       Mean |     Error |    StdDev | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|-------------- |------- |-----------:|----------:|----------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|   **ListToArray** |   **1000** |   **2.228 ms** | **0.0114 ms** | **0.0107 ms** |  **1.00** |    **0.00** |  **12785.1563** |           **-** |           **-** |            **38.41 MB** |
| PooledToArray |   1000 |   3.545 ms | 0.0183 ms | 0.0172 ms |  1.59 |    0.01 |  12785.1563 |           - |           - |            38.41 MB |
|               |        |            |           |           |       |         |             |             |             |                     |
|   **ListToArray** |  **10000** |  **25.163 ms** | **0.1497 ms** | **0.1400 ms** |  **1.00** |    **0.00** | **126562.5000** |           **-** |           **-** |           **381.93 MB** |
| PooledToArray |  10000 |  32.800 ms | 0.1228 ms | 0.1088 ms |  1.30 |    0.01 | 126533.3333 |           - |           - |           381.93 MB |
|               |        |            |           |           |       |         |             |             |             |                     |
|   **ListToArray** | **100000** | **702.418 ms** | **9.2714 ms** | **8.6725 ms** |  **1.00** |    **0.00** | **803000.0000** | **802000.0000** | **802000.0000** |          **3814.93 MB** |
| PooledToArray | 100000 | 923.157 ms | 4.2702 ms | 3.9943 ms |  1.31 |    0.02 | 912000.0000 | 909000.0000 | 909000.0000 |          3814.93 MB |