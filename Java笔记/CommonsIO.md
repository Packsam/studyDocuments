# CommomsIO组件
## 文件/目录大小
 `FileUtils.sizeOf(file)`  
## 目录操作 
`FileUtils.listFiles(file,fileFilter,listFilter)`fileFilter 指定文件过滤器  
可以过滤空文件 `EmptyFileFilter.EMPTY/NO_EMPTY`  
选择后缀名的文件`SuffixFileFilter("")`同时两个后缀还可以通过`FileFilterUtils.or`进行或  
`listFilter`可以指定为`DirectoryFileFilter`列出子孙级  
## 读取文件
`FileUtils.readFileToString`/`FileUtils.readFileToByteArray`  
逐行读取`List<E> x = FileUtils.readLines(file,"UTF-8")`
## 写出内容
`FileUtils.write(file,str,"UTF-8",true` true指定是否为追加  
也可以从Byte数组或者List进行写入
## 拷贝内容
`FileUtils.copyFile(file src,file dest)`  
`FileUtils.copyFileToDirectory(file src,file dest)`  
`FileUtils.copyDirectoryToDirectory(file src,file dest)`把源目录拷贝为目的目录的子目录  
`FileUtils.copyDirectory`把原目录中的内容拷贝到目的目录
`FileUtils.copyURLToFile(URL url,File file)`拷贝URL
