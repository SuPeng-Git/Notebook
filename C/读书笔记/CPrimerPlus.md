# C语言概述

C语言：关键字、标识符、运算符和数据

C语言中的6种语句：标号语句、复合语句、表达式语句、选择语句、迭代语句、跳转语句

```c
//first.c
#include <stdio.h>
int main(void)				 	/* 一个简单的C程序 */
{
    int num;                     /* 定义一个名为num的变量 */
    num = 1;                     /* 为num赋一个值 */

    printf("hello world\n");

    return 0;
}
```

## 程序细节

1. `#include`指令和头文件——一种“拷贝—粘贴”操作

通常，C编译器在编译前会对源代码做一些准备工作，即预处理（*`preprocessing`*）。`#include`这行代码是一条C预处理器指令（`preprocessor directive`）。

所有的C编译器软件包都提供 `stdio.h`文件。该文件中包含了供编译器使用的输入和输出函数（如，`printf()`）信息。该文件名的含义是标准输入/输出头文件。通常，在C程序顶部的信息集合被称为头文件（*`header`*）。

\#include中的#符号表明，C预处理器在编译器接手之前处理这条指令。

2. `main()`函数

函数是C程序的基本模块。

C程序一定从 `main()`函数开始执行（目前不必考虑例外的情况）。除了 `main()`函数，你可以任意命名其他函数，而且 `main()`函数必须是开始的函数。

3. 注释

C语言提供两种注释风格：

```c
//这是一条注释
/*这是一条注释*/
```

4. 花括号、函数体和块

一般而言，所有的C函数都使用花括号标记函数体的开始和结束。这是规定，不能省略。

花括号还可用于把函数中的多条语句合并为一个单元或块。

5. 声明

```c
int num;	//声明一个int类型变量
```

声明是C语言最重要的特性之一。在该例中，声明完成了两件事。其一，在函数中有一个名为 `num`的变量（*`variable`*）。其二，`int`表明 `num`是一个整数（即，没有小数点或小数部分的数）。`int`是一种数据类型。编译器使用这些信息为 `num`变量在内存中分配存储空间。分号在C语言中是大部分语句和声明的一部分，一般代表着一个语句的结束。

`int`是C语言的一个关键字（*`keyword`*），表示一种基本的C语言数据类型。关键字是语言定义的单词，不能做其他用途。

示例中的 `num`是一个标识符（*`identifier`*），也就是一个变量、函数或其他实体的名称。因此，**声明把特定标识符与计算机内存中的特定位置联系起来，同时也确定了存储在某位置的信息类型或数据类型。**

在C语言中，所有变量都必须先声明才能使用。这意味着必须列出程序中用到的所有变量名及其类型。以前的C语言，还要求把变量声明在块的顶部，其他语句不能在任何声明的前面。C99和C11遵循C++的惯例，可以把声明放在块中的任何位置。尽管如此，首次使用变量之前一定要先声明它。

- 数据类型

C语言可以处理多种类型的数据，如整数、字符和浮点数。把变量声明为整型或字符类型，计算机才能正确地存储、读取和解释数据。

- 命名

给变量命名时要使用有意义的变量名或标识符。如果变量名无法清楚地表达自身的用途，可在注释中进一步说明。这是一种良好的编程习惯和编程技巧。

C99和C11允许使用更长的标识符名，但是编译器只识别前63个字符。

可以用小写字母、大写字母、数字和下划线（_）来命名。而且，名称的第1个字符必须是字母或下划线，不能是数字。

C语言的名称区分大小写，即把一个字母的大写和小写视为两个不同的字符。

C99之前的标准要求把声明都置于块的顶部，这样规定的好处是：把声明放在一起更容易理解程序的用途。C99允许在需要时才声明变量，这样做的好处是：在给变量赋值之前声明变量，就不会忘记给变量赋值。

6. 赋值

```c
num = 1;		//赋值表达式语句
```

赋值是C语言的基本操作之一。该行代码的意思是“把值 `1`赋给变量 `num`”。在执行 `int num;`声明时，编译器在计算机内存中为变量 `num`预留了空间，然后在执行这行赋值表达式语句时，把值存储在之前预留的位置。可以给 `num`赋不同的值，这就是 `num`之所以被称为变量（*`variable`*）的原因。注意，该赋值表达式语句从右侧把值赋到左侧。另外，该语句以分号结尾。

7. `printf()`函数

```c
printf("hello world\n");
```

示例把 `hello world`传递给 `printf()`函数。该信息被称为参数，或者更确切地说，是函数的实际参数（*`actual argument`*）。〔在C语言中，实际参数（简称实参）是传递给函数的特定值，形式参数（简称形参）是函数中用于存储值的变量。〕

示例演示了在C语言中如何调用函数。只需输入函数名，把所需的参数填入圆括号即可。当程序运行到这一行时，控制权被转给已命名的函数（该例中是 `printf()`）。函数执行结束后，控制权被返回至主调函数（*`calling function`*），该例中是 `main()`。

`\n`组合（依次输入这两个字符）代表一个换行符（*`newline character`*）。

