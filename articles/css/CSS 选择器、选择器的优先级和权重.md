> 以下总结内容摘自 《移动Web前端高效开发实战》  

## 基本选择器
| 选择器 | 名 称 | 实 例 | 描 述 | 版 本 |
| --- | --- | --- | --- | --- |
| \* | 通用选择器（Universal selectors）| ```*``` | 匹配所有的元素 | 2.1 |
| E | 标签选择器（Type selectors） | ```p``` | 匹配所有的 ```<p>``` | 1 |
| .class | 类选择器（Class selectors） | ```.nav``` | 匹配所有 ```class="nav"``` 的元素 | 1 |
| #id | ID选择器（ID selectors） | ```#wrapper``` | 匹配所有 ```id="wrapper"``` 的元素 | 1 |
| E[attr] | 属性选择器（Attribute selectors） | ```a[data-url]``` | 匹配所有 ```data-url``` 属性的 ```<a>``` 的元素 | 2.1 |
| E[attr=val] | 属性选择器（Attribute selectors） | ```a[data-url='http']``` | 匹配所有 ```data-url="http"``` 属性的 ```<a>``` 的元素 | 2.1 |
| E[attr~=val] | 属性选择器（Attribute selectors） | ```a[data-url~='http']``` | 匹配所有 ```data-url``` 属性包含 ```http``` 的 ```<a>``` 元素 | 2.1 |
| E[attr\|=val] | 属性选择器（Attribute selectors） | ```a[data-url\|='http']``` | 匹配所有 ```data-url``` 属性以 ```http``` 开头的 ```<a>``` 元素 | 2.1 |
| E[attr^=val] | 属性选择器（Attribute selectors） | ```a[data-url^='http']``` | 匹配所有 ```data-url``` 属性以 ```http``` 开头的 ```<a>``` 元素 | 3 |
| E[attr$=val] | 属性选择器（Attribute selectors） | ```a[data-url$='http']``` | 匹配所有 ```data-url``` 属性以 ```http``` 结尾的 ```<a>``` 元素 | 3 |
| E[attr\*=val] | 属性选择器（Attribute selectors） | ```a[data-url*='http']``` | 匹配所有 ```data-url``` 属性包含 ```http``` 的 ```<a>``` 元素 | 3 |
| E F | 后代选择器（Descendant selectors） | ```div p``` | 匹配所有 ```<div>``` 元素下所有 ```<p>``` 元素 | 1 |
| E > F | 子选择器（Child selectors） | ```div p``` | 匹配所有 ```<div>``` 元素下所有子 ```<p>``` 元素 | 2.1 |
| E + F | 相邻兄弟选择器 | ```label + input``` | 匹配所有``` <label> ``` 元素同级的第一个 ``` <input> ``` 元素 | 2.1 |
| E ~ F | 兄弟选择器 | ```label ~ input``` | 匹配所有``` <label> ``` 元素同级的所有 ``` <input> ``` 元素 | 3 |
| S1,S2,..... | 选择器分组 | ```label,input``` | 匹配所有``` <label>,<input> ```元素 | 1 |

## 伪类和伪元素

&ensp;&ensp;伪类（Pseudo-classes）用于指定选择器的某种特定状态或条件，伪类在 DOM 中并不存在，但对用户却是可见的。

### 动态伪类（Dynamic pseudo-classes）

&ensp;&ensp;动态伪类对除了其名称、属性或内容之外的特性的元素进行分类，不会显示在文档源或文树中。

| 选择器 | 实 例 | 描 述 | 版 本 |
| --- | --- | --- | --- |
| :link | ```a:link``` | 匹配未被访问的链接 | 1 |
| :visited | ```a:visited``` | 匹配被访问过的链接 | 1 |
| :hover | ```a:hover``` | 匹配鼠标指针在其浮动的元素 | 1 |
| :active | ```a:active``` | 匹配鼠标指针在其上按下的元素 | 1 |
| :focus | ```input:focus``` | 匹配获得焦点的元素 | 2.1 |

### 目标伪类（The target pseudo-classes）

&ensp;&ensp;目标伪类指定当前活动的锚，使用目标伪类可以为活动的锚设置样式。

| 选择器 | 实 例 | 描 述 | 版 本 |
| --- | --- | --- | --- |
| :target | ```#tab1:target``` | 匹配活动的锚 | 3 |

### 语言伪类（The language pseudo-classes）

&ensp;&ensp;语言伪类向带有指定 ```lang``` 属性元素添加样式。

