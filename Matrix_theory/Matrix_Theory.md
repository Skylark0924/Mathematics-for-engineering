<font color=#FF8C00></font>

# 理解矩阵

1. [理解矩阵（一）](https://blog.csdn.net/myan/article/details/647511)
2. [理解矩阵（二）](https://blog.csdn.net/myan/article/details/649018)
3. [理解矩阵（三）](https://blog.csdn.net/myan/article/details/1865397)

**总结：**

- **“空间”是容纳运动的一个对象集合，而变换则规定了对应空间的运动。**
- **矩阵的本质是运动的描述。**
- **所谓变换，其实就是空间里从一个点（元素/对象）到另一个点（元素/对象）的跃迁**
- **矩阵是线性空间里的变换的描述，矩阵与向量相乘，就是实施运动（变换）的过程。**
- **矩阵是线性空间中的线性变换的一个描述。在一个线性空间中，只要我们选定一组基，那么对于任何一个线性变换，都能够用一个确定的矩阵来加以描述。**
- **所谓相似矩阵，就是同一个线性变换的不同的描述矩阵，它们的本质是一样的，所以本征值相同。**
- **矩阵不仅可以作为线性变换的描述，而且可以作为一组基的描述。而作为变换的矩阵，不但可以把线性空间中的一个点给变换到另一个点去，而且也能够把线性空间中的一个坐标系（基）表换到另一个坐标系（基）去。而且，变换点与变换坐标系，具有异曲同工的效果。（运动等价于坐标系的变换，即运动是相对的！）**

-------

# Linear Algebra Done Right

## Vector Spaces

1. A ***vector space*** is a set V along with an addition on V and a scalar
   multiplication on V such that the following **properties** hold:

   - **commutativity**

     ​	$u+v=v+u$ for all $u,v \in V$ ;

   - **associativity**

     ​	$(u+v)+w=u+(v+w)​$ and $(ab)v=a(bv)​$ for all $u,v,w \in V ​$ and all $a,b\in F​$ ;

   - **additive identity** (must be unique)

     ​	there exists an element $0\in V$ such that $v+0=v$ for all $v\in V$

   - **additive inverse**  (must be unique)

     ​	for every $v\in V$, there exists $w\in V$ such that $v+w=0$ ;

   - **multiplication identity**

     ​	$1v=v​$ for all $v\in V​$ ;

   - **distributive properties**

     ​	$a(u+v)=au+av$ and $(a+b)u=au+bu$ for all $a,b\in F$ and all $u,v\in V$

   **Polynomial**  is also a vector space

2. **Propositions**:

   - $0v =0​$ for every $v \in V​$.
   - $a0=0​$ for every $a∈F.​$ 
   - $(−1)v =−v​$ for every $v \in V​$ .

   **Remember that the $0, -1$ above may not be the regular $0, -1$ as we known, they denote additive inverse and additive identity of the specific operation**(pending)

3. **Subspaces**：If $U$ is a subset of $V$, then to check that $U$ is a subspace of $V$ we need only check that $U$ satisﬁes the following: 

   - **additive identity** : $0∈U; ​$ 
   - **closed under addition** : $u,v ∈U $ implies $u+v ∈U; ​$
   - **closed under scalar multiplication** : $a∈F$ and $u∈U$ implies $au∈U$. 

   <font color=#FF8C00>A subspace can be regard as a large space with some properties being limited</font>

4. **Sums and Direct Sums**： Speciﬁcally, we say that $V​$ is the direct sum of subspaces$ U_1 ,...,U_m​$, 

   (1)  $V =U_1 ⊕···⊕U_m​$, 

   (2) each element of $V​$ can be written <font color=#FF8C00>**uniquely** </font>as a sum $u_1+\dots +u_m​$, where each $u_j \in U_j​$.

   **Proposition**: Suppose that $U​$ and $W​$ are subspaces of $V​$. Then $V =U⊕W​$ if and only if $V =U+W​$ and $U∩W =\{0\}​$.  (only with the case of two subspaces). 

   $$V =U⊕W  \Leftrightarrow  V =U+W  \&  U∩W =\{0\}​$$

   

## Finite-Dimensional Vector Spaces

### Span and Linear Independence 

1. **The set of all linear combinations of $(v_1,...,v_m)​$ is called the span of $(v_1,...,v_m)​$, denoted $span(v_1,...,v_m)​$.**

   $$span(v_1,...,v_m)=\lbrace a_1v_1+···+a_mv_m : a_1,...,a_m ∈F\rbrace. ​$$

    the span of any list of vectors in $V$ is a subspace of $V$.

2. **Inﬁnite-dimensional** vector spaces are the center of attention in the branch of mathematics called *functional analysis*.

3. A list $(v_1,...,v_m)​$ of vectors in $V​$ is called **linearly independent** if the only choice of $a_1 ,...,a_m ∈F​$ that makes $a_1 v_1 +···+a_mv_m​$ equal $0​$ is $a_1 =···=a_m =0.​$

### Bases

A basis of $V$ is a list of vectors in $V$ that is linearly independent and spans $V.$ 

1. A list $(v_1,...,v_n)$ of vectors in $V$ is a basis of $V$ if and only if every $v ∈V$ can be written uniquely in the form

   $$ v =a_1v_1+···+a_nv_n$$

   where $a_1,...,a_n ∈F$.

2. Every spanning list in a vector space can be reduced to a basis of the vector space.

3.  Every linearly independent list of vectors in a ﬁnite-dimensional vector space can be extended to a basis of the vector space.

4.  Suppose $V$ is ﬁnite dimensional and $U$ is a subspace of $V$. Then there is a subspace W of $V$ such that $V =U⊕W.​$

### Dimension

1.  If $V$ is ﬁnite dimensional and $U$ is a subspace of $V$, then $dimU ≤dimV.$ 

2.  If $U1$ and  $U2$ are subspaces of a ﬁnite-dimensional vector space, then 

   <font color=#FF8C00>$dim(U1+U2)=dimU1+dimU2−dim(U1∩U2)$</font>.

   - It is same as the number of elements in the union of  two finite sets: $$n(A+B)=n(A)+n(B)-n(A\cap B)​$$

3. Suppose V is ﬁnite dimensional and $U1,...,Um$ are subspaces of V such that

    $$V =U_1+···+U_m​$$ 

   and  

   $$dimV =dimU_1+···+dimU_m$$.

   Then $V =U_1⊕···⊕U_m$.

   <font color=#FF8C00>Recall that direct sum is analogous to disjoint union. </font>

   - In sets:

     If $B=A_1 \cup \dots A_m$, and $n(B)=n(A_1)+\dots+n(A_m)$, then the union is a disjoint union.

## Linear Maps









# 第二章 矩阵与线性变换

### 维数定理
设V是线性空间，U与W是V的两个子空间，则
$$dim(U+W)=dimU+dimW-dim(U \cap W)$$
1. 基的扩充定理
![](img/15529549269818.png)
1. 欲使子空间U+W的维数最大，必须且只要$U\cap W=0$，亦即U和W重合的部分最小，为零空间。这时称U+W是**直和**，记为$U\oplus W$。因此$dim(U\oplus W)=dimU+dimW$。
2. 如果是直和，则任意$\gamma\in U+W$可以唯一由U和W中的两个元素表示，并且零向量也表示唯一（反证法），这三个命题等价。
3. **补空间：** $V=U\oplus W$，则W是U的补子空间。                                                                                                       补空间不唯一（反例：二维空间中两个相交在原点的向量）

### 四个子空间
1. 零空间$N(A)$：齐次线性方程组$Ax=0$的解空间
2. 列空间$R(A)$（像空间、值域）：A的列向量生成的子空间
3. 行空间$R(A^T)$：A的行向量生成的子空间
4. 左零空间$N(A^T)$：线性方程组$y^TA=0$或$A^Tx=0$的解空间

![](img/15529566462652.png)

### 线性变换
线性变换应满足可加性和齐次性，U到V的线性变换全体记为$Hom(U, V)$ 
1. **核：** “零点”集$ \{\alpha \in U: \sigma(\alpha)=0\} $，记作$Ker(\sigma)$或$\sigma^{-1}(0)$

2. **像：** “函数值”的集合$\{\alpha \in V: \exists \beta \in U, 使得\alpha=\sigma(\beta)\}$，记作$Im(\sigma)$或$\sigma(U)$

3. $Ker\sigma和Im\sigma$分别是U和V的子空间，其维数记作$\eta (\sigma)与\gamma(\sigma)$
    **理解：** 线性变换$\sigma=Ax$对应矩阵A，零变换对应零矩阵，恒等变换对应恒等矩阵；变换的核与矩阵零空间$N(A)$有关，像与矩阵的列空间$R(A)$。当选取标准基时，线性变换几乎就是左乘一个矩阵A，进一步，设$A=(a_{ij})$，则
    $$\sigma(\alpha)=A(x_1, x_2, \dots, x_n)^T$$$$=(a_{11}x_1+a_{12}x_2+\dots+a_{1n}x_n,\dots,a_{n1}x_1+a_{n2}x_2+\dots+a_{nn}x_n)^T $$$$=(\sigma_1(\alpha),\dots,\sigma_n(\alpha))$$ 

    即线性变换不过是多个多元线性函数

4. **不同基下的矩阵的关系：** 设$\alpha和\beta$是U的两组基，P是由$\alpha-基到\beta-基$的过渡矩阵；设$\alpha’和\beta’$是V的两组基，Q是由$\alpha’-基到\beta’-基$的过渡矩阵；设$\sigma\in Hom(U,V)$关于$\alpha-基和\alpha’-基$的矩阵为A，关于$\beta-基 和\beta’-基$的矩阵为B：
    $$B=Q^{-1}AP$$
    假定U=V且$\alpha-基等于\alpha’-基$，$\beta-基等于\beta’基$，于是：
    $$B=P^{-1}AP​$$
    则A与B**相似**

5. **同构：** $\sigma: U-> V$ 既是单射又是满射；两个空间不仅元素对应，运算也对应；并且**维度相同**