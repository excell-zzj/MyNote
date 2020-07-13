# typora使用教程

## 常用快捷键

~~~
Ctrl+B 	加粗		Ctrl+H 	 标题
Ctrl+1  一阶标题    Ctrl+B  字体加粗
Ctrl+2  二阶标题    Ctrl+I  字体倾斜
Ctrl+3  三阶标题    Ctrl+U  下划线
Ctrl+4  四阶标题    Ctrl+Home   返回Typora顶部
Ctrl+5  五阶标题    Ctrl+End    返回Typora底部
Ctrl+6  六阶标题    Ctrl+T  创建表格
Ctrl+L  选中某句话   Ctrl+K  创建超链接
Ctrl+D  选中某个单词  Ctrl+F  搜索
Ctrl+E  选中相同格式的文字   Ctrl+H  搜索并替换
Alt+Shift+5 删除线 Ctrl+Shift+I    插入图片
Ctrl+Shift+M    公式块 Ctrl+Shift+Q    引用
~~~



## 引用

~~~
> 	引用内容1
>>	引用内容2
>>>	引用内容3
~~~

> 引用内容1
>
> >引用内容2
> >
> >> 引用内容3



## 代码

- 只要输入“~ ~ ~” 回车

~~~c++
int a = 3;
while(a != 1){
    pass;
}
~~~

- 单行代码：只要输入``

  `string s = a`

## 列表

#### 无序列表

- 只要在前面输出- 或者 * 或者+
  - 对于多行，只需要前面输出TAB

#### 有序列表

1. 只要输出数字加.
   1. 多行也是一样前面输入TAB

## 表格

语法：



~~~
|姓名|性别|年龄|手机号|
|:---|:--:|:--:|---:|
|张三|男|21|18975346876|
|李四|女|23|17789548964|
|王五|男|25|15876513546|

左对齐 ：|
右对齐 |：
中对齐 ：|：
~~~

| 姓名 | 性别 | 年龄 |      手机号 |
| :--- | :--: | :--: | ----------: |
| 张三 |  男  |  21  | 18975346876 |
| 李四 |  女  |  23  | 17789548964 |
| 王五 |  男  |  25  | 15876513546 |

## 添加图片

只需要输入：`![名字](C:\Users\think\Desktop\桌面壁纸\201903031829559065_small.jpg “图片标题”)`

<img src="C:\Users\think\Desktop\桌面壁纸\201903031829559065_small.jpg" alt="名字" title="图片标题" style="zoom:80%;" />

## 超链接