换行符是一个转义序列（*`escape sequence`*）。转义序列用于代表难以表示或无法输入的字符。如，`\t`代表Tab键，`\b`代表Backspace键（退格键）。每个转义序列都以反斜杠字符（`\`）开始。

`%`提醒程序，要在该处打印一个变量，`d`表明把变量作为十进制整数打印。`printf()`函数名中的 `f`提醒用户，这是一种格式化打印函数。`printf()`函数有多种打印变量的格式，包括小数和十六进制整数。

8. `return`语句

`int main(void)`中的 `int`表明 `main()`函数应返回一个整数。C标准要求 `main()`这样做。有返回值的C函数要有 `return`语句。该语句以 `return`关键字开始，后面是待返回的值，并以分号结尾。如果遗漏 `main()`函数中的 `return`语句，程序在运行至最外面的右花括号（`}`）时会返回 `0`。因此，可以省略 `main()`函数末尾的 `return`语句。但是，不要在其他有返回值的函数中漏掉它。因此，强烈建议读者养成在 `main()`函数中保留 `return`语句的好习惯。在这种情况下，可将其看作是统一代码风格。但对于某些操作系统（包括 `Linux`和 `UNIX`），`return`语句有实际的用途。

## 简单程序的结构

程序由一个或多个函数组成，必须有 `main()`函数。函数由函数头和函数体组成。函数头包括函数名、传入该函数的信息类型和函数的返回类型。通过函数名后的圆括号可识别出函数，圆括号里可能为空，可能有参数。函数体被花括号括起来，由一系列语句、声明组成。

简而言之，一个简单的C程序的格式如下：

```c
#include <stdio.h>
int main(void)
{
     //语句
     return 0;
}
```

## 提高程序可读性的技巧

- 选择有意义的函数名和写注释。注意，使用这两种技巧时应相得益彰，避免重复啰嗦。
- 在函数中用空行分隔概念上的多个部分。C语言并未规定一定要使用空行，但是多使用空行能提高程序的可读性。
- 每条语句各占一行。同样，这也不是C语言的要求。C语言的格式比较自由，可以把多条语句放在一行，也可以每条语句独占一行。
- 程序在开始处有一条注释（使用新的注释风格），给出了文件名和程序的目的。

## 调试程序

程序的错误通常叫作bug，找出并修正错误的过程叫作调试（*debug*）。

如果不遵循C语言的规则就会犯语法错误。语义错误是指意思上的错误。

编译器无法检测语义错误，因为这类错误并未违反C语言的规则。编译器无法了解你的真正意图，所以你只能自己找出这些错误。

通过逐步跟踪程序的执行步骤，并记录每个变量，便可监视程序的状态。程序状态（*program state*）是在程序的执行过程中，某给定点上所有变量值的集合。它是计算机当前状态的一个快照。

定位语义错误的一种方法是：自己模拟计算机逐步执行程序。定位语义错误的另一种方法是：在程序中的关键点插入额外的 `printf()`语句，以监视指定变量值的变化。通过查看值的变化可以了解程序的执行情况。对程序的执行满意后，便可删除额外的 `printf()`语句，然后重新编译。

## 关键字和保留标识符

在表中所列的C语言关键字中，粗体表示的是 `C90`标准新增的关键字，斜体表示的 `C99`标准新增的关键字，粗斜体表示的是 `C11`标准新增的关键字。

| `auto`      | `extern`   | `short`        | `while`                |
| ----------- | ---------- | -------------- | ---------------------- |
| `break`     | `float`    | **`signed`**   | ***`_Alignas`***       |
| `case`      | `for`      | `sizeof`       | ***`_Alignof`***       |
| `char`      | `goto`     | `static`       | ***`_Atomic`***        |
| **`const`** | `if`       | `struct`       | ***`_Bool`***          |
| `continue`  | *`inline`* | `switch`       | ***`_Complex`***       |
| `default`   | `int`      | `typedef`      | ***`_Generic`***       |
| `do`        | `long`     | `union`        | ***`_Imaginary`***     |
| `double`    | `register` | `unsigned`     | ***`_Noreturn`***      |
| `else`      | `restrict` | **`void`**     | ***`_Static_assert`*** |
| **`enum`**  | `return`   | **`volatile`** | ***`_Thread_local`***  |

如果使用关键字不当（如，用关键字作为变量名），编译器会将其视为语法错误。还有一些保留标识符（*`reserved identifier`*），C语言已经指定了它们的用途或保留它们的使用权，如果你使用这些标识符来表示其他意思会导致一些问题。因此，尽管它们也是有效的名称，不会引起语法错误，也不能随便使用。保留标识符包括那些以下划线字符开头的标识符和标准库函数名，如 `printf()`。

## 本章小结

C程序由一个或多个C函数组成。每个C程序必须包含一个 `main()`函数，这是C程序要调用的第 `1`个函数。简单的函数由函数头和后面的一对花括号组成，花括号中是由声明、语句组成的函数体。

在C语言中，大部分语句都以分号结尾。声明语句为变量指定变量名，并标识该变量中存储的数据类型。变量名是一种标识符。赋值表达式语句把值赋给变量，或者更一般地说，把值赋给存储空间。函数表达式语句用于调用指定的已命名函数。调用函数执行完毕后，程序会返回到函数调用后面的语句继续执行。

`printf()`函数用于输出想要表达的内容和变量的值。

一门语言的语法是一套规则，用于管理语言中各有效语句组合在一起的方式。语句的语义是语句要表达的意思。编译器可以检测出语法错误，但是程序里的语义错误只有在编译完之后才能从程序的行为中表现出来。检查程序是否有语义错误要跟踪程序的状态，即检查程序每执行一步后所有变量的值。

最后，关键字是C语言的词汇。

# 数据和C

只存储单个值的变量有时也称为**标量变量**（`scalar variable`）。



# 字符串和格式化输入/输出

# 运算符、表达式和语句

# C控制语句：循环

# C控制语句：分支和跳转

# 字符输入/输出和输入验证

# 函数

# 数组和指针

## 数组

一组数据的集合称为**数组（Array）**，它所包含的每一个数据叫做数组元素（`Element`），所包含的数据的个数称为数组长度（`Length`），例如 `int a[4];`就定义了一个长度为4的整型数组，名字是 `a`。方括号（`[]`）表明 `a`是数组，方括号中的数字表明数组中的元素个数。

数组中的每个元素都有一个序号，这个序号从0开始计数，称为下标（`Index`）。使用数组元素时，指明下标即可，形式为：

```c
typename arrayName[index];
```

`typename`为数组类型， `arrayName` 为数组名称，`index` 为下标。例如，`a[0]` 表示第0个元素，`a[3]` 表示第3个元素。

**数组是一个整体，它的内存是连续的**；也就是说，数组元素之间是相互挨着的，彼此之间没有一点点缝隙。

### 初始化数组

与普通变量类似，在使用数组元素之前，必须先给它们赋初值。在给数组元素初始化之前数组元素的值是不确定的（对自动存储类型的数组元素是这样的）。C使用新的语法来初始化数组，如下所示：

```c
int main(void)
{
     int powers[8] = {1,2,4,6,8,16,32,64}; /* 从ANSI C开始支持这种初始化 */
     ...
}
```

如上所示，用以逗号分隔的值列表（用花括号括起来）来初始化数组，各值之间用逗号分隔。在逗号和值之间可以使用空格。

> 如果编译器不支持ANSI，那么这种形式视为语法错误，可以再数组声明前加上关键字`static`解决此问题。

如果部分初始化数组，剩余的元素就会被初始化为 `0`。

```c
int array[10] = {1, 1, 2, 3, 5}
```

如果初始化数组时省略方括号中的数字，编译器会根据初始化列表中的项数来确定数组的大小。

```c
int array[] = {1, 2, 3, 5};
```

在对数组进行遍历时，由于人工计算容易出错，所以可以让计算机来计算数组的大小。整个数组的大小除以单个元素的大小的商即为数组元素的个数。`sizeof(array)`是整个数组的大小（以字节为单位），`sizeof(array[0])`是数组中一个元素的大小（以字节为单位）。自动计数的弊端：无法察觉初始化列表中的项数有误。

```c
 for (index = 0; index < sizeof(array) / sizeof array[0]; index++)
