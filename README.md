# Java-object-SerializeAndDeserialize-
### Java 对象序列化和反序列化 （实现 Serializable 接口）

#### 序列化和反序列化的概念
　　 把对象转换为字节序列的过程称为对象的序列化。
  　 把字节序列恢复为对象的过程称为对象的反序列化。
~~~
    对象的序列化主要有两种用途：
　　1） 把对象的字节序列永久地保存到硬盘上，通常存放在一个文件中；
　　2） 在网络上传送对象的字节序列。
~~~
 
#### JDK类库中的序列化API
~~~
　　java.io.ObjectOutputStream代表对象输出流，它的writeObject(Object obj)方法可对参数指定的obj对象进行序列化，
    把得到的字节序列写到一个目标输出流中。
    
　　java.io.ObjectInputStream代表对象输入流，它的readObject()方法从一个源输入流中读取字节序列，再把它们反序列化为一个对象，并将其返回。
　　只有实现了Serializable和Externalizable接口的类的对象才能被序列化。Externalizable接口继承自 Serializable接口，
    实现Externalizable接口的类完全由自身来控制序列化的行为,
　　而仅实现Serializable接口的类可以 采用默认的序列化方式 。
~~~

~~~
 对象序列化包括如下步骤：　
   　1、创建一个对象输出流，它可以包装一个其他类型的目标输出流，如文件输出流；
　　 2、通过对象输出流的writeObject()方法写对象。

 对象反序列化的步骤如下：
　　1、创建一个对象输入流，它可以包装一个其他类型的源输入流，如文件输入流；
　　2、通过对象输入流的readObject()方法读取对象。
~~~
