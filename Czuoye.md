# C++大作业

### 学号：18062042

### 姓名：袁鑫杰

## **实验过程**

## 一.准备工作

由于要使用源码编译，所以需要Nebula Graph。
根据https://github.com/vesoft-inc/nebula 网站的教程，成功下载编译器。
在这期间有时会忘记一些操作，所以努力按照步骤进行。
期间也有同学的指导，最终成功下载了编译器

## 二.更改代码

原来老师给的代码为：

```
std::cout << "Got " << resp.get_rows()->size()
                      << " rows (Time spent: "
                      << resp.get_latency_in_us() << "/"
                      << dur.elapsedInUSec() << " us)\n";
```

更改后的代码为：

```
if (resp.get_rows() && !resp.get_rows()->empty()) {
    printResult(resp);
    std::cout << "Got " << resp.get_rows()->size()
              << " rows (Time spent: ";
} else if (resp.get_rows()) {
    std::cout << "Empty set (Time spent: ";
} else {
    std::cout << "Execution succeeded (Time spent: ";
}
if (resp.get_latency_in_us() < 1000 || dur.elapsedInUSec() < 1000) {
    std::cout << resp.get_latency_in_us() << "/"
              << dur.elapsedInUSec() << " us)\n";
} else if (resp.get_latency_in_us() < 1000000 || dur.elapsedInUSec() < 1000000) {
    std::cout << resp.get_latency_in_us() / 1000.0 << "/"
              << dur.elapsedInUSec() / 1000.0 << " ms)\n";
} else {
    std::cout << resp.get_latency_in_us() / 1000000.0 << "/"
              << dur.elapsedInUSec() / 1000000.0 << " s)\n";
}
std::cout << std::endl;
```
## 三.将代码上传至Github

### 1.初步新建一个REDEMA.md的文件，可以在里面编写文档

```
echo"# exmple">>REDEMA.md
```

### 2.新建并初始化仓库

```
git init
```

### 3.将所以文件添加到仓库中

```
git add
```

### 4.将本地文件夹和github仓库关联

```
git remote add origin https://github.com/yuanxinjie1208/c-dazuoye
```

### 5.

```
git pull origin master
```

### 6.提交到github上

```
git push -u origin master
```

## 四.总结

这次c++大作业对我来说是一次刺激而又富有收获的作业，在通过在这次大作业中的学习，我学会使用了git的使用方法。
虽然我觉得这次大作业的内容操作比较少，但是却富有内涵，让我学习了许多知识。比如如何去将代码发送到GitHub上，就是要先在GitHub上创立一个仓库，
然后将你所需要上传的文件添加到仓库中。我通过这次大作业，在网络上找寻了许多相关资料，既让我完成了此次作业，也丰富了自己的知识。
最后谢谢老师一个学期的陪伴，感谢您一个学期的教导。提前祝老师新年快乐。
