chunk by chunk
```C++
typedef struct chunk_payload_t
{
    uint8_t *buffer;
    int buffer_index;
} chunk_payload_t;
```

# Words
- Chunking data（数据分块）是一种将大型数据集或数据流分割成更小的块或片段的过程。这个过程通常用于处理大型数据，以提高处理效率、减少内存使用和优化网络传输。