```

> **注意　使用const声明数组**
>
> 有时需要把数组设置为只读。这样，程序只能从数组中检索值，不能把新值写入数组。要创建只读数组，应该用 `const`声明和初始化数组。

### 指定初始化器（C99）

C99增加了一个新特性：指定初始化器（*designated initializer*）。可以在初始化列表中使用带方括号的下标指明待初始化的元素：

```c
int arr[6] = {[5] = 212}; // 把arr[5]初始化为212
```

对于一般的初始化，在初始化一个元素后，未初始化的元素都会被设置为 `0`。

```c
int days[MONTHS] = { 31, 28, [4] = 31, 30, 31, [1] = 29 };
```

第一，如果指定初始化器后面有更多的值，如该例中的初始化列表中的片段：`[4] = 31,30,31`，那么后面这些值将被用于初始化指定元素后面的元素。也就是说，在 `days[4]`被初始化为 `31`后，`days[5]`和 `days[6]`将分别被初始化为 `30`和 `31`。

第二，如果再次初始化指定的元素，那么最后的初始化将会取代之前的初始化。例如，程序清单10.5中，初始化列表开始时把 `days[1]`初始化为 `28`，但是 `days[1]`又被后面的指定初始化 `[1] = 29`初始化为 `29`。

如果未指定元素大小，编译器会把数组的大小设置为足够装得下初始化的值。

### 给数组元素赋值

声明数组后，可以借助数组下标（或索引）给数组元素赋值。

C不允许把数组作为一个单元赋给另一个数组，除初始化以外也不允许使用花括号列表的形式赋值。

### 数组边界

数组元素的编号从0开始。最好是在声明数组时使用符号常量来表示数组的大小。在使用数组时，要防止数组下标超出边界。

编译器不会检查数组下标是否使用得当。在C标准中，使用越界下标的结果是未定义的。这意味着程序看上去可以运行，但是运行结果很奇怪，或异常中止。

### 指定数组的大小

在C99标准之前，声明数组时只能在方括号中使用整型常量表达式。所谓整型常量表达式，是由整型常量构成的表达式。`sizeof`表达式被视为整型常量，但是（与C++不同）`const`值不是。另外，表达式的值必须大于 `0`。

```c
int n = 5;
int m = 8;
float a1[5];                  // 可以
float a2[5*2 + 1];            //可以
float a3[sizeof(int) + 1];    //可以
float a4[-4];                 // 不可以，数组大小必须大于0
float a5[0];                  // 不可以，数组大小必须大于0
float a6[2.5];                // 不可以，数组大小必须是整数
float a7[(int)2.5];           // 可以，已被强制转换为整型常量
float a8[n];                  // C99之前不允许
float a9[m];                  // C99之前不允许
```

上面的注释表明，以前支持C90标准的编译器不允许后两种声明方式。而C99标准允许这样声明，这创建了一种新型数组，称为变长数组（*variable-length array*）或简称VLA（C11放弃了这一创新的举措，把VLA设定为可选，而不是语言必备的特性）。VLA有一些限制，例如，声明VLA时不能进行初始化。

### 二维数组

初始化二维数组是建立在初始化一维数组的基础上。首先，初始化一维数组如下：

```c
sometype ar1[5] = {val1, val2, val3, val4, val5};
```

初始化二维数组 `rain`，要用逗号分隔5个这样的数值列表：

```c
sometype ar1[5][5] = {
    {val1, val2, val3, val4, val5},
    {val1, val2, val3, val4, val5},
    {val1, val2, val3, val4, val5},
    {val1, val2, val3, val4, val5},
    {val1, val2, val3, val4, val5}
};
```

初始化时也可省略内部的花括号，只保留最外面的一对花括号。只要保证初始化的数值个数正确，初始化的效果与上面相同。但是如果初始化的数值不够，则按照先后顺序逐行初始化，直到用完所有的值。后面没有值初始化的元素被统一初始化为 `0`。

如果对全部元素都赋初值（即提供全部初始数据），则定义数组时对第一位的长度可以不指定，但第二维的长度不能省。也可以只对部分元素赋初值而省略第一维的长度，但应分行赋初值。

## 指针

指针的定义：指针是一个特殊的变量，它里面存储的数值被解释成为内存里的一个地址。

举一个变相使用指针的例子：数组名是数组首元素的地址。也就是说，如果 `flizny`是一个数组，下面的语句成立：

```c
flizny == &flizny[0]; // 数组名是该数组首元素的地址
```

`flizny`和 `&flizny[0]`都表示数组首元素的内存地址（`&`是地址运算符）。两者都是常量，在程序的运行过程中，不会改变。但是，可以把它们赋值给指针变量，然后可以修改指针变量的值。

在C中，指针加 `1`指的是增加一个存储单元。对数组而言，这意味着加 `1`后的地址是下一个元素的地址，而不是下一个字节的地址。这是为什么必须声明指针所指向对象类型的原因之一。只知道地址不够，因为计算机要知道存储对象需要多少字节（即使指针指向的是标量变量，也要知道变量的类型，否则*`pt`就无法正确地取回地址上的值）。

- 指针的值是它所指向对象的地址。地址的表示方式依赖于计算机内部的硬件。许多计算机（包括PC和Macintosh）都是按字节编址，意思是内存中的每个字节都按顺序编号。这里，一个较大对象的地址（如 `double`类型的变量）通常是该对象第一个字节的地址。
- 在指针前面使用 `*`运算符可以得到该指针所指向对象的值。
- 指针加1，指针的值递增它所指向类型的大小（以字节为单位）。

数组的指针表示法：

```c
type_name array[len] = { ... };
int index;		//index < len
```

这里，`array`是数组首元素的地址，`array + index`是元素 `array[index]`的地址，而*`(arary + index)`则是该元素的值，相当于 `array[index]`。

### 指针的一些基本操作

- **赋值：**可以把地址赋给指针。
- **解引用：***运算符给出指针指向地址上存储的值。
- **取址：**和所有变量一样，指针变量也有自己的地址和值。
- **指针与整数相加：**可以使用 `+`运算符把指针与整数相加，或整数与指针相加。无论哪种情况，整数都会和指针所指向类型的大小（以字节为单位）相乘，然后把结果与初始地址相加。
- **递增指针：**递增指向数组元素的指针可以让该指针移动至数组的下一个元素。
- **指针减去一个整数：**可以使用 `-`运算符从一个指针中减去一个整数。指针必须是第1个运算对象，整数是第2个运算对象。该整数将乘以指针指向类型的大小（以字节为单位），然后用初始地址减去乘积。
- **递减指针**
- **指针求差：**可以计算两个指针的差值。通常，求差的两个指针分别指向同一个数组的不同元素，通过计算求出两元素之间的距离。差值的单位与数组类型的单位相同。
- **比较：**使用关系运算符可以比较两个指针的值，前提是两个指针都指向相同类型的对象。

> 注意：
>
> 一定要牢记一点：千万不要解引用未初始化的指针。创建一个指针时，系统只分配了存储指针本身的内存，并未分配存储数据的内存。因此，在使用指针之前，必须先用已分配的地址初始化它。

### 指向const的指针

```c
const type_name * ptr;
```

**特性：**指向 `const`的指针不能用于改变值。

**用处：**保护数组中的数据。如果函数的意图不是修改数组中的数据内容，那么在函数原型和函数定义中声明形式参数时应使用关键字 `const`。

关于指针赋值和 `const`需要注意一些规则。

- 首先，把 `const`数据或非 `const`数据的地址初始化为指向 `const`的指针或为其赋值是合法的。
- 然而，只能把非 `const`数据的地址赋给普通指针，否则，通过指针就能改变 `const`数组中的数据。C标准规定，使用非 `const`标识符修改 `const`数据导致的结果是未定义的。

### const指针

```c
type_name * const ptr = ...;
```

上述语句声明并初始化一个不能指向别处的指针

**特性：**这种指针可以修改它所指向的值，但是它只能指向初始化时设置的地址。

在创建指针时还可以使用 `const`两次，该指针既不能更改它所指向的地址，也不能修改指向地址上的值：

```c
double rates[5] = {88.99, 100.12, 59.45, 183.11, 340.5};
const double * const pc = rates;
pc = &rates[2];     //不允许
*pc = 92.99;        //不允许
```

**C const和C++ const**

C和C++中 `const`的用法很相似，但是并不完全相同。区别之一是，C++允许在声明数组大小时使用 `const`整数，而C却不允许。区别之二是，C++的指针赋值检查更严格：

```c
const int y;
const int * p2 = &y;
int * p1;
p1 = p2;　// C++中不允许这样做，但是C可能只给出警告
```

C++不允许把 `const`指针赋给非 `const`指针。而C则允许这样做，但是如果通过 `p1`更改 `y`，其行为是未定义的。

### 指针与二维数组

`C`语言传递多维数组的传统方法是把数组名（即数组的地址）传递给类型匹配的指针形参。声明这样的指针形参要指定所有的数组维度，除了第 `1`个维度。传递的第 `1`个维度通常作为第 `2`个参数。

## 变长数组（VLA）

C99新增了变长数组（*variable-length array*，VLA），允许使用变量表示数组的维度。如下所示：

```c
int quarters = 4;
int regions = 5;
double sales[regions][quarters];    // 一个变长数组（VLA）
```

变长数组有一些限制。变长数组必须是自动存储类别，这意味着无论在函数中声明还是作为函数形参声明，都不能使用 `static`或 `extern`存储类别说明符。而且，不能在声明中初始化它们。最终，C11把变长数组作为一个可选特性，而不是必须强制实现的特性。

> **注意　变长数组不能改变大小**
>
> 变长数组中的“变”不是指可以修改已创建数组的大小。一旦创建了变长数组，它的大小则保持不变。这里的“变”指的是：在创建数组时，可以使用变量指定数组的维度。

声明一个带二维变长数组参数的函数，如下所示：

```c
int sum2d(int rows, int cols, int ar[rows][cols]); // ar是一个变长数组（VLA）
```

注意前两个形参（`rows`和 `cols`）用作第3个形参二维数组 `ar`的两个维度。因为 `ar`的声明要使用 `rows`和 `cols`，所以在形参列表中必须在声明 `ar`之前先声明这两个形参。

需要注意的是，在函数定义的形参列表中声明的变长数组并未实际创建数组。和传统的语法类似，变长数组名实际上是一个指针。这说明带变长数组形参的函数实际上是在原始数组中处理数组，因此可以修改传入的数组。

C99/C11标准允许在声明变长数组时使用 `const`变量。所以该数组的定义必须是声明在块中的自动存储类别数组。

变长数组还允许动态内存分配，这说明可以在程序运行时指定数组的大小。普通C数组都是静态内存分配，即在编译时确定数组的大小。

## 复合字面量

在C99标准以前，对于带数组形参的函数，情况不同，可以传递数组，但是没有等价的数组常量。C99新增了复合字面量（*compound literal*）。字面量是除符号常量外的常量。发布C99标准的委员会认为，如果有代表数组和结构内容的复合字面量，在编程时会更方便。

对于数组，复合字面量类似数组初始化列表，前面是用括号括起来的类型名。例如，下面是一个普通的数组声明：

```c
int diva[2] = {10, 20};
```

下面的复合字面量创建了一个和 `diva`数组相同的匿名数组，也有两个 `int`类型的值：

```c
(int [2]){10, 20}        // 复合字面量
```

注意，去掉声明中的数组名，留下的 `int [2]`即是复合字面量的类型名。

初始化有数组名的数组时可以省略数组大小，复合字面量也可以省略大小，编译器会自动计算数组当前的元素个数：

```c
(int []){50, 20, 90} // 内含3个元素的复合字面量
```

因为复合字面量是匿名的，所以不能先创建然后再使用它，必须在创建的同时使用它。使用指针记录地址就是一种用法。也就是说，可以这样用：

```c
int * pt1;
pt1 = (int [2]) {10, 20};
```

注意，该复合字面量的字面常量与上面创建的 `diva`数组的字面常量完全相同。与有数组名的数组类似，复合字面量的类型名也代表首元素的地址，所以可以把它赋给指向 `int`的指针。然后便可使用这个指针。例如，本例中*`pt1`是 `10`，`pt1[1]`是 `20`。

还可以把复合字面量作为实际参数传递给带有匹配形式参数的函数：

```c
int sum(const int ar[], int n);
...
int total3;
total3 = sum((int []){4,4,4,5,5,5}, 6);
```

这里，第 `1`个实参是内含 `6`个 `int`类型值的数组，和数组名类似，这同时也是该数组首元素的地址。这种用法的好处是，把信息传入函数前不必先创建数组，这是复合字面量的典型用法。

可以把这种用法应用于二维数组或多维数组。

# 字符串和字符串函数

## 表示字符串和字符串I/O

==字符串==：字符串是以空字符(\0)结尾的char类型数组。

字符串IO函数：==gets()、gets_s()、fgets()、puts()、fputs()、sprintf()==

## 定义字符串

### 1.字符串字面量(字符串常量)

    ==字符串字面量==：用双引号括起来的内容称为字符串字面量或字符串常量。双引号中的字符和编译器自动加入末尾的\0字符，都作为字符串存储在内存中。
    
    从ANSIC标准起，如果字符串字面量之间无间隔，或者用空字符分隔，C会将其视为串联起来的字符串字面量。

例如:

```c
char greeting[50] = "Hello, and""how are" "you"
    				                  "today!";
