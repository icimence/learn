

<p align="center" style="color:blue">
  <a href="https://github.com/icimence/learn" target="_blank">
    <h2 align="center">
        网站内容不断更新中...
    </h2>
  </a>
</p>
<!-- <p>
  <br>
</p> -->

---
# **网站介绍**
---
## **声明**
> [!TIP]
> 本站希望将本人在针对各个企业面试的过程中的感受以及学习的资料记录下来，希望能让自己留下更深刻的印象并且方便之后的查阅工作，同时方便学弟学妹进行一定的参考来减小一定的工作量。
>
> 
>
> 旨在为准备各种大厂面试的人提供一定的技术支持，主要面对Java岗，欢迎大家对其他内容进行进一步的补充，项目已经发布在GitHub中
>
> 
>
> 方便自己也方便他人。网站内容会保持**持续更新**，欢迎收藏品鉴！

## **注意事项**

> [!ATTENTION|style:flat]
>
> 本站的所有内容都是由本人理解以及整理得来的，本人水平有限，难免出现纰漏，希望阅读网站的各位对不恰当或者是错误之处随时进行批评指正，[点击链接](https://github.com/icimence/learn)创建issue进行反馈。同时若本站任何内容构成侵权或者您不希望被引用请尽快联系我！

---
# **本站内容地图**
---

暂无，完成度一定之后会定期更新地图

---
# **知识大梳理**

---
> [!NOTE]
> 本站目前仅仅开始整理Java的相关资料，希望进行广度优先的学习，所以可能并没有深度，会随时更新这个模块，目前已经有的内容是
>
> - **Java相关知识**
>
>  - ~~**MySQL**~~
>  - ~~**操作系统**~~
>  - ~~**分布式**~~
>  - ~~**高性能开发**~~
>  - ~~**高可用**~~
>

后续本站也会持续更新和增加更多方向面试频繁考点

---
# **Java相关知识**
---
## **Java语言特性**

Java在创立之初宣传的是"Write Once, Run Anywhere"，显然这个目标是达成了的，我们需要知道是怎样达成的以及这其中的细节。在这里就不得不强调几个核心概念，**JVM，JDK，JRE，字节码**

### JVM，JDK，JRE

Java虚拟机是运行Java字节码的虚拟机，针对不同的操作系统有不同的JVM提供实现相同的字节码在不同的操作系统环境下可以达到相同的效果，这也是Java的宣传标语的关键所在，需要注意的是JVM并不是一个操作系统对应一个的，其实JVM只是一种规范，任何组织和个人都可以开发属于自己的JVM，规范可以在Oracle的官网上找到。

JDK即Java Development Kit是功能齐全的Java SDK，拥有JRE的所有功能，另外包括了编译器和工具让用户能够使用JDK对Java程序进行编译和运行。

JRE则是Java运行环境，JRE只需要保证已经编译完成的Java程序能够正常运行即可。所以JRE包括了JVM，Java类库，Java命令和一些其他的基础构件。

### 字节码

JVM能够理解的代码即为字节码，或者更加简单的定义是扩展名为.class的文件，因为Java的特性，所以字节码不面向任何操作系统，只面向虚拟机，由JVM来保证相同的字节码在不同的操作系统中稳定的表现。

为了进一步了解字节码，将这个概念和传统解释型语言进行比较。在传统解释型语言运行的过程中一般直接将高级语言翻译成汇编码即机器指令，在这个过程中没有进行任何的优化，所以相对于字节码而言效率更低。PS优化必须是脱离操作系统的，即不能针对操作系统进行优化。而相较于C语言这种字节码的效率较低，因为C编译后产生的汇编码已经是操作系统所能理解的机器指令，而Java通过Javac的编译产生的字节码虽然进行了平台无关的优化，但是仍然不能被操作系统直接执行，需要虚拟机作为解释器进行运行。

> [!TIP]
>
> 针对于上段描述的解释型语言和编译型语言进行进一步的解释
>
> * 编译型语言：通过编译器将源代码一次性编译成可以被当前操作系统执行的机器码，会生成当前操作系统的可执行文件，所以在这种情况下编译型语言的执行效率较高，典型的编译型语言有C，CPP，Go，Rust等。这些语言具有“一次编译，无限次运行”的特点。从介绍中就可以看出编译型语言是以来操作系统的，所以一般编译型语言是不能跨平台的，不仅仅是生成的可执行文件不能跨平台同时源代码也是不能跨平台的，这个相信大家都能有所体会。
> * 解释型语言：通过解释器一句一句将代码解释为机器代码一边执行一边转换，需要哪些源代码就转换哪些源代码，不会生成当前操作系统的可执行文件，虽然开发效率较高，但是这种解释执行的方式导致执行速度较慢，比较典型的解释型语言有Python，JavaScript，PHP等

再说明一下JIT，原本的JVM作为字节码的解释器只是对已经进行过优化的字节码转化为机器指令并执行，但是随着复用的概念越来越流行，有些方法和代码块会经常被调用，所以引进了JIT（just in time compilation）编译器，运行时编译，会对字节码对应的机器码进行保存，同时之后如果有复用不需要重新编译，提高了运行效率。所以Java从源代码到执行经过了编译和解释两个步骤，这也就是为什么Java被称为编译与解释共存的语言。

### Java与CPP

Java和CPP是经常被用来比较的两种语言，他们有以下这些特征需要记住

* 都是面对对象的语言，都支持封装、继承和多态
* Java不提供指针来直接访问内存，程序内存更加安全
* Java的类是单继承的，CPP支持多重继承，虽然Java的类不可以多继承，接口是可以多继承
* Java有GC（自动垃圾回收），不用程序员手动释放内存
* CPP同时支持方法重载和操作符重载，但是Java只支持方法重载

### 静态相关问题

1. 静态方法为什么不能调用非静态成员？

   > 静态方法是属于类的，在类加载的时候就会分配内存，可以通过类名进行直接访问，但是非静态成员属于实体，在对象实例化之前是不存在的，所以要通过实例对象的方法去访问。同时类的静态成员存在的时候非静态成员还不存在，此时调用肯定是非法的。

2. 静态方法和示例方法有什么不同

   > 1. 调用方法上不同，在外部调用静态方法的时候可以使用`ClassName.MethodName`也可以使用`ObjectName.MethodName`，静态方法可以不创建对象直接使用类名进行调用，而实例方法则只能使用创建对象的方法进行调用，所以一般为了区分这两种方法，静态方法使用`ClassName.MethodName`进行调用。
   > 2. 在访问成员的限制上不同，这在第一个问题中已经进行过强调，静态方法不能调用非静态成员，而实例方法没有这个限制。

### 重载和重写

重载是指同一个方法根据入参的不同做出不同的处理而重写是入参同样的情况下做出有别于父类的相应，覆盖父类的方法

重载发生在同一个类中（或者是父子类之间），方法名必须相同，仅仅是参数的类型、个数、顺序不同，方法的返回值和访问修饰符也可以不同。在编译时由编译器选取要执行的方法，并调用该方法，如果编译器找不到对应的参数就会报错，Java是允许重载任何方法的

重写是子类对父类已有方法的修改，方法名和参数是必须相同的，同时子类方法返回值类型要小于等于父类的返回值类型，抛出的异常要小于等于父类，访问修饰符范围大于等于父类（这三点可以使用里氏替换原则进行推导）。

> [!TIP]
>
> 为什么重写equals方法需要同时重写hashCode方法？
>
> 答：首先是hashCode()函数的作用，这个函数负责计算类的哈希码，这个哈希码的作用是确定该对象在哈希表中的索引位置。如果没有重写hashCode方法可能会导致虽然两个完全相同的对象通过equals判断是可以断定相等的，但是hashCode函数返回的哈希值不同会导致哈希表出现问题。
>
> 这里再说明一下Java在向hashmap和hashSet中添加对象时发生的操作，首先会计算要添加的对象的hashCode，如果在当前的hashMap中已经有相同的hashCode的对象，会再通过equals函数对两个对象是否相同进行判断，如果不同才会进行添加，相同则不会。
>
> 这里读者可能会感到奇怪为什么hashCode和equals需要区分，需要说明的是hashCode只是对某个对象的哈希值进行计算，计算的结果完全取决于hashCode的设计算法，糟糕的hashCode算法可能会导致很多不同的对象拥有相同的哈希值，所以并不能使用hashCode函数直接代替equals函数来判断两个对象是否相同。反之，如果使用equals完全替换hashCode理论上是没有任何问题的，但是在处理哈希表相关问题时效率会比较低下，相较于hashCode函数equals的执行速度较为缓慢。

### 基本类型

Java共有基本类型对应的八种包装类分别是`Byte`,`Short`,`Integer`,`Long`,`boolean`,`Float`,`Double`,`Character`。这些包装类中`Byte`,`Short`,`Integer`,`Long`默认创建了在[-128,127]的缓存数据，`Character`则是创建[0,127]的缓存，这也是常量池技术。下面是比较易懂的代码来辅助理解什么是常量池

```java
    /**
     * Returns an {@code Integer} instance representing the specified
     * {@code int} value.  If a new {@code Integer} instance is not
     * required, this method should generally be used in preference to
     * the constructor {@link #Integer(int)}, as this method is likely
     * to yield significantly better space and time performance by
     * caching frequently requested values.
     *
     * This method will always cache values in the range -128 to 127,
     * inclusive, and may cache other values outside of this range.
     *
     * @param  i an {@code int} value.
     * @return an {@code Integer} instance representing {@code i}.
     * @since  1.5
     */
    public static Integer valueOf(int i) {
        if (i >= IntegerCache.low && i <= IntegerCache.high)
            return IntegerCache.cache[i + (-IntegerCache.low)];
        return new Integer(i);
    }

    /**
     * Cache to support the object identity semantics of autoboxing for values between
     * -128 and 127 (inclusive) as required by JLS.
     *
     * The cache is initialized on first usage.  The size of the cache
     * may be controlled by the {@code -XX:AutoBoxCacheMax=<size>} option.
     * During VM initialization, java.lang.Integer.IntegerCache.high property
     * may be set and saved in the private system properties in the
     * sun.misc.VM class.
     */

    private static class IntegerCache {
        static final int low = -128;
        static final int high;
        static final Integer cache[];

        static {
            // high value may be configured by property
            int h = 127;
            String integerCacheHighPropValue =
                sun.misc.VM.getSavedProperty("java.lang.Integer.IntegerCache.high");
            if (integerCacheHighPropValue != null) {
                try {
                    int i = parseInt(integerCacheHighPropValue);
                    i = Math.max(i, 127);
                    // Maximum array size is Integer.MAX_VALUE
                    h = Math.min(i, Integer.MAX_VALUE - (-low) -1);
                } catch( NumberFormatException nfe) {
                    // If the property cannot be parsed into an int, ignore it.
                }
            }
            high = h;

            cache = new Integer[(high - low) + 1];
            int j = low;
            for(int k = 0; k < cache.length; k++)
                cache[k] = new Integer(j++);

            // range [-128, 127] must be interned (JLS7 5.1.7)
            assert IntegerCache.high >= 127;
        }

        private IntegerCache() {}
    }
```

我们可以看到如果超过了一定的范围源码还是会创建新的对象，但是如果需要创建的类型在常量池中已经存在就可以直接进行返回。

需要注意的是如果`Float`和`Double`两种类型并没有实现常量池。

> [!TIP]
>
> Java中的==判断符都是通过地址来进行比较的，所以在比较对象的时候需要使用equals函数，举一个简单的例子
>
> ```java
> Integer i1 = 40;
> Integer i2 = new Integer(40);
> System.out.println(i1==i2);
> ```
>
> 这个代码的输出结果是false
>
> 
>
> 同时还有一点需要注意，以上的包装类会自动装箱，在赋值时又会自动拆箱。所以在平时写代码的过程中尽量少使用包装类，以免计算速度的下降

---
# **本站参考地址**
---

## GitHub开源地址

- [https://github.com/icimence/learn](https://github.com/icimence/learn) **欢迎Star支持**

## 参考网址
- [https://javaguide.cn/](https://javaguide.cn/)



---
# 持续更新中...

网站内容会持续保持更新，欢迎收藏品鉴！
