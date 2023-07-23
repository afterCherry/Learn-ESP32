- Component has many function directory.
- REQUIRES: what component library do we want to add?
- ESP-IDF/Components which we would include in REQUIRES
- External CMakefile.txt in the root
```C++
set(EXTRA_COMPONENT_DIRS C:/projects/learnEsp32/esp32-course/_5_working_with_c/5_5_external_components/calc)
```

```C++
idf.py fullclean

idf.py build

idf.py flash monitor
```

 ⚠️
- CMakeLists.txt refers to relevant path of file, so "include" will have effect
- See and analyze the complaination carefully






# Words
- backslash \ forwardslash /
- unseemic 不雅观的
- complain 抱怨
- capability
- subdirectory
- miniature 微型
