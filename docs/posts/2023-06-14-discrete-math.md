# 集合与对称差习题

*迁移自 2023 年 6 月 14 日的旧 Hexo 文章。原文标题为 “My New Post”。以下保留原有习题与解答内容，并仅对 Markdown / LaTeX 排版做迁移整理，未重新校订数学推导。*

---

## 1. 集合运算

考虑集合

$$
A = \{1,2,3,4,5\}, \qquad B = \{2,4,6\}
$$

计算 $A \cup B$、$A \cap B$、$A-B$、$B-A$ 和 $A \oplus B$。

**解：**

$$
\begin{aligned}
A \cup B &= \{1,2,3,4,5,6\} \\
A \cap B &= \{2,4\} \\
A-B &= \{1,3,5\} \\
B-A &= \{6\} \\
A \oplus B &= \{1,3,5,6\}
\end{aligned}
$$

---

## 2. 对称差的文氏图

集合 $A$ 和 $B$ 的对称差 $A \oplus B$ 表示只属于 $A$ 或只属于 $B$、但不同时属于二者的元素：

$$
A \oplus B = (A-B) \cup (B-A)
$$

!!! note "迁移说明"
    旧 Hexo 页面引用了一张 `Pasted image 20230301201050.png`，但该图片并未保存在已部署的仓库中，因此迁移时以等价的文字和公式说明替代。文氏图中应将 $A-B$ 与 $B-A$ 两侧区域涂色，而交集 $A\cap B$ 不涂色。

---

## 3. 对称差的性质

### (1) $A \oplus B \subseteq A \cup B$

由

$$
A \oplus B = (A-B) \cup (B-A)
$$

若 $x \in A-B$，则 $x \in A \subseteq A \cup B$；若 $x \in B-A$，则 $x \in B \subseteq A \cup B$。

所以

$$
A \oplus B \subseteq A \cup B
$$

### (2) $(A \oplus B) \cap (A \cap B)=\varnothing$

由

$$
A \oplus B = (A-B) \cup (B-A)
$$

若 $x \in A-B$，则 $x \notin B$；若 $x \in B-A$，则 $x \notin A$。因此任何属于 $A \oplus B$ 的元素都不可能同时属于 $A$ 和 $B$。

所以

$$
(A \oplus B) \cap (A \cap B)=\varnothing
$$

### (3) $A \oplus B=(A\cup B)-(A\cap B)$

$$
\begin{aligned}
(A \cup B)-(A \cap B)
&= (A \cup B) \cap \overline{A \cap B} \\
&= (A \cup B) \cap (\bar A \cup \bar B) \\
&= (A \cap \bar B) \cup (\bar A \cap B) \\
&= (A-B) \cup (B-A) \\
&= A \oplus B
\end{aligned}
$$

---

## 4. 消去律

考虑集合 $A,B,C$。若

$$
A \oplus C = B \oplus C
$$

证明 $A=B$。

可以在等式两边再次与 $C$ 做对称差：

$$
(A\oplus C)\oplus C=(B\oplus C)\oplus C
$$

利用结合律以及 $C\oplus C=\varnothing$、$X\oplus\varnothing=X$，得到

$$
A=B
$$

---

## 5. 对称差的运算律

### (1) 交换律

满足交换律：

$$
\begin{aligned}
A \oplus B
&= (A-B)\cup(B-A) \\
&= (B-A)\cup(A-B) \\
&= B\oplus A
\end{aligned}
$$

因此

$$
A\oplus B=B\oplus A
$$

### (2) 结合律

满足结合律：

$$
(A\oplus B)\oplus C=A\oplus(B\oplus C)
$$

从元素是否属于各集合的角度看，对称差等价于“成员关系的异或（XOR）”。异或满足结合律，因此集合的对称差也满足结合律。

### (3) $\cap$ 对 $\oplus$ 的分配律

满足：

$$
(A\oplus B)\cap C=(A\cap C)\oplus(B\cap C)
$$

因为

$$
\begin{aligned}
(A\oplus B)\cap C
&= \big[(A\cap\bar B)\cup(\bar A\cap B)\big]\cap C \\
&= (A\cap\bar B\cap C)\cup(\bar A\cap B\cap C)
\end{aligned}
$$

而右侧展开后得到相同的集合。

### (4) $\oplus$ 对 $\cap$ 不满足分配律

命题

$$
(A\cap B)\oplus C=(A\oplus B)\cap(A\oplus C)
$$

一般不成立。

取

$$
A=\{1\},\qquad B=\{2\},\qquad C=\{3\}
$$

则

$$
(A\cap B)\oplus C
=\varnothing\oplus\{3\}
=\{3\}
$$

而

$$
(A\oplus B)\cap(A\oplus C)
=\{1,2\}\cap\{1,3\}
=\{1\}
$$

两者不相等，因此该分配律不成立。
