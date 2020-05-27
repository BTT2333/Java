# IDEA 快捷键
1. 运行：Ctrl+Shift+F10
2. 复制行：Ctrl+D
3. 删除行：Ctrl+Shift+Y
4. 移动行：Alt+Shift+↑/↓
5. 选中行：Shift+↑/↓
6. 格式化代码：Ctrl+Alt+L
7. 注释：Ctrl+/或者Ctrl+Shift+/
8. 导包、自动修正代码：Alt+Enter
9. 自动生成代码：Alt+Ins
10. for循环 fori正序，forr倒序

# Java
## 基础
1. 转义符：\
2. 输入：Scanner
```java
Scanner sc = new Scanner(System.in);
int num = sc.nextInt();
String str = sc.next();
```

3. 随机数：random
```java
Random r = new Random();
//0~n随机数
int num = r.nextInt(n);
```



## 集合容器
### ArrayList
```java
ArrayList<String> list = new ArrayList<>();
//向集合尾添加元素
list.add(str);
//向集合指定位置添加元素
list.add(index,str);
//从集合中获取元素
list.get(index);
//从集合中删除指定位置元素并返回
String s = list.remove(index);
//集合长度
int sz = list.size();
```
### Map
```java
Map<String,Integer> map = new HashMap<>();
```
### Queue
```java
Queue<Integer> que = new LinkList<>();
```
### String
```java
//不推荐str.equals("abc");\
//当str为null时后者返回false，前者报错
"abc".equals(str);
//忽略大小写
str1.equalsIgnoreCase(str2);
str.length();
str.charAt(index);
//查找子串第一次出现的位置，没有返回-1
int flag = str.indexof(str1);
//截取位置从[begin,end)子串
String str1 = str.substring(begin,end);
//begin到结尾
String str2 = str.substring(begin);
//替换字符串中原有子串
String str1 = str.replace(oldStr,newStr);
//按照参数分割字符串,"."需要写为"\\."
String[] strArray = str.split(",")
```
### Arrays
```java
//数组变为字符串
Arrays.toString(array);
//数组排序，默认按照升序排序
//自定义类需要有Comparable或者Comparator接口
Arrays.sort(array);
```
### Math
```java
//取绝对值
Math.abs();
//向上取整
Math.ceil();
//向下取整
Math.floor();
//四舍五入
Math.round();
//π常量
Math.PI
```


## Tips
### static
1. 成员方法不要写static关键字。
2. 成员变量使用了static，则此变量不属于对象，而属于类
3. static静态方法属于类，可以使用类名调用；成员方法必须由对象调用。
4. 静态变量和静态方法直接只用类名进行调用。
5. 静态不能直接访问非静态。内存中**先**有静态，**后**有的非静态。
6. 静态方法中不能使用this关键字。
7. 静态代码块比构造方法先执行，且执行唯一一次。

### 继承
1. 成员变量重名，创建子类对象访问
   1. 直接通过子类对象访问：等号左边是谁就优先用谁，没有则向上找
   2. 间接通过成员方法访问：方法属于谁就优先用谁，没有则向上找。
2. 局部变量、子类成员变量、父类成员变量
   1. 局部变量： num
   2. 子类成员变量：this.num
   3. 父类成员变量：super.num
3. 成员方法重名，创建对象是谁就优先用谁，没有则向上找。
4. 重写方法前加上 **@Override** 检测重写是否正确
5. 子类方法返回值必须 **小于等于** 父类方法返回值。
6. 子类方法的权限必须 **大于等于** 父类方法修饰符。
   1. public > protected > (default) > private
7. 子类构造方法隐含 **super()** 调用父类构造方法
   1. 先父类构造方法，后子类
   2. super父类构造调用，必须是子类构造第一个语句
   3. super调用父类重载构造
8. super
   1. 子类成员方法中，访问父类成员变量
   2. 子类成员方法中，访问父类成员方法
   3. 子类构造方法中，访问父类构造方法
9. this
   1.  本类成员方法中，访问本类成员变量
   2.  本类成员方法中，访问本类另一个成员方法
   3.  本类构造方法中，访问本类另一个构造方法
10. 继承特点
    1.  Java单继承，一个子类只有一个直接父类
    2.  Java多级继承
    3.  Java一个父类可以有多个子类