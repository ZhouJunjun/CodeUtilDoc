### 加/解密调试工具

#### 执行面板Tab

1.   先在**右侧规则编辑区**编辑执行规则，然后在左侧输入区输入需要加/解密的字符串，点击下方的【Run】即可执行；执行结果在中间的结果区展示。
2.   加/密规则从上往下执行，规则1的输入为原始字符串，规则2的输入为规则1的执行结果..., 规则n的输入为规则n-1的执行结果

![image-20230719153053695](https://raw.githubusercontent.com/ZhouJunjun/CodeUtilDoc/master/image/image-20230719153053695.png)



#### 配置面板Tab

如果需要使用**执行面板Tab-右侧规则编辑区**中不存在的加密算法，可以使用自定义功能

1.   下载 https://github.com/ZhouJunjun/encrypt-core，并创建EncryptRunner的子类，最后打包成jar。

2.   将该jar包放到统一的目录下，并在Setting tab中指定该目录，最后重启idea即可完成导入。

![image-20230719154042388](https://raw.githubusercontent.com/ZhouJunjun/CodeUtilDoc/main/image/image-20230719154042388.png)



#### 复杂功能说明

#### Call Saved Rule

该规则支持简单的字符串编辑功能

1.   变量$0代表用户输入，变量$1~n代表**右侧规则编辑区**的历史执行结果，变量$last代表**右侧规则编辑区**上一条规则的执行结果。

2.   可使用运算符+号进行字符串拼接

3.   可在计算过程中拼接字符串(使用反引号``)

4.   可调用已保存的规则：SavedRuleName(变量)

     ![image-20230719160105438](https://raw.githubusercontent.com/ZhouJunjun/CodeUtilDoc/main/image/image-20230719160105438.png)