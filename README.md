leetcode12. 整数转罗马数字
==
思路：
--
    先罗马字符转对应数字放入数组，然后遍历数组，相邻两项相减，大于0则加减数，小于0则减掉两数之差，对这n-1项sum求和。  
    但是这样没有考虑最后一项，如果最后两项还存在小的在前面的情况则不必操作，不然还要要加上最后一项。 
     遍历数组还得加一个条件，当只有一个罗马字符时，直接返回这个字符对应的数就行，否则遍历会数组越界。     
代码： 
--
<pre>
