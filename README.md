G1 collector.
Improved Concurrent Mark Sweep garbage collector. It is suitable for very large JVMs (4GB and above) running I/O intensive applications such as web applications which are sensitive to response times.
Pros:
1. Less GC pause times for large JVMs.
2. Application doesn't freeze during mark and sweep phases.
3. Heap memory gets compacted during collection phase and not after(on-the-go).
4. Uses multiple cores, hence parallel.
Cons:
1. Conitnuous tuning required for maintaining GC performance.
3. Tuning parameters that worked for test environments may underperform in production.
4. Incurrs 5 - 10% resource overhead.
Tip:
CMS collector performs better than G1 for small to medium(512MB - 4GB) I/O intensive applications.

Parallel collector.
Improved serial collector that uses all available CPU cores for garbage collection. Suitable for very large JVMs(6GB and above) running CPU intensive applications where throughput is of significance and large GC pause times are accecptable.
Pros:
1. Suitable for running batched workloads.
2. Easy to use as minimal tuning is required. 
3. Minimum resource overhead usage.
Cons:
1. Application freezes during entire GC process.
2. Not suitable for responsive applications.
Tip:
Serial collector is best suited for containerized applications/micro services with small JVM footprint(< 512MB and < 2 vCPU). 
