# MethodHandle 
来源《深入理解Java虚拟机：JVM高级特性与最佳实践》

有Method Handle之后，Java语言拥有类似函数指针或委托的方法别名工具，和反射非常相似，但还是有以下区别：

# 1
  MethodHandle 和 Reflection 机制都是在模拟方法调用，但Reflection是模拟Java代码层次的方法调用，而MethodHandle是模拟字节码层次的方法调用。
  
# 2
  反射对象比MethodHandle对象包含更多信息，前者是Java一端的全面映像。通俗的说，Reflection是重量级，MethodHandle是轻量级

# 3
  MethodHandle是对字节码的方法指令调用的模拟，理论上可以享受到虚拟机在这方面做的各种优化（比如内联）
  
# 4
  Reflection API只为Java语言服务，而MethodHandl则设计成可服务于所有Java虚拟机上的语言
  
# 经实验：
  https://github.com/ruanzf/study/tree/master/src/main/java/com/study/methodhandle
  
  在500（并非定值）次调用内，MethodHandle比反射更快，之后是反射调用更快
  上百、千万级别的调用后，两者耗时相关不大，MethodHandle并没有更快。与直接方法调用也不会有数量级的差距
  当然，还是直接方法调用最快
