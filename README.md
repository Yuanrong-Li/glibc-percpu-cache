# glibc percpu cache内存管理机制
**项目名称**

glibc percpu cache内存管理机制

**导师信息**：

姓名：李清清

邮箱：liqingqing3@huawei.com

**难度**：中

**分类**：系统调试/支撑库的设计

**题目要求**：

1. 功能需求：基于openEuler 2403LTS sp1操作系统开发glibc2.38版本的内存管理percpu cache实现。
   背景：glibc实现了perthread的tcache管理，该机制每个线程会申请一个thread cache作为缓存，但实际应用场景会存在线程数比实际cpu核数使用较多的情况，这种场景下的内存申请的局部性并不是最优状态。当前linux内核提供了rseq机制，使得用户态可以使用类似内核态percpu的功能，可参考google/tcmalloc实现glibc ptmalloc的类似功能。
   目标：本需求目标实现一套基于glibc的ptmalloc内存管理算法percpu tcache缓存机制，x86/arm架构优先。
2. 性能需求：基于mysql整机场景，percpu相较perthread缓存的目标性能提升5%。
   如上功能需求为必选，性能需求基于mysql场景提升5%以上。通过综合考核功能完成度，编码实现，以及性能提升幅度综合打分评估。

**License**

MulanPSL-2.0

**参考资料**

参考资料1：google/tcmalloc实现 https://github.com/google/tcmalloc

参考资料2：google/tcmalloc实现对应论文 https://www.usenix.org/conference/osdi21/presentation/hunter

参考资料3：“Harvesting Memory-bound CPU Stall Cycles in Software with MSH” https://www.usenix.org/conference/osdi24/presentation/luo
