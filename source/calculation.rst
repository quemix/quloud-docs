=============================================
計算ジョブの登録２（GUIを用いる方法）
=============================================

------------------------------------
第一原理計算
------------------------------------

++++++++++++++++++++++++++++++++++++
OpenMX
++++++++++++++++++++++++++++++++++++

.. math::
  \begin{pmatrix}
  x_1 \\
  x_2 \\
  x_3
  \end{pmatrix}
  =
  \begin{pmatrix}
  a_{11} & a_{12} & a_{13} \\
  a_{21} & a_{22} & a_{23} \\
  a_{31} & a_{32} & a_{33} \\
  \end{pmatrix}
  \begin{pmatrix}
  \alpha_1  \\
  \alpha_2 \\
  \alpha_3
  \end{pmatrix}

.. math::
  x_i = \sum_{j=1}^3 a_{ij} \alpha_j

.. math::
  \boldsymbol{a}_1 =
  \begin{pmatrix}
  a_{11} \\
  a_{21} \\
  a_{31}
  \end{pmatrix}
  , \quad
  \boldsymbol{a}_2 =
  \begin{pmatrix}
  a_{12} \\
  a_{22} \\
  a_{32}
  \end{pmatrix}
  , \quad
  \boldsymbol{a}_3 =
  \begin{pmatrix}
  a_{13} \\
  a_{23} \\
  a_{33}
  \end{pmatrix}

.. math::
  \boldsymbol{a}_i \cdot \boldsymbol{b}_j = 2\pi\delta_{ij}

.. math::
  A \equiv
  \begin{pmatrix}
  a_{11} & a_{12} & a_{13} \\
  a_{21} & a_{22} & a_{23} \\
  a_{31} & a_{32} & a_{33} \\
  \end{pmatrix}
  , \qquad
  B \equiv
  \begin{pmatrix}
  b_{11} & b_{12} & b_{13} \\
  b_{21} & b_{22} & b_{23} \\
  b_{31} & b_{32} & b_{33} \\
  \end{pmatrix}

.. math::
  \begin{pmatrix}
  a_{11} & a_{21} & a_{31} \\
  a_{12} & a_{22} & a_{32} \\
  a_{13} & a_{23} & a_{33} \\
  \end{pmatrix}
  \begin{pmatrix}
  b_{11} & b_{12} & b_{13} \\
  b_{21} & b_{22} & b_{23} \\
  b_{31} & b_{32} & b_{33} \\
  \end{pmatrix}
  =
  A^\top B = 2\pi I

.. math::
  \frac{1}{2\pi}A^\top = B^{-1}
  \\
  \frac{1}{2\pi}B^\top = A^{-1}

++++++++++++++++++++++++++++++++++++
Quantum ESPRESSO
++++++++++++++++++++++++++++++++++++

++++++++++++++++++++++++++++++++++++
RSDFT
++++++++++++++++++++++++++++++++++++

++++++++++++++++++++++++++++++++++++
SPRKKR
++++++++++++++++++++++++++++++++++++

------------------------------------
古典分子動力学計算
------------------------------------
++++++++++++++++++++++++++++++++++++
LAMMPS
++++++++++++++++++++++++++++++++++++
++++++++++++++++++++++++++++++++++++
CHGNet
++++++++++++++++++++++++++++++++++++

.. math::
  \begin{pmatrix}
  x_1' \\
  x_2' \\
  x_3'
  \end{pmatrix}
  =
  \begin{pmatrix}
  R_{11} & R_{12} & R_{13} \\
  R_{21} & R_{22} & R_{23} \\
  R_{31} & R_{32} & R_{33} \\
  \end{pmatrix}
  \begin{pmatrix}
  x_1  \\
  x_2 \\
  x_3
  \end{pmatrix}
  +
  \begin{pmatrix}
  t_1 \\
  t_2 \\
  t_3
  \end{pmatrix}

.. math::
  R \equiv
  \begin{pmatrix}
  R_{11} & R_{12} & R_{13} \\
  R_{21} & R_{22} & R_{23} \\
  R_{31} & R_{32} & R_{33} \\
  \end{pmatrix}

.. math::
  R^\top = R^{-1}