| 选择器 | 实 例 | 描 述 | 版 本 |
| --- | --- | --- | --- |
| :lang(val) | ```#p:lang(en)``` | 匹配带有指定 ```lange="en"``` 的 ```<p>``` 元素 | 3 |

### UI元素状态伪类（The UI element states pseudo-classes）

&ensp;&ensp;UI元素状态伪类主要用于指定表单中的元素状态。

| 选择器 | 实 例 | 描 述 | 版 本 |
| --- | --- | --- | --- |
| :enabled | ```input:enabled``` | 匹配启动的元素 | 3 |
| :disabled | ```input:disabled``` | 匹配禁用的元素 | 3 |
| :checked | ```input:checked``` | 匹配被选中的元素 | 3 |

> ```display``` 和 ```visibility``` 属性对于UI元素状态伪类匹配 ```enabled/disabled``` 状态没有影响。

### 结构性伪类（Structural pseudo-classes）

&ensp;&ensp;结构性伪类用于指定文档的特定结构。

| 选择器 | 实 例 | 描 述 | 版 本 |
| --- | --- | --- | --- |
| :root | ```:root``` | 匹配文档的根元素 | 3 |
| :nth-child(n) | ```:nth-child(n)``` | 匹配其父元素的第 n 个子元素| 3 |
| :nth-last-child(n) | ```:nth-last-child(n)``` | 匹配其父类倒数第 n 个子元素 | 3 |
| :nth-of-type(n) | ```:nth-of-type(n)``` | 匹配其父类第 n 个有着相同选择器的子元素| 3 |
| :nth-last-of-type(n) | ```:nth-last-of-type(n)``` | 匹配其父类倒数第 n 个有着相同选择器的子元素 | 3 |
| :first-child | ```:first-child ``` | 匹配其父类元素的第一个子元素 | 3 |
| :last-child | ```:last-child ``` | 匹配其父类元素的最后一个子元素 | 3 |
| :last-child | ```:last-child ``` | 匹配其父类元素的最后一个子元素 | 3 |
| :first-of-type | ```:first-of-type``` | 匹配其父类元素第一个有着相同选择器的子元素 | 3 |
| :last-of-type | ```:first-of-type``` | 匹配其父类元素最后一个有着相同选择器的子元素 | 3 |
| :only-child | ```:only-child``` | 匹配其父类的唯一子元素 | 3 |
| :only-of-type | ```:only-child``` | 匹配其父类的唯一有着相同选择器的子元素 | 3 |
| :empty | ```:empty``` | 匹配没有子元素（包括文字节点）的元素 | 3 |

> ```:nth-child(n)```、```:nth-last-child(n)```、```:nth-of-type(n)```、```:nth-last-of-type(n)``` 中 **n 是从 0 开始的整数，表达式可写成 ```an+b```， a 和 b 是 0 或正整数，表达式的写法相当于把每 a 个子元素分成一组，取每组的第 b 个元素；取第奇数、偶数个子元素可写表达式为 ```2n+1 或 even```、```2n 或 odd```**。

&ensp;&ensp;否定伪类是用来选择所有非指定类型元素的其他元素。

| 选择器 | 实 例 | 描 述 | 版 本 |
| --- | --- | --- | --- |
| :not(s) | ```input:not([type="text"])``` | 匹配所有非指定类型的其他元素 | 3 |

### 伪元素

&ensp;&ensp;伪元素（Pseudo-elements）是指不存在与文档树中的抽象。

| 选择器 | 实 例 | 描 述 | 版 本 |
| --- | --- | --- | --- |
| ::first-line | ```::first-line``` | 匹配元素文本内容的首行 | 1 |
| ::first-letter | ```::first-letter``` | 匹配元素文本内容的首个字母 | 1 |
| ::before | ```::before``` | 元素之前 | 2.1 |
| ::after | ```::after``` | 元素之后 | 2.1 |

> 在 CSS 1 和 CSS 2 中，伪类选择器中只有一个 ":"，而 CSS 3 变为两个 "::"，是为了区分伪类与伪元素，目前这两个写法效果一致。

> ```::before``` 与 ```::after``` 必须设置 ```content``` 属性，否则元素不能生效。

## 优先级和权重

&ensp;&ensp; CSS 中的权重分别为 4 个等级：
- 内联样式（HTML 文档中的 style 属性）
- ID 选择器
- 类、伪类、属性选择器
- 元素、伪类元素

这 4 个等级由高到低代表不同的优先级，```!important``` 写在 CSS 规则后，可以将对应的规则提升到最高权重。

文章原文地址 [CSS 选择器、选择器的优先级和权重](https://github.com/SilenceHVK/articles/issues/19) 欢迎 Star 和 Watch