//等价于代码：
char greeting2[50] = "Hello, and how are you today!"; 
```

    字符串常量属于静态存储类别，这说明如果在函数中使用字符串常量，该字符串智慧被存储一次，在整个程序的生命期内存在，即使函数被多次调用。用双引号括起来的内容被视为指向该字符串存储位置的指针。

```c
#include "stdio.h"
int main(void)
{
    printf("%s, %p, %c\n", "we", "are", *"space farers");
  
    return 0;
}
```

程序输出：

```c
we, 00007ff69cdea050, s
```

### 2.char数组定义字符串

***定义字符串数组时，必须让编译器知道需要多少空间***

1. char数组指定长度：

```c
const char m1[40] = "Limit yourself to one line`s worth."
   //const表明不会修改这个字符串
```

在指定数组大小时，要确保数组的元素个数至少比字符串长度多1（为了容纳空字符）。所有未被使用的元素被自动初始化为0（这里的0是char形式的空字符，不是数字字符0。

2. char数组不指定长度：

初始化数组时也可省略字符串数组大小声明，让编译器计算数组的大小。

```c
const char m1[] = "Limit yourself to one line`s worth."
```

让编译器计算数组的大小只能如果创建一个稍后再填充的数组，就必须在声明时指定大小。

```c
int n = 8;
char cookies[n];
char cakes[2+3];
char pies[ 2*sizeof(long double) + 1];
```

### 3.数组和指针

```c
const int ar1[] = "something is pointing at me";
const int *pt1 = "something is pointing at me";
```

通常，字符串都作为可执行文件的一部分存储在数据段中。当程序载入内存时，也载入了程序中的字符串。字符串存储在静态存储区中。但是，程序在开始运行时才会为该数组分配内存。此时才将字符串拷贝到数组。==注意，此时字符串有两个副本。一个是静态内存中的字符串字面量，另一个是存储在ar1数组中的字符串。==

    在数组形式中，ar1是地址常量，是数组首元素的地址。不能更改ar1，如果改变了ar1，则意味着改变了数组存储位置。可以进行类似ar1+1这样的操作，标识数组的下一个元素。但是不允许进行++ar1这样的操作。递增运算符只能用于可修改的左值，不能用于常量。
    
    指针形式(*pt1)也使得编译器为字符串在静态存储区预留29个元素的空间。另外，一旦开始执行程序，它会为指针变量留出一个存储位置，并把字符串的地址存储在指针变量中。该变量最初指向该字符串的首字符，但是它的值是可变的，因此，可以使用递增运算符。
    
    字符串字面量被视为const数据。由于pt1指向这个const数据，所以应该把pt1声明为指向const数据的指针。这意味着不能用pt1改变它所指向的数据，但是仍然可以改变pt1的值（即pt1指向的位置）。

All in all	初始化数组把静态存储区的字符串拷贝到数组中，而初始化指针只把字符串的地址拷贝给指针。

### 4.数组和指针的区别

```c
char  add[] = "重庆"；
char  *sch = "CQUPT"; 
```

初始化字符数组和初始化指针主要的区别是：	数组名add是常量，而指针sch是变量。

- 两者都可以使用数组表示法
- 两者都可以进行指针加法操作
- 只有指针表示法可以进行

### 5.字符串数组

创建一个 字符串数组通常很方便，可以通过数组下标访问多个不同的字符串。

如果要用数组表示一系列待显示的字符串，使用指针数组，因为它比二维字符数组的效率高。但是，指针指向的字符串字面量不可更改；而二维数组中的内容可以更改。所以，如果要改变字符串或为字符串输入预留空间，那就使用二位字符数组。

## 指针和字符串

字符串的绝大多数操作都是通过指针来完成的。

## 字符串输入

将一个字符串读入程序，首先必须预留存储该字符串的空间，然后输入函数获取该字符串。

### 分配空间

字符串输入函数应该在char数组内存中写入字符串；C语言不会在输入字符串的同时计算它的长度并分配内存，所以程序员需要事先分配字符串所需内存。

### gets()函数

**scanf()函数的局限性**：scanf()和转换说明%s只能读取一个单词。

**gets()函数：**：gets()函数读取整行输入，直到遇到换行符，然后丢弃换行符，存储其余字符，并在末尾添加一个空字符使其成为一个C字符串。它经常与puts()函数配对使用，该函数用于显示字符串，并在末尾添加换行符。

```c
#include <stdio.h>
#define STRLEN 81