- 语法1：`[要显示的东西](连接地址)`
  - 显示效果：[一个教程](https://www.jianshu.com/p/a6a6a22e9393)
- 快捷方式：ctrl+K
- 第三种语法：`<网址>`
  - <https://github.com/>

## 其他

1. 斜体：

   - 语法：

     ~~~
     * 斜体 *
     _斜体_
     ~~~

   - 效果：*斜体*

2. 加粗

   - 语法：`**加粗**  或者 __加粗__`
   - 效果：**加粗**

3. 下划线

   - 语法：`<u>下划线</u>`
   - 效果：<u>下划线</u>

4. 删除线

   - 语法：`~~删除线~~`
   - 效果：~~删除~~

5. 分割线

   - 用法：

     ~~~
     ***
     ---
     ___
     ~~~

6. 注脚

   - 语法：`zhujiao[^1]`
   - 效果：注脚[^1]

7. 上下标

   - 语法：

     ~~~
     $3^2=9$			// 3^2^=9
     $3^{(3-1)}=9$
     $H_2SO_4$		//H~2~SO~4~
     $H_{2SO_4}$
     ~~~

     3^2^=9​
     $3^{(3-1)}=9$
     $H_2SO_4$

     *H~2~SO~4~*

     $H_{2SO_4}$

8. 符号输入

   - 语法：

     ~~~
     \\   反斜线
     \`   反引号
     \*   星号
     \_   底线
     \{ \}  花括号
     \[ \]  方括号
     \( \)  括弧
     \#   井字号
     \+   加号
     \-   减号
     \.   英文句点
     \!   惊叹号
     ~~~

     \\   反斜线
     \`   反引号
     \*   星号
     \_   底线
     \{ \}  花括号
     \[ \]  方括号
     \( \)  括弧
     \#   井字号
     \+   加号
     \-   减号
     \.   英文句点
     \!   惊叹号

9. 特殊符号

   - 用例：

     ~~~
     &copy;      版权      
     &reg;       注册商标
     &trade;     商标
     &nbsp;      空格
     &amp;       和号
     &quot;      引号
     &apos;      撇号
     &lt;        小于号
     &gt;        大于号
     &ne;        不等号
     &le;        小于等于
     &ge;        大于等于
     &cent;      分
     &pound;     磅
     &euro;      欧元
     &yen;       元
     &sect;      节
     &times;     乘号
     &divide;    除号
     &plusmn;    正负号
     ~~~

     &copy;      版权      
     &reg;       注册商标
     &trade;     商标
     &nbsp;      空格
     &amp;       和号
     &quot;      引号
     &apos;      撇号
     &lt;        小于号
     &gt;        大于号
     &ne;        不等号
     &le;        小于等于
     &ge;        大于等于
     &cent;      分
     &pound;     磅
     &euro;      欧元
     &yen;       元
     &sect;      节
     &times;     乘号
     &divide;    除号
     &plusmn;    正负号

10. 高亮：`==高亮==`
    
- ==高亮==
    
11. emoji表情：`只需要在两个冒号中间即可`

    - :smile::small_airplane::currency_exchange::accept:

12. 居中：`<center>这是要居中的内容</center>`

    - <center>居中</center>



## 行内与独行

1. 行内公式：将公式插入到本行内，符号：`$公式内容$`，如：$xyz$
2. 独行公式：将公式插入到新的一行内，并且居中，符号：`$$公式内容$$`，如：$$xyz$$

## 上标、下标与组合

1. 上标符号，符号：`^`，如：$x^4$
2. 下标符号，符号：`_`，如：$x_1$
3. 组合符号，符号：`{}`，如：${16}_{8}O{2+}_{2}$

## 汉字、字体与格式

1. 汉字形式，符号：`\mbox{}`，如：$V_{\mbox{初始}}$
2. 字体控制，符号：`\displaystyle`，如：$\displaystyle \frac{x+y}{y+z}$
3. 下划线符号，符号：`\underline`，如：$\underline{x+y}$
4. 标签，符号`\tag{数字}`，如：$\tag{11}$
5. 上大括号，符号：`\overbrace{算式}`，如：$\overbrace{a+b+c+d}^{2.0}$
6. 下大括号，符号：`\underbrace{算式}`，如：$a+\underbrace{b+c}_{1.0}+d$
7. 上位符号，符号：`\stacrel{上位符号}{基位符号}`，如：$\vec{x}\stackrel{\mathrm{def}}{=}{x_1,\dots,x_n}$

## 占位符

1. 两个quad空格，符号：`\qquad`，如：$x \qquad y$
2. quad空格，符号：`\quad`，如：$x \quad y$
3. 大空格，符号`\`，如：$x \  y$
4. 中空格，符号`\:`，如：$x : y$
5. 小空格，符号`\,`，如：$x , y$
6. 没有空格，符号``，如：$xy$
7. 紧贴，符号`\!`，如：$x ! y$

## 定界符与组合

1. 括号，符号：`（）\big(\big) \Big(\Big) \bigg(\bigg) \Bigg(\Bigg)`，如：$（）\big(\big) \Big(\Big) \bigg(\bigg) \Bigg(\Bigg)$
2. 中括号，符号：`[]`，如：$[x+y]$
3. 大括号，符号：`\{ \}`，如：${x+y}$
4. 自适应括号，符号：`\left \right`，如：$\left(x\right)$，$\left(x{yz}\right)$
5. 组合公式，符号：`{上位公式 \choose 下位公式}`，如：${n+1 \choose k}={n \choose k}+{n \choose k-1}$
6. 组合公式，符号：`{上位公式 \atop 下位公式}`，如：$\sum_{k_0,k_1,\ldots>0 \atop k_0+k_1+\cdots=n}A_{k_0}A_{k_1}\cdots$

## 四则运算

1. 加法运算，符号：`+`，如：$x+y=z$
2. 减法运算，符号：`-`，如：$x-y=z$
3. 加减运算，符号：`\pm`，如：$x \pm y=z$
4. 减甲运算，符号：`\mp`，如：$x \mp y=z$
5. 乘法运算，符号：`\times`，如：$x \times y=z$
6. 点乘运算，符号：`\cdot`，如：$x \cdot y=z$
7. 星乘运算，符号：`\ast`，如：$x \ast y=z$
8. 除法运算，符号：`\div`，如：$x \div y=z$
9. 斜法运算，符号：`/`，如：$x/y=z$
10. 分式表示，符号：`\frac{分子}{分母}`，如：$\frac{x+y}{y+z}$
11. 分式表示，符号：`{分子} \voer {分母}`，如：${x+y} \over {y+z}$
12. 绝对值表示，符号：`||`，如：$|x+y|$

## 高级运算

1. 平均数运算，符号：`\overline{算式}`，如：$\overline{xyz}$
2. 开二次方运算，符号：`\sqrt`，如：$\sqrt x$
3. 开方运算，符号：`\sqrt[开方数]{被开方数}`，如：$\sqrt[3]{x+y}$
4. 对数运算，符号：`\log`，如：$\log(x)$
5. 极限运算，符号：`\lim`，如：$\lim^{x \to \infty}_{y \to 0}{\frac{x}{y}}$
6. 极限运算，符号：`\displaystyle \lim`，如：$\displaystyle \lim^{x \to \infty}_{y \to 0}{\frac{x}{y}}$
7. 求和运算，符号：`\sum`，如：$\sum^{x \to \infty}_{y \to 0}{\frac{x}{y}}$
8. 求和运算，符号：`\displaystyle \sum`，如：$\displaystyle \sum^{x \to \infty}_{y \to 0}{\frac{x}{y}}$
9. 积分运算，符号：`\int`，如：$\int^{\infty}_{0}{xdx}$
10. 积分运算，符号：`\displaystyle \int`，如：$\displaystyle \int^{\infty}_{0}{xdx}$
11. 微分运算，符号：`\partial`，如：$\frac{\partial x}{\partial y}$
12. 矩阵表示，符号：`\begin{matrix} \end{matrix}`，如：$\left[ \begin{matrix} 1 &2 &\cdots &4\5 &6 &\cdots &8\\vdots &\vdots &\ddots &\vdots\13 &14 &\cdots &16\end{matrix} \right]$

## 逻辑运算

1. 等于运算，符号：`=`，如：$x+y=z$
2. 大于运算，符号：`>`，如：$x+y>z$
3. 小于运算，符号：`<`，如：$x+y<z$
4. 大于等于运算，符号：`\geq`，如：$x+y \geq z$
5. 小于等于运算，符号：`\leq`，如：$x+y \leq z$
6. 不等于运算，符号：`\neq`，如：$x+y \neq z$
7. 不大于等于运算，符号：`\ngeq`，如：$x+y \ngeq z$
8. 不大于等于运算，符号：`\not\geq`，如：$x+y \not\geq z$
9. 不小于等于运算，符号：`\nleq`，如：$x+y \nleq z$
10. 不小于等于运算，符号：`\not\leq`，如：$x+y \not\leq z$
11. 约等于运算，符号：`\approx`，如：$x+y \approx z$
12. 恒定等于运算，符号：`\equiv`，如：$x+y \equiv z$

## 集合运算

1. 属于运算，符号：`\in`，如：$x \in y$
2. 不属于运算，符号：`\notin`，如：$x \notin y$
3. 不属于运算，符号：`\not\in`，如：$x \not\in y$
4. 子集运算，符号：`\subset`，如：$x \subset y$
5. 子集运算，符号：`\supset`，如：$x \supset y$
6. 真子集运算，符号：`\subseteq`，如：$x \subseteq y$
7. 非真子集运算，符号：`\subsetneq`，如：$x \subsetneq y$
8. 真子集运算，符号：`\supseteq`，如：$x \supseteq y$
9. 非真子集运算，符号：`\supsetneq`，如：$x \supsetneq y$
10. 非子集运算，符号：`\not\subset`，如：$x \not\subset y$
11. 非子集运算，符号：`\not\supset`，如：$x \not\supset y$
12. 并集运算，符号：`\cup`，如：$x \cup y$
13. 交集运算，符号：`\cap`，如：$x \cap y$
14. 差集运算，符号：`\setminus`，如：$x \setminus y$
15. 同或运算，符号：`\bigodot`，如：$x \bigodot y$
16. 同与运算，符号：`\bigotimes`，如：$x \bigotimes y$
17. 实数集合，符号：`\mathbb{R}`，如：$\mathbb{R}$
18. 自然数集合，符号：`\mathbb{Z}`，如：$\mathbb{Z}$
19. 空集，符号：`\emptyset`，如：$\emptyset$

## 数学符号

1. 无穷，符号：`\infty`，如：$\infty$
2. 虚数，符号：`\imath`，如：$\imath$
3. 虚数，符号：`\jmath`，如：$\jmath$
4. 数学符号，符号`\hat{a}`，如：$\hat{a}$
5. 数学符号，符号`\check{a}`，如：$\check{a}$
6. 数学符号，符号`\breve{a}`，如：$\breve{a}$
7. 数学符号，符号`\tilde{a}`，如：$\tilde{a}$
8. 数学符号，符号`\bar{a}`，如：$\bar{a}$
9. 矢量符号，符号`\vec{a}`，如：$\vec{a}$
10. 数学符号，符号`\acute{a}`，如：$\acute{a}$
11. 数学符号，符号`\grave{a}`，如：$\grave{a}$
12. 数学符号，符号`\mathring{a}`，如：$\mathring{a}$
13. 一阶导数符号，符号`\dot{a}`，如：$\dot{a}$
14. 二阶导数符号，符号`\ddot{a}`，如：$\ddot{a}$
15. 上箭头，符号：`\uparrow`，如：$\uparrow$
16. 上箭头，符号：`\Uparrow`，如：$\Uparrow$
17. 下箭头，符号：`\downarrow`，如：$\downarrow$
18. 下箭头，符号：`\Downarrow`，如：$\Downarrow$
19. 左箭头，符号：`\leftarrow`，如：$\leftarrow$
20. 左箭头，符号：`\Leftarrow`，如：$\Leftarrow$
21. 右箭头，符号：`\rightarrow`，如：$\rightarrow$
22. 右箭头，符号：`\Rightarrow`，如：$\Rightarrow$
23. 底端对齐的省略号，符号：`\ldots`，如：$1,2,\ldots,n$
24. 中线对齐的省略号，符号：`\cdots`，如：$x_1^2 + x_2^2 + \cdots + x_n^2$
25. 竖直对齐的省略号，符号：`\vdots`，如：$\vdots$
26. 斜对齐的省略号，符号：`\ddots`，如：$\ddots$

各种希腊字母：

|    A `A`    |  α `\alhpa`  |    B `B`     |  β `\beta`   |
| :---------: | :----------: | :----------: | :----------: |
| Γ `\Gamma`  |  γ `\gamma`  |  Δ `\Delta`  |  δ `\delta`  |
|    E `E`    | ϵ `\epsilon` |    Z `Z`     |  ζ `\zeta`   |
|    H `H`    |   η `\eta`   |  Θ `\Theta`  |  θ `\theta`  |
|    I `I`    |  ι `\iota`   |    K `K`     |  κ `\kappa`  |
| Λ `\Lambda` | λ `\lambda`  |    M `M`     |   μ `\mu`    |
|    N `N`    |    ξ`\xi`    |   ν `\nu`    |   Ξ `\Xi`    |
|    O `O`    | ο `\omicron` |   Π `\Pi`    |   π `\pi`    |
|    T `T`    |   τ `\tau`   | Υ `\Upsilon` | υ `\upsilon` |
|    P `P`    |   ρ `\rho`   |  Σ `\Sigma`  |  σ `\sigma`  |
|    T `T`    |   τ `\tau`   | Υ `\Upsilon` | υ`\upsilon`  |
|  Φ `\Phi`   |   ϕ `\phi`   |    X `X`     |   χ `\chi`   |
|  Ψ `\Psi`   |   ψ `\psi`   |    Ω `\v`    |  ω `\omega`  |

  

  

 

  









