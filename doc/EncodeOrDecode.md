Call Saved Rule用于调用已保存的加密规则，并支持表达式



为方便举例，预先保存一个名为AddPrefix的规则，作用是为输入的字符串添加前缀：###

![image-20220907171525652](https://raw.githubusercontent.com/ZhouJunjun/image/master/markdown/image-20220907171525652.png)



1.   当只调用一个已保存的加密规则时，可将表达式简化为指定加密规则的名称，下面的计算规则等同于：先将aaa进行MD5计算，再拼接上###前缀

     ![image-20220907171823806](https://raw.githubusercontent.com/ZhouJunjun/image/master/markdown/image-20220907171823806.png)