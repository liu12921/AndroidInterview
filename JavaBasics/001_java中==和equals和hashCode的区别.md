## java中==和equals和hashCode的区别
####  “==” 用于比较两个对象是否相同 ####

- 	针对基本数据类型对比的是值是否相等个
- 	针对对象，对比的是	对象的内存地址是否相等

#### “equals”是Object类中的方法 ####

-	在Object中默认的实现是和“==”的结果一直，默认实现是直接对比两个对象的地址值

	```java
    public boolean equals(Object obj) { 
        return (this == obj);  
	}  
	```
-	针对我们自己创建的类的对象，我们可以通过复写equals方法来实现我们自己的判断

#### 关于HashCode
-	hashCode也是Object类的一个方法，放回一个int类型的值
-	主要在集合中操作，提高查询速度（HashMap，HashSet）
-	我们可以复写HashCode方法，用来适应自己的业务逻辑


#### PS
-	例如：String中，==比较的是两个字符串对象是是同一个对象，equals比较的是两个对象的值是否相同
-	一般情况下重写了equals方法的话，一般要重写hashCode方法，因为会在再操作Hash相关的集合时候，如果不重写会添加进去两个equals的对象