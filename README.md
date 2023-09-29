|这个作业属于哪个课程|[软件工程](https://bbs.csdn.net/forums/ssynkqtd-05)| 
|--    |--    |
|这个作业要求在哪里|[实践第一次作业](https://bbs.csdn.net/topics/617294583)|
|这个作业的目标|完成具有可视化界面的计算器|
|博客连接|[第一次作业](https://bbs.csdn.net/topics/617335676)   |

[TOC]
 
 
 

 
 
## 1.完成一个具有可视化界面的计算器。
 ![](https://pic1.zhimg.com/v2-88856d6a570b0f046c622a933a76cdd8_b.webp)

## 2.Gitcode项目地址
 
 [源码地址](https://github.com/bloon456/calculator)
 
## 3.PSP表格
 

| PSP| 	Personal Software Process Stages |预估耗时（分钟） |实际耗时（分钟） |
| ------- | ------- | ------- | ------- |
|Planning |计划     |    20    |    15     |
|•Estimate    | • 估计这个任务需要多少时间     |   10      |   10  |
|  Development     |开发         |     450    |     400    |
| • Analysis     |• 需求分析 (包括学习新技术）         |     240    |   300      |
| • Design Spec     |• 生成设计文档       |    15     |   15      |
| • Design Review     |• 设计复审     |   30      |      30   |
|• Coding Standard    |• 代码规范 (为目前的开发制定合适的规范) |    15     |  15       |
| • Design     |• 具体设计        |   60      |    60     | 
|• Coding    |• 具体编码        |     300    |     240    | 
|• Code Review     |• 代码复审        |  40       |    60     | 
|• Test   |• 测试（自我测试，修改代码，提交修改）        |    60     |   240      | 
|Reporting    |报告        |   60      |    30     | 
|• Test Repor  | • 测试报告   |    30     |  30   | 
|• Size Measurement   |• 计算工作量    |  20       |    20 | 
|• Postmortem & Process Improvement Plan | •事后总结, 并提出过程改进计划   |   30      |    20 | 
|   | 合计     |   1380      |  1185   | 

 
## 3.解题思路描述
 完成一个可视化界面的计算器
 
学习如何实现可视化界面，科学计算器包含的功能如何实现，可以在网站中搜索相关资料。

用HTML+CSS+JS可以编写出比较美观的界面

由于是第一次用HTMl编写代码，有很多不懂的地方，所以需要搜索学习如何编写HTML代码框架，实现计算器各种功能。

用JS实现计算器的各种功能

在https://codepen.io/accounts/signup/user/free/
中编写HTML+CSS+JS代码比较便捷，可以实时观察生成界面

在网站https://neumorphism.io/#decece
可以选择喜欢的神经拟液态显示效果，能快速便捷地实现较美观的界面设计，非常方便！

用HTML Executable 4.9软件生成exe文件的

## 4.接口设计和实现过程
#### 用HTML定义基本结构
     
创建计算器所需的按钮
#### 在CSS中设计界面显示效果

我用的是神经拟态的效果，看起来比较美观

#### 在JS中实现计算器的各种功能

主要通过以下函数接口实现

````javascript
//输出框
function append(value)
{ ... }
//清空
function clearall() 
{ ... }
//正负号
function tog() 
{ ... }
//三角函数
function sin() 
{ ... }
function cos() 
{ ... }
function tan() 
{ ... }
function power() 
{ ... }
function exp() 
{ ... }
function squa() 
{ ... }
````

## 5.关键代码展示

#### HTML和CSS实现界面设计

以下为HTML的代码,注意clear，del，calculate 按键需要额外定义类别，实现颜色区分
````html
<div class="calculator">
  <input type="text" id="display" readonly>
  <div class="buttons">
    <button class="clear-button" onclick="clearall()">C</button>
  		...
    <button class="delete-button" onclick="delLast()">Del</button>
    	...
    <button onclick="append('7')">7</button>
    	...
	<button class="calculate-button" onclick="calculate()">=</button>
  </div>
</div>

````
以下为CSS代码
````css
.calculator 
{
  width: 600px;
  margin: auto;
  padding: 10px;
  border: none;
  border-radius: 20px;
 background-color: #e8c9c9;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.2), inset 0 0 10px rgba(0, 0, 0, 0.1);
}

#display 
{
  width: 96.5%;
  height: 60px;
  margin-bottom: 10px;
  padding: 10px;
  font-size: 30px;
  border: none;
  border-radius: 20px;
  background-color:#ffe5e5;
  box-shadow: 5px 5px 20px rgba(0, 0, 0, 0.1);
}

.buttons 
{
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  gap: 10px;
}

button 
{
  width: 80px;
  height: 80px;
  font-size: 24px;
  background-color:#e7dfdf;
  border: none;
  border-radius: 50%;
  box-shadow: 5px 5px 20px rgba(0, 0, 0, 0.1);
  outline: none;
  cursor: pointer;
  transition: all 0.3s ease;
}

button.clear-button
{
background-color:lightblue;
}

button.calculate-button
{
  background-color:lightblue;
}
button.delete-button
{
  background-color:#f46666;
}

button:hover 
{
  transform: scale(1.05);
  box-shadow: 5px 5px 20px rgba(0, 0, 0, 0.2);
}

button:active 
{
  transform: scale(0.95);
  box-shadow: 5px 5px 20px rgba(0, 0, 0, 0.1);
}

button.operator 
{
  background-image: radial-gradient(circle at center, #ff8474, #e84a5f);
  color: #fff;
}

button.operator:hover 
{
  background-image: radial-gradient(circle at center, #e84a5f, #ff8474);
}

button.operator:active 
{
  background-image: radial-gradient(circle at center, #ff3c3c, #d73737);
}

````
完成界面如下
![](https://pic2.zhimg.com/80/v2-283861057ea5ca07db3190f00f547df1_1440w.webp)

#### 用JS实现科学计算器功能

````javascript
//输出框
function append(value)
{
  const display = document.getElementById('display');
  let currentValue = display.value;
 
  //第一个不能为右括号
  if(currentValue === ''&&value === ')')
    {
      return;
    }
  
   // 第一个可以为左括号
  if (currentValue === '' && value === '(') 
    {
      currentValue += '(';
    }
  
  //左括号的情况
  else if (value === '(')
    { //当前是右括号则不可以输出‘（’ 
      if(currentValue.slice(-1)===')')
      {
        return;
      }
      //若当前的值是不是数字可以输出‘（’
      if (isNaN(currentValue.slice(-1)) ) 
      {
        currentValue += '(';
      } 
    
    }
  
  //右括号的情况
   else if (value === ')')
    {
    // 检查当前值是否以数字结尾，若前一个为右括号也能输出
      if (!isNaN(currentValue.slice(-1))||currentValue.slice(-1) === ')') 
      {
        currentValue += ')';
      }
     
    }
  
  // 其他情况
  else 
  {
     // 若连续点击符号使新符号替代旧符号。且前一个符号不为右括号
      //若前一个为右括号，则正常输出
      if(currentValue.slice(-1) === ')'&&isNaN(value))
        {
           currentValue += value;
        }
      //否则替代
      else if ( isNaN(currentValue.slice(-1))&&isNaN(value)) 
         {
    
           currentValue = currentValue.slice(0, -1) + value;
         } 
      //若前一个为左括号，则覆盖左括号
      else if ( currentValue.slice(-1) === '('&&isNaN(value)) 
         {
    
           currentValue = currentValue.slice(0, -1) + value;
         } 
    
       // 否则，在结果输出框中追加新的值
      else 
         {
            currentValue += value;
         }
  }

   
  display.value = currentValue;
}
// 删除最后一个字符
function delLast() 
{
  let display = document.getElementById("display");
  let currentValue = display.value;

  if (currentValue.length > 0) 
  {
      currentValue = currentValue.slice(0, -1);
      display.value = currentValue;
  }
}
//计算结果
function calculate() 
{
  const display = document.getElementById('display');
  const equation = display.value;

  try 
  {
      const result = eval(equation);
      display.value = result;
  }
  catch (error) 
  {
      display.value = 'error';
  }
  
}
//清空
function clearall() 
{
  document.getElementById('display').value = '';
}
//正负号
function tog() 
{
  const display = document.getElementById('display');
  let value = display.value;

  if (value.includes('-')) 
  {
      value = value.replace('-', '');
  } 
  else 
  {
      value = '-' + value;
  }

  display.value = value;
}
//三角函数
function sin() 
{
  const display = document.getElementById('display');
  const value = parseFloat(display.value);
  
  if (!isNaN(value)) 
  {
      const result = Math.sin(value);
      display.value = result;
  } 
  else 
  {
      display.value = 'Invalid input';
  }
}

function cos() 
{
  const display = document.getElementById('display');
  const value = parseFloat(display.value);
  
  if (!isNaN(value)) 
  {
      const result = Math.cos(value);
      display.value = result;
  } 
  else 
  {
      display.value = 'Invalid input';
  }
}

function tan() 
{
  const display = document.getElementById('display');
  const value = parseFloat(display.value);
  
  if (!isNaN(value)) 
  {
      const result = Math.tan(value);
      display.value = result;
  } 
  else 
  {
      display.value = 'Invalid input';
  }
}

function power() 
{
  const display = document.getElementById('display');
  const value = parseFloat(display.value);
  const exponent = parseFloat(prompt('Enter the exponent:'));

  if (!isNaN(value) && !isNaN(exponent)) 
  {
      const result = Math.pow(value, exponent);
      display.value = result;
  } 
  else 
  {
      display.value = 'Invalid input';
  }
}

function exp() 
{
  const display = document.getElementById('display');
  const value = parseFloat(display.value);

  if (!isNaN(value)) 
  {
      const result = Math.pow(value, 2);
      display.value = result;
  } 
  else 
  {
      display.value = 'Invalid input';
  }
}

function squa() 
{
  const display = document.getElementById('display');
  const value = parseFloat(display.value);

  if (!isNaN(value)) 
  {
      if (value < 0)
      {
        display.value = 'Invalid input';
      } 
      else 
      {
        const result = Math.sqrt(value);
        display.value = result;
      }
  } 
  
  else 
  {
      display.value = 'Invalid input';
  }
}

````
## 6.性能改进
 
一开始计算器的功能只有加减乘除，为避免“-+*/”多符号输出的情况，只需要新符号覆盖旧符号，但在添加了左右括号后，需要考虑的情况变多了，为了一定程度上模拟电脑上的计算器，我在append(value)编写了如下代码
````

function append(value)
{
  const display = document.getElementById('display');
  let currentValue = display.value;
 
  //第一个不能为右括号
  if(currentValue === ''&&value === ')')
    {
      return;
    }
  
   // 第一个可以为左括号
  if (currentValue === '' && value === '(') 
    {
      currentValue += '(';
    }
  
  //左括号的情况
  else if (value === '(')
    { //当前是右括号则不可以输出‘（’ 
      if(currentValue.slice(-1)===')')
      {
        return;
      }
      //若当前的值是不是数字可以输出‘（’
      if (isNaN(currentValue.slice(-1)) ) 
      {
        currentValue += '(';
      } 
    
    }
  
  //右括号的情况
   else if (value === ')')
    {
    // 检查当前值是否以数字结尾，若前一个为右括号也能输出
      if (!isNaN(currentValue.slice(-1))||currentValue.slice(-1) === ')') 
      {
        currentValue += ')';
      }
     
    }
  
  // 其他情况
  else 
  {
     // 若连续点击符号使新符号替代旧符号。且前一个符号不为右括号
      //若前一个为右括号，则正常输出
      if(currentValue.slice(-1) === ')'&&isNaN(value))
        {
           currentValue += value;
        }
      //否则替代
      else if ( isNaN(currentValue.slice(-1))&&isNaN(value)) 
         {
    
           currentValue = currentValue.slice(0, -1) + value;
         } 
      //若前一个为左括号，则覆盖左括号
      else if ( currentValue.slice(-1) === '('&&isNaN(value)) 
         {
    
           currentValue = currentValue.slice(0, -1) + value;
         } 
    
       // 否则，在结果输出框中追加新的值
      else 
         {
            currentValue += value;
         }
  }

   
  display.value = currentValue;
}
````
以下为具体功能实例
![](https://pic2.zhimg.com/v2-ef4063a4bd374b2d4a8c0462f8c53571_b.jpg)

## 7.异常处理
 
 在函数calculate()中用try和catch实现异常处理
 
````
try 
  {
      const result = eval(equation);
      display.value = result;
  }
  catch (error) 
  {
      display.value = 'error';
  }
 ````
 在数学函数中若输入不为数字则输出“Invalid input”
 
 /0显示“Infinity”
 
## 8.心得体会
 
在本次软工作业中我第一次用HTML+CSS+JS实现了可视化计算器，学习了很多新知识，一开始找了很多资料，看别人是用什么来写计算器，后面觉得还是用html的界面比较好看，花了许多实际设计了一个界面，在codepen看着界面实时效果显示还是挺有趣的。在实现过程中考虑了符号覆盖的问题，不断修改代码，测试，希望做出来的计算器和计算机自带的差不多。由于能力有限所以三角函数，幂运算只能先输入数据再点击相应按钮输出结果，没有把过程显示出来，希望后面有时间能再改进一下。还有单元测试做了很久不知道因为什么原因一直没法运行，心态不是很好，后面有空再做吧。

