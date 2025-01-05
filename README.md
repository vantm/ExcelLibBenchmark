# Excel Battle

Compare excel libraries

## Result

```

BenchmarkDotNet v0.13.10, Windows 10 (10.0.19045.3803/22H2/2022Update)
AMD Ryzen 7 5700X, 1 CPU, 16 logical and 8 physical cores
.NET SDK 8.0.100
  [Host]     : .NET 8.0.0 (8.0.23.53103), X64 RyuJIT AVX2
  DefaultJob : .NET 8.0.0 (8.0.23.53103), X64 RyuJIT AVX2


```
| Method        | TotalRow | Mean         | Error      | StdDev     | Gen0        | Gen1        | Gen2      | Allocated     |
|-------------- |--------- |-------------:|-----------:|-----------:|------------:|------------:|----------:|--------------:|
| **UseNpoi**       | **10**       |     **3.022 ms** |  **0.0432 ms** |  **0.0361 ms** |    **132.8125** |     **46.8750** |         **-** |     **2236.3 KB** |
| UseCloseXML   | 10       |           NA |         NA |         NA |          NA |          NA |        NA |            NA |
| UseMiniExcel  | 10       |     1.931 ms |  0.0185 ms |  0.0155 ms |     85.9375 |     39.0625 |         - |    1451.58 KB |
| UseOpenXmlSdk | 10       |     1.818 ms |  0.0131 ms |  0.0116 ms |     39.0625 |     15.6250 |         - |     653.21 KB |
| **UseNpoi**       | **1000**     |    **73.520 ms** |  **0.9001 ms** |  **0.7516 ms** |   **3750.0000** |   **2250.0000** | **1000.0000** |   **52845.48 KB** |
| UseCloseXML   | 1000     |           NA |         NA |         NA |          NA |          NA |        NA |            NA |
| UseMiniExcel  | 1000     |    77.499 ms |  0.5147 ms |  0.4814 ms |   4000.0000 |   3250.0000 |  750.0000 |   58898.42 KB |
| UseOpenXmlSdk | 1000     |    32.490 ms |  0.1603 ms |  0.1500 ms |   1187.5000 |   1062.5000 |  500.0000 |   14144.92 KB |
| **UseNpoi**       | **100000**   | **8,363.515 ms** | **27.8532 ms** | **23.2587 ms** | **263000.0000** | **109000.0000** | **4000.0000** | **4858617.91 KB** |
| UseCloseXML   | 100000   |           NA |         NA |         NA |          NA |          NA |        NA |            NA |
| UseMiniExcel  | 100000   | 9,329.880 ms | 25.4404 ms | 22.5523 ms | 332000.0000 | 129000.0000 | 6000.0000 | 5790701.05 KB |
| UseOpenXmlSdk | 100000   | 4,516.058 ms | 14.7478 ms | 13.7951 ms |  68000.0000 |  67000.0000 | 3000.0000 | 1405445.88 KB |

Benchmarks with issues:
ExcelBenchmark.UseCloseXML: DefaultJob [TotalRow=10]
ExcelBenchmark.UseCloseXML: DefaultJob [TotalRow=1000]
ExcelBenchmark.UseCloseXML: DefaultJob [TotalRow=100000]