int main()
{
    char words[STRLEN];

    puts("Enter a string, please.");
    gets(words);
    printf("Your string twice:\n");
    printf("%s\n", words);
    puts(words);
    puts("Done!");

    return 0;
}
```

程序输出：

```c
Enter a string, please.
I want to learn about string theory!
Your string twice:
I want to learn about string theory!
I want to learn about string theory!
Done!
```

**gets()函数局限性**：

gets()函数唯一的参数是words，gets()函数只知道数组开始的地处，并不知道数组中有多少个元素，无法检查数组是否装得下输入行；

如果输入的字符串过长，会导致缓冲区溢出，即多余的字符超出了指定的目标空间；这些多余的字符串很可能擦写程序中的其他数据，会导致程序异常终止。

### fgets()函数


#### fgets()函数和fputs()函数

- fgets()函数的第二个参数指明了读入字符的最大数量。如果该参数是n，那么fgets()将读入n-1个字符，或者读到遇到的第一个换行符为止。
- 如果fgets()读到一个换行符，会把它存储到字符串中。这点与gets()不同，gets()会丢弃换行符。
- fgets()函数的第三个参数指明要读入的文件。如果读入从键盘输入的数据，则以stdin(标准输入)作为参数，该标识符定义在stdio.h中。
- 因为fgets()函数把换行符放在字符串的末尾(假设输入行不溢出)，通常要与fputs()函数配对使用，除非该函数不在字符串末尾添加换行符。
- fputs()函数的第二参数指明它要写入的文件。stdout(标准输出)作为参数则显示在计算机显示器上
- fgets()函数返回指向char的指针。如果一切顺利，该函数返回的地址与传入的第一个参数相同。但是，如果函数读到文件末尾，它返回一个特殊的指针：空指针(null pointer)

```c
#include "stdio.h"
#define SIZE 14
int main(void)
{
    char words[SIZE];
  
    puts("Enter a string, please.");
    fgets(words,SIZE,stdin);
    printf("Your string twice (puts(), then fputs() ):\n");
    puts(words);
    fputs(words, stdout);
    puts("Enter another string, please.");
    fgets(words, SIZE, stdin);
    peintf("Your string twice (puts(), then fputs() ):\n");
    puts(words);
    fputs(words, stdout);
  
    return 0;
}
```

#### gets_s()函数

#### s_gets()函数(自定义)

读取整行输入并用空字符代替换行符，或者读取一部分输入，并丢弃其余部分。

```c
char * s_gets(char *st, int n)
{
    char *ret_val;
    int i = 0;
    ret_val = fgets(st, n, stdin);
    if(ret_val)
    {
        while(st[i] != '\0' && st[i] != '\n')
        i++;
    if(st[i] == '\n')
        st[i] = '\0';
    else
        while(getchar() != '\n')
            continue;
    }
    return ret_val;
}
```

## 字符串输出函数

## 字符串函数

### 11.5.1strlen()函数

### 11.5.2strcat()函数

### 11.5.3strncat()函数

strcat()函数无法检查第一个数组能否容纳第二个字符串。如果分配给第一个数组的空间不够大，多出来的字符溢出到相邻存储单元时就会出问题。

==strncat()函数==接收3个参数，第三个参数指定了最大添加字符数。

```c
//join._chk.c
#include "stdio.h"
#include "string.h"
#define SIZE 30
#define BUGSIZE 13
char * s_gets (char * st,int n);
int main(void)
{
    char flower[SIZE];
    char addon[] = "s smell like old shoes.";
    char bug[BUGSIZE];
    int available;
    puts("What is your favorite flower?");
    s_gets(flower,SIZE);
    if((strlen(addon) + strlen(flower) + 1) <= SIZE)
        strcat(flower,addon);
    puts(flower);
    puts("What is your favorite bug?");
    s_gets(bug,BUGSIZE);
    available = BUGSIZE - strlen(bug) - 1;
    strncat(bug, addon, available);
    puts(bug);

    return 0;
}
char * s_gets(char * st,int n)
{
    char * ret_val;
    int i = 0;
    ret_val = fgets(st, n, stdin);
    if(ret_val){
        while (st[i] != '\0' && st[i] != '\n')
            i++;
        if(st[i] == '\n')
            st[i] = '\0';
        else
            while(getchar() != '\n')
                continue;
    }
    return ret_val;

}
```

### 11.5.4strcmp()函数

```c
#include "stdio.h"
#define ANSWER "Grant"
#define SIZE 40
char * s_gets(char * st, int n);