.. math::
  A \begin{pmatrix}
  \alpha_1' \\
  \alpha_2' \\
  \alpha_3' \\
  \end{pmatrix}
  =
  R A
  \begin{pmatrix}
  \alpha_1 \\
  \alpha_2 \\
  \alpha_3 \\
  \end{pmatrix}
  +
  A \begin{pmatrix}
  \tau_1 \\
  \tau_2 \\
  \tau_3
  \end{pmatrix}

.. math::
  \begin{pmatrix}
  \alpha_1' \\
  \alpha_2' \\
  \alpha_3' \\
  \end{pmatrix}
  =
  A^{-1} R A
  \begin{pmatrix}
  \alpha_1 \\
  \alpha_2 \\
  \alpha_3 \\
  \end{pmatrix}
  +
  \begin{pmatrix}
  \tau_1 \\
  \tau_2 \\
  \tau_3
  \end{pmatrix}

------------------------------------
機械学習分子動力学計算
------------------------------------

++++++++++++++++++++++++++++++++++
CHGNet
++++++++++++++++++++++++++++++++++

++++++++++++++++++++++++++++++++++
FLARE
++++++++++++++++++++++++++++++++++

3次元（カーテシアン）座標の回転を

.. math::
  \boldsymbol{r}' = R \boldsymbol{r}

と表す。関数の回転を次のように定義する。

.. math::
  f'(\boldsymbol{r}') = f(\boldsymbol{r})

回転した先の座標で、元と同じ値を取るべしという意味である。このとき

