# 字节缓冲流：BufferedInputStream & BufferedOutputStream
对字节流增加8K大小的缓冲区。  
`InputStream bis = new BufferedIutputStream(new FileInputStream(file))`  
可以减少IO对文件的操作时间。

# 字符缓冲流：BufferReader & BufferedWriter  
字符缓冲流和字符流一样，只适用纯文本文件。字符缓冲流中实现了一些新函数，但是注意，由于新增了一些方法，所以不可以使用多态，而应该直接BufferReader或BufferedWriter 引用指向其对象而不是  
用其父类Reader引用指向对象。  
新方法：  
`readLine()`逐行读取  
`newLine()`换行符  
e.g  
`line = a.readLine()`  
`b.write(line)`  
`b.newLine()`  
`b.flush()`

# 转换流：InputStreamReader & OutputStreamWriter  
1:将字节流转换为字符流，方便处理（字节流必须为纯文本）。2：处理过程中可以指定编解码（Input/Output）字符集  
可以用`System.in`和`System.out`作为参数对转换流进行构造。S.in和out都是字节流。  
因为转换流把字节流转换为了字符流，所以转化流对象可以作为字符缓冲流构造器的参数：  
e.g.  
`BufferReader = reader = new BufferReader(new InputStreamReader(system.in),"UTF-8")`  

# 数据流：DataInputStream & DataOutputStream  
数据流给出了许多方法 包括读写 int UTF char boolean 可以操作数据类型  
同理作为处理流也需要用原始节点流进行构造，为了提升性能，所有原始节点流都最好使用缓冲流包装。  

# 对象流：ObjectInputStream & ObjectOutputStream  
可以处理对象等非原始数据类型   
对象输出流：序列化：对象→流→文件/内存  
对象输入流：反序列化：文件/内存→流→对象  
并不是所有对象都可以序列化，必须实现`Serializable`接口才可以进行序列化  
注意，读写的顺序应该一致，即使有一些用不到的数据，但是要写入了就必须要读出。  
关键字 trasient可以防止对象中的相应的成员被序列化，成为透明。

# 打印流 PrintStream & PrintWriter
打印流的构造器可以传入控制西东刷新的指令，就可以不用在输出之后接flush  
重定向：`System.setOut()`可以将syso的输出端重定向，例如文件。

# 随机流 RandomAcessFile  
读写都使用一个流，构造器2个参数，指定文件，或者读写模式。操作方法与字节流类似  
seek方法可以指定文件的操作偏移位置，用于文件的分块分割操作。  
可以通过面向对象把分割文件的许多参数储存为类成员，分割方法可以写成成员函数。

# 序列流 SequenceInputStream
将多个输入流合成一个流  
用`Vector <E> vi = new Vector<>()`泛型一般为输入流  
`vi.add(InputStream)`  
`SequenceInputStream sis = new SequenceInputStream(vi.elements())`  
序列流只是将多个输入流合并为一个流进行操作，并没有把多个文件块合在一起，只是不用通过for循环遍历多个输入流
