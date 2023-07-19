### 支持加密功能的表单调试工具

1.支持调用已在【加/解密调试工具】保存的加密规则对参数值进行加/解密运算。本工具会在发起请求时自动将加密结果作为对应参数的值。

![image-20230719161452728](https://raw.githubusercontent.com/ZhouJunjun/CodeUtilDoc/main/image/image-20230719161452728.png)

![image-20230719161522128](https://raw.githubusercontent.com/ZhouJunjun/CodeUtilDoc/main/image/image-20230719161522128.png)

![image-20230719161559354](https://raw.githubusercontent.com/ZhouJunjun/CodeUtilDoc/main/image/image-20230719161559354.png)

2.   支持字段拼接功能（通常用于参数的整体加密），可指定：排序、分隔符和字段拼接范围。下图示例为：

     某接口接受三个参数：user、pwd和signature；pwd单独加密；signature的值等于：将user参数和pwd参数按参数名从小到大排序，并使用分隔符&，拼接成 a=A&b=B的形式，最后再调用规则进行加密。

     ![image-20230719162659281](https://raw.githubusercontent.com/ZhouJunjun/CodeUtilDoc/main/image/image-20230719162659281.png)

3.   支持上传文件

     ![image-20230719163259083](https://raw.githubusercontent.com/ZhouJunjun/CodeUtilDoc/main/image/image-20230719163259083.png)