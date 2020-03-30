# nniefacelib

nniefacelib是一个在海思35xx系列芯片上运行的人脸算法库，目前集成了mobilefacenet和retinaface。
后期也会融合一些其他经典的模型，目的也是总结经验，让更多人早日脱离苦海。

**目前只在3516DV300上进行了测试。鉴于很多同学在其他型号上进行测试失败的情况，做一下统一说明，编译错误显示，
不同型号的sample代码略有不同，有必要的话需要自己移植核心源码，仿照着SDK的源码进行移植，应该问题不大**

### 入坑指南
因为代码这部分并没有对NNIE进行重构，是纯C代码，所以看起来会比较晦涩，为此，我们可以将算法模块直接编译成
动态链接库供上层进行调用。

```bash
make -f Makefile.Shared
```

为了方便测试，也可以直接编译成可执行文件
```bash
make -f Makefile.Debug
```

### 模型转换
模型转换其实是一个大坑，也可以说是一个玄学，如何转换？如何让速度更快？目前也是在总结一些经验，
我也会在知乎上更新一些关于模型转换的一些方法  
[海思NNIE之Mobilefacenet量化部署](https://zhuanlan.zhihu.com/p/107548509)  
[海思NNIE之RetinaFace量化部署](https://zhuanlan.zhihu.com/p/111399987)  
[海思NNIE之PFPLD训练与量化](https://zhuanlan.zhihu.com/p/120376337)
### TODO
- [x] mobilefacenet
- [x] retinaface
- [x] [PFLD(更偏向角度、姿态检测)，会公布训练代码](https://github.com/hanson-young/nniefacelib/blob/master/PFPLD/README.md)
- [ ] 人脸质量（模糊度检测）
- [ ] RGB活体检测（保佑我早日中paper吧）