.. math::
  f'(\boldsymbol{r}') = f(\boldsymbol{r}) = f(R^{-1}\boldsymbol{r}')

となるので、回転された関数は

.. math::
  f'(\boldsymbol{r}) = f(R^{-1}\boldsymbol{r})

という値を取るものになる事がわかる。


------------------------------------
磁性材料計算（Quloud-Mag）
------------------------------------

++++++++++++++++++++++++++++++++++++
SPRKKR
++++++++++++++++++++++++++++++++++++

++++++++++++++++++++++++++++++++++++
Quloud-Mag
++++++++++++++++++++++++++++++++++++

++++++++++++++++++++++++++++++++++++
UppASD
++++++++++++++++++++++++++++++++++++

:math:`f'=f` となる場合には

.. math::
  f(\boldsymbol{r}) = f(R^{-1}\boldsymbol{r})

が成り立つ。これにより :math:`\boldsymbol{r}` での関数値が分かっていれば、
回転で移った先の座標での関数値も直ちにわかる。これを利用すれば、関数を評価する点の数を削減したり、
関数形の事前情報として反復計算のようなものを加速する事が可能となる。


回転 :math:`\alpha` を行ってから並進 :math:`\boldsymbol{b}` を行う操作を

.. math::
  \left\{ \alpha \left| \boldsymbol{b} \right. \right\} \boldsymbol{r}
  = \alpha \boldsymbol{r} + \boldsymbol{b}
  \equiv \boldsymbol{r}'

と表す事にする。この逆の操作は

.. math::
  \boldsymbol{r} =
  \left\{ \alpha \left| \boldsymbol{b} \right. \right\}^{-1} \boldsymbol{r}'
  = \alpha^{-1} \left( \boldsymbol{r}' -  \boldsymbol{b} \right)
  = \alpha^{-1} \boldsymbol{r}' - \alpha^{-1}\boldsymbol{b}

となる。すなわち

.. math::
  \left\{ \alpha \left| \boldsymbol{b} \right. \right\}^{-1}
  =
  \left\{ \alpha^{-1} \left| - \alpha^{-1}\boldsymbol{b} \right. \right\}

という操作となる。



回転されたブロッホ関数の取る値は、回転前の関数を用いて

.. math::
  \psi'_{n\boldsymbol{k}}(\boldsymbol{r})
  = \psi_{n\boldsymbol{k}}(\alpha^{-1}\boldsymbol{r}-\alpha^{-1}\boldsymbol{b})

と評価できる。任意の格子ベクトル :math:`\boldsymbol{R}` の平行移動を考える。

.. math::
  \psi'_{n\boldsymbol{k}}(\boldsymbol{r}+\boldsymbol{R})
  & = & \psi_{n\boldsymbol{k}}
  ( \alpha^{-1}( \boldsymbol{r} + \boldsymbol{R} ) -\alpha^{-1}\boldsymbol{b} ) \\
  & = & e^{ \boldsymbol{k} \cdot \alpha^{-1}\boldsymbol{R} }
  \psi_{n\boldsymbol{k}}
  ( \alpha^{-1}\boldsymbol{r} -\alpha^{-1}\boldsymbol{b} ) \\
  & = & e^{ \alpha\boldsymbol{k} \cdot \boldsymbol{R} }
  \psi'_{n\boldsymbol{k}}( \boldsymbol{r} )

これより回転された波数 :math:`\boldsymbol{k}` のBloch関数は、
波数 :math:`\alpha\boldsymbol{k}` のBloch関数となることがわかる。
系に回転＋並進の不変性（対称性）があれば

.. math::
  \psi_{n\boldsymbol{k}}
  ( \alpha^{-1}\boldsymbol{r} -\alpha^{-1}\boldsymbol{b} )

を波数 :math:`\alpha\boldsymbol{k}` のBloch関数として使えることになる。



.. math::
  f(\boldsymbol{r}) = f(R^{-1}\boldsymbol{r})

.. math::
  \frac{\partial f(\boldsymbol{r})}{\partial x_i}
  & = & \sum_{j=1}^3
  \left. \frac{\partial f(\boldsymbol{r}')}{\partial x'_j} \right|
    _{ \boldsymbol{r}'=R^{-1}\boldsymbol{r} }
  \frac{\partial x'_j}{\partial x_i} \\
  & = & \sum_{j=1}^3
  \left. \frac{\partial f(\boldsymbol{r}')}{\partial x'_j} \right|
    _{ \boldsymbol{r}'=R^{-1}\boldsymbol{r} }
  \left( R^{-1} \right)_{ji} \\
  & = & \sum_{j=1}^3 R_{ij}
  \left. \frac{\partial f(\boldsymbol{r}')}{\partial x'_j} \right|
    _{ \boldsymbol{r}'=R^{-1}\boldsymbol{r} }



.. math::
  \frac{\partial f}{\partial x_i}
  = \sum_{j=1}^3 \frac{\partial f}{\partial x_j'}\frac{\partial x_j'}{\partial x_i}
  = \sum_{j=1}^3 \frac{\partial f}{\partial x_j'} R_{ji}

.. math::
  \begin{pmatrix}
  \frac{\partial f}{\partial x_1} \\
  \frac{\partial f}{\partial x_2} \\
  \frac{\partial f}{\partial x_3}
  \end{pmatrix}
  =
  R^\top
  \begin{pmatrix}
  \frac{\partial f}{\partial x_1'} \\
  \frac{\partial f}{\partial x_2'} \\
  \frac{\partial f}{\partial x_3'}
  \end{pmatrix}
  
.. math::
  R \begin{pmatrix}
  \frac{\partial f}{\partial x_1} \\
  \frac{\partial f}{\partial x_2} \\
  \frac{\partial f}{\partial x_3}
  \end{pmatrix}
  =
  \begin{pmatrix}
  \frac{\partial f}{\partial x_1'} \\
  \frac{\partial f}{\partial x_2'} \\
  \frac{\partial f}{\partial x_3'}
  \end{pmatrix}


.. math::
  \frac{\partial f}{\partial x_i}
  & = & \sum_{j=1}^3 \frac{\partial f}{\partial \alpha_j}\frac{\partial \alpha_j}{\partial x_i}
  = \sum_{j=1}^3 \frac{\partial f}{\partial \alpha_j} (A^{-1})_{ji} \\
  & = & \frac{1}{2\pi} \sum_{j=1}^3 B_{ij} \frac{\partial f}{\partial \alpha_j}


.. math::
  \begin{pmatrix}
  \frac{\partial f}{\partial x_1} \\
  \frac{\partial f}{\partial x_2} \\
  \frac{\partial f}{\partial x_3}
  \end{pmatrix}
  =
  (A^{-1})^\top
  \begin{pmatrix}
  \frac{\partial f}{\partial \alpha_1} \\
  \frac{\partial f}{\partial \alpha_2} \\
  \frac{\partial f}{\partial \alpha_3}
  \end{pmatrix}
  =
  \frac{1}{2\pi} B
  \begin{pmatrix}
  \frac{\partial f}{\partial \alpha_1} \\
  \frac{\partial f}{\partial \alpha_2} \\
  \frac{\partial f}{\partial \alpha_3}
  \end{pmatrix}


.. math::
  \begin{pmatrix}
  \frac{\partial f}{\partial \alpha_1} \\
  \frac{\partial f}{\partial \alpha_2} \\
  \frac{\partial f}{\partial \alpha_3}
  \end{pmatrix}
  =
  2\pi B^{-1}
  \begin{pmatrix}
  \frac{\partial f}{\partial x_1} \\
  \frac{\partial f}{\partial x_2} \\
  \frac{\partial f}{\partial x_3}
  \end{pmatrix}
  =
  A^\top
  \begin{pmatrix}
  \frac{\partial f}{\partial x_1} \\
  \frac{\partial f}{\partial x_2} \\
  \frac{\partial f}{\partial x_3}
  \end{pmatrix}



.. math::
  R \begin{pmatrix}
  \frac{\partial f}{\partial x_1} \\
  \frac{\partial f}{\partial x_2} \\
  \frac{\partial f}{\partial x_3}
  \end{pmatrix}
  =
  R (A^{-1})^\top
  \begin{pmatrix}
  \frac{\partial f}{\partial \alpha_1} \\
  \frac{\partial f}{\partial \alpha_2} \\
  \frac{\partial f}{\partial \alpha_3}
  \end{pmatrix}
  =
  \begin{pmatrix}
  \frac{\partial f}{\partial x_1'} \\
  \frac{\partial f}{\partial x_2'} \\
  \frac{\partial f}{\partial x_3'}
  \end{pmatrix}

.. math::
  A^\top R \begin{pmatrix}
  \frac{\partial f}{\partial x_1} \\
  \frac{\partial f}{\partial x_2} \\
  \frac{\partial f}{\partial x_3}
  \end{pmatrix}
  =
  A^\top R (A^{-1})^\top
  \begin{pmatrix}
  \frac{\partial f}{\partial \alpha_1} \\
  \frac{\partial f}{\partial \alpha_2} \\
  \frac{\partial f}{\partial \alpha_3}
  \end{pmatrix}
  =
  A^\top \begin{pmatrix}
  \frac{\partial f}{\partial x_1'} \\
  \frac{\partial f}{\partial x_2'} \\
  \frac{\partial f}{\partial x_3'}
  \end{pmatrix}
  =
  \begin{pmatrix}
  \frac{\partial f}{\partial \alpha'_1} \\
  \frac{\partial f}{\partial \alpha'_2} \\
  \frac{\partial f}{\partial \alpha'_3}
  \end{pmatrix}

.. math::
  \begin{pmatrix}
  \frac{\partial f}{\partial \alpha'_1} \\
  \frac{\partial f}{\partial \alpha'_2} \\
  \frac{\partial f}{\partial \alpha'_3}
  \end{pmatrix}
  =
  A^\top R (A^{-1})^\top
  \begin{pmatrix}
  \frac{\partial f}{\partial \alpha_1} \\
  \frac{\partial f}{\partial \alpha_2} \\
  \frac{\partial f}{\partial \alpha_3}
  \end{pmatrix}
  =
  B^{-1} R B
  \begin{pmatrix}
  \frac{\partial f}{\partial \alpha_1} \\
  \frac{\partial f}{\partial \alpha_2} \\
  \frac{\partial f}{\partial \alpha_3}
  \end{pmatrix}

.. math::
  \begin{pmatrix}
  \frac{\partial f}{\partial \alpha_1} \\
  \frac{\partial f}{\partial \alpha_2} \\
  \frac{\partial f}{\partial \alpha_3}
  \end{pmatrix}
  =
  B^{-1} R B
  \begin{pmatrix}
  \frac{\partial f}{\partial \alpha'_1} \\
  \frac{\partial f}{\partial \alpha'_2} \\
  \frac{\partial f}{\partial \alpha'_3}
  \end{pmatrix}