int main(void)
{
    char try[SIZE];

    puts("Who is buried in Grant`s tomb?");
    s_gets(try, SIZE);
    while(strcmp(try,ANSWER))
    {
        puts("No, that`s wrong.Try again.");
        s_gets(try,SIZE);
    }
    puts("That is right!");
  
    return 0;
}

char * s_gets(char * st, int n)
{
    int i = 0;
    char * ret_val;
  
    ret_val = fgets(st,n,stdin);
    if(ret_val)
    {
        while(st[i] != '\n' && st[i] != '\0')
            i++;
        if(st[i] == '\n')
            st[i] = '\0';
        else
            while(getchar() != '\n')
                continue;
    }
    return ret_val;
}
```

```c
#include "stdio.h"
#define ANSWER "Grant"
#define SIZE 40
char * s_gets(char * st, int n);

int main(void)
{
    char try[SIZE];

    puts("Who is buried in Grant`s tomb?");
    s_gets(try, SIZE);
    while(try != ANSWER)
    {
        puts("No, that`s wrong.Try again.");
        s_gets(try,SIZE);
    }
    puts("That is right!");
  
    return 0;
}

char * s_gets(char * st, int n)
{
    int i = 0;
    char * ret_val;
  
    ret_val = fgets(st,n,stdin);
    if(ret_val)
    {
        while(st[i] != '\n' && st[i] != '\0')
            i++;
        if(st[i] == '\n')
            st[i] = '\0';
        else
            while(getchar() != '\n')
                continue;
    }
    return ret_val;
}
```

**1.strcmp()的返回值**

ASCII规定：

在字母表中，如果第一个字符串在第二个字符串前面，则返回一个负数；

如果第一个字符串在第二个字符串后面，则返回一个正数；

如果两个字符串相等，则返回0。

strcmp()的返回值 = 字符串中首个不相同的字符的ASCII码相减的差

'\0'也要参与比较

**2.strncmp()函数**

strncmp()函数比较两个字符串时，可以通过第三个参数指定的字符数。

### 11.5.5strcpy()和strncpy()函数

strcpy( ‘目标字符串’ ， ’源字符串‘)；

第一个参数应是一个数据对象eg.数组，且该对象有足够的存储空间存储源字符串的副本；

第二个参数可声明为指针，数组名或字符串常量。

**1.strcpy()的其他属性**

一、strcpy()的返回类型为char *，该函数返回的是第一个参数的值，即一个字符的地址。

二、第一参数不必指向数组的开始。

**2.strncpy()函数**

该函数的第三个参数指明可拷贝的最大字符数

### 11.5.6sprintf()函数

- 该函数包含于stdio.h头文件中
- 功能：把数据写入字符串，不是屏幕输出；第一个参数是目标字符串的地址，其余参数和printf()函数相同，即格式转换串和待写入列表。

```c
sprintf(<目标字符串的地址>, "%d,%s",<待写入列表>)；
```

## 11.6字符串示例：字符串排列

```c
#include "stdio.h"
#include "string.h"
#define SIZE 81
#define LIM 20
#define HALT ""
void stsrt(char *strings[], int num);
char * s_gets(char * st, int n);

