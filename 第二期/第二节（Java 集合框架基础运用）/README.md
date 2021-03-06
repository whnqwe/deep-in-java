### 第二期 第二节 Java 集合框架基础运用



## 你所知道的集合

process



collection API

```java
public interface Collection<E> extends Iterable<E> {
      int size(); 
    Int.MAX +1  = Int.MIN
         Int.MAX +2  = Int.MIN+1
        
         boolean isEmpty();
    
    boolean contains(Object o); //双想链表  正向搜索  反向搜索
    
    Iterator<E> iterator();
    //在迭代的时候 删除元素会报错
    
      Object[] toArray();
    
      <T> T[] toArray(T[] a);
    
      add 
               * @throws UnsupportedOperationException  不能添加
     * @throws ClassCastException  
     * @throws NullPointerException  null
     * @throws IllegalArgumentException   实体中id为null
     * @throws IllegalStateException   id 不为小于零 但传入的Id 为-1
          
          
          remove
          
          
          改查
       
}
```







#### Collection interfaces（集合接口）

##### collection

###### 通⽤用接⼝

• java.util.List

可以重复  下标访问

扩张Collection 

> get()



• java.util.Set

不重复 

不保证顺序 

> （teeset例外   )
>
> • java.util.SortedSet ( java1.6之前直接实现）
> • java.util.NavigableSet（since Java 1.6）

Hash 是否是有序的

//错觉

ListAndSetDemo.java

想要有序

> SortedSet

>    NavigableSet

  // 一致性 Hash 1 2 3
    // 3000 的请求，平均每个节点是一个 1000 个请求
    // 当 节点 1 失效，Key 1 就尝试 2 或 3





• java.util.SortedSet
• java.util.NavigableSet（since Java 1.6）

• java.util.Queue（since Java 1.5）(单项列表）

```java
public interface Queue<E> extends Collection<E> {
      boolean add(E e);  //与collection中的add 语义发生了变化
     boolean offer(E e); //使用offer
    poll 取出 不移除
        peek 只取
    
}
```

```
Queue<String> qe = new LinkedList<>();
List<String> list = new LinkedList<>();
Deque<String> dqe = new LinkedList<>();
```





• java.util.Deque（since Java 1.6）（双向列表）

linkedList实现deque



为什么继承在Collection<E>接口

还要在写一遍 add         不能写 poll方法就没意义了

###### 并发接⼝

• java.util.concurrent.BlockingQueue（since Java 1.5）
• java.util.concurrent.BlockingDeque（since Java 1.6）
• java.util.concurrent.TransferQueue （since Java 1.7）

##### Map

###### 通⽤用接⼝



MapAndSetDemo

• java.util.SortedMap
• java.util.NavigableMap（since Java 1.6）

###### 并发接⼝

• java.util.concurrent.ConcurrentMap（since Java 1.5）
• java.util.concurrent.ConcurrentNavigableMap（since Java 1.6）



##### Dictionary

->HashTable



##### Enum

大于1.5  Enum 任何枚举会继承这个类 final class



1.5 之前 Enumeration表示枚举









#### • Infrastructure（基础设施）



其他框架对java的框架做了很多的补充



##### commons-collections

bag

boundedMap (有边界的Map)

>  所有的集合有边界  java语言限制

> ArrayList  int的最大值









#### • General-purpose implementations（通⽤用实现）

运用范围

ArrayList



#### • Abstract implementations（抽象实现）

设计范围

#### • Legacy implementations（遗留留实现）

遗留实现都是线程安全

Vector

HashTable


java.util.Vector

Vector   ArrayList

>       // Vector 数组实现，对比 ArrayList，实现了 List
>         // Vector 所有操作线程安全的，使用关键字“synchronized”修饰
>         Vector<String> vector = new Vector<>();
>         List<String> list = new ArrayList<>();
>         // 如果 Vector 在方法内部使用的话， synchronized 修饰后的方法基本上没有线程同步的消耗
>         vector.add("A");
>         list.add("A");

java.util.Stack

    // Vector 是 FIFO
        // Stack 是 LIFO，是 Vector 的子类
java.util.Hashtable
java.util.Enumeration
java.util.BitSet



#### • Convenience implementations（便利实现）

```
EnumSet
Set Map of方法
```

#### • Wrapper implementations（包装实现）

#### • Special-purpose implementations（特殊实现）

weakSoftHashMap

#### • Array Utilities（数组⼯工具类）



#### • Algorithms（算法）



#### • Concurrent implementations（并发实现



