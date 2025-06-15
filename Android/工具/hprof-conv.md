hprof-conv 是 Android 内存分析流程的桥梁, 解决了原生堆转储格式与标准 Java 工具的兼容性问题。转换后的堆转储文件可以通过标准Java内存分析工具打开。

### 使用
```bash
hprof-conv heap-original.hprof heap-converted.hprof
```