int main(void)
{
    char input[LIM][SIZE];
    char *ptstr[LIM];
    int ct = 0;
    int k;

    printf("Input up to %d lines, and I will sort them.\n", LIM);
    printf("To stop, press the Enter key at a line`s start.\n");
    while (ct < LIM && s_gets(input[ct], SIZE) != NULL && input[ct][0] != '\0')
    {
        ptstr[ct] = input[ct];
        ct++;
    }
    stsrt(ptstr, ct);
    puts("\nHere`s the sorted list:\n");
    for (k = 0; k < ct; k++)
    {
        puts(ptstr[k]);
    }
    return 0;
}
void stsrt(char *strings[], int num)
{
    char *temp;
    int top, seek;

    for (top = 0; top < num - 1; top++){
        for (seek = top+1; seek < num; seek++){
            if(strcmp(strings[top], strings[seek]) > 0){
                temp = strings[top];
                strings[top] = strings[seek];
                strings[seek] = temp;
            }
        }
    }
}
char * s_gets(char * st, int n)
{
    int i = 0;
    char * ret_val;

    ret_val = fgets(st,n,stdin);
    if(ret_val)
    {
        while(st[i] != '\n' && st[i] != '\0')
            i++;
        if(st[i] == '\n')
            st[i] = '\0';
        else
            while(getchar() != '\n')
                continue;
    }
    return ret_val;
}
```

# 存储类别、链接和内存管理

# 文件输入/输出

# 结构和其他数据形式

# 位操作

# C预处理器和C库

# 高级数据表示
