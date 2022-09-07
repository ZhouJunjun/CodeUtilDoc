Call Saved Rule用于调用已保存的加密规则，并支持表达式



为方便举例，预先保存一个名为Around的规则，作用是为输入的字符串添加前缀**$***和添加后缀**#**

![image-20220907173220747](https://raw.githubusercontent.com/ZhouJunjun/image/master/markdown/image-20220907173220747.png)

![image-20220907173359439](https://raw.githubusercontent.com/ZhouJunjun/image/master/markdown/image-20220907173359439.png)



1.   当只调用一个已保存的加密规则时，可将表达式简化为指定加密规则的名称，下面的计算规则等同于：先将aaa进行MD5计算，再拼接上**$**前缀和**#**后缀

     ![image-20220907173600660](https://raw.githubusercontent.com/ZhouJunjun/image/master/markdown/image-20220907173600660.png)



2.   当需要调用一个以上加密规则时，本工具提供两个变量，并支持多重调用和支持+操作符：

     ***$input*** 初始输入值

     ***$last*** 上一个规则的计算结果

     ![image-20220907173703566](https://raw.githubusercontent.com/ZhouJunjun/image/master/markdown/image-20220907173703566.png)

     上图示例中的表达式：**Around($input+Around(Around($last)))** 的计算过程为：

     1.   $last等于上一个规则的计算结果，即MD5(aaa) = 47bce5c74f589f4867dbd57e9ca9f808

     2.   Around($last) = $47bce5c74f589f4867dbd57e9ca9f808#

     3.   Around(Around($last)) = $$47bce5c74f589f4867dbd57e9ca9f808##

     4.   $input + Around(Around($last)) = aaa$$47bce5c74f589f4867dbd57e9ca9f808##

     5.   Around($input + Around(Around($last))) = $aaa$$47bce5c74f589f4867dbd57e9ca9f808###

上述举例的Around可以替换成任意不同的已保存的规则