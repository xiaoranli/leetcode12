leetcode12. 整数转罗马数字
==
思路：
--

特别注意：本文介绍的是“贪心算法”，但这种贪心选择性质的成立是有一定条件的。跟这里的“候选”数值有关，如果“候选”数值是另一些数字，“贪心算法”很可能就失效了，此时可能就要应用“动态规划”来解决。这一点在本文并不展开，本人也要进行相应的学习以后，才能解释清楚这个问题。也希望能解释清楚这件事情的朋友能够把您的理解分享给大家。  
在生活中的例子：  
在以前还使用现金购物的年代，如果我们不想让对方找钱，付款的时候我们会尽量拿面值大的纸币给对方，这样才会使得我们给对方的纸币张数最少，对方点钱的时候（因为对方要检验你给的钱对不对）也最方便。最极端的一种情况，你要是都拿零钱去买一个比较贵重的东西，我相信没有人是很高兴收到你的钱的，因为他们点钱费劲。
“整数转罗马数字”与上面的问题是一模一样的思想：在表示一个较大整数的时候，“罗马数字”不会让你都用 11 加起来，肯定是写出来的“罗马数字”的个数越少越好。
于这道问题，“纸币”有哪些，并不是只有题目中给出的对应关系，根据规则，还可以得到一些“纸币”的面值，不过都是有限个“纸币”，很快就能罗列出来。
于是解这道题的思路就出来了：  
“纸币”有哪些？  
一个整数如何做“加法因子”的分解？  
链接：https://leetcode-cn.com/problems/integer-to-roman/solution/tan-xin-suan-fa-by-liweiwei1419/

代码： 
--
<pre>
/**
 * @author lihe
 * @date 2019/10/11 21:19
 * @descriptor  12. 整数转罗马数字
 */
public class IntToRoman_12 {

    public static String intToRoman(int num) {
        String[] strings = {"M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"};
        int [] numbers = {1000,900,500,400,100,90,50,40,10,9,5,4,1};

        StringBuilder builder = new StringBuilder();
        int index = 0;
        while(index<13){
            while(num >= numbers[index]){
                builder.append(strings[index]);
                num -= numbers[index];
            }
            index ++;
        }
        return builder.toString();
    }

    public static void main(String[] args) {
        int sum = 1994;
        String s = intToRoman(sum);
        System.out.println(s);
    }
}
</pre>
