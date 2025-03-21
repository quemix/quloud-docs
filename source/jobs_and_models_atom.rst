==============================
原子構造の登録
==============================

------------------------------------
外部データベースからの登録
------------------------------------
++++++++++++++++++++++++++++++++++
結晶構造（Material Project）
++++++++++++++++++++++++++++++++++


.. math::
  E_{\rm x} \left[ \rho^\alpha, \rho^\beta \right]
    = \frac{1}{2} E_{\rm x} \left[ 2\rho^\alpha \right]
    + \frac{1}{2} E_{\rm x} \left[ 2\rho^\beta \right]


++++++++++++++++++++++++++++++
分子構造（PubChem）
++++++++++++++++++++++++++++++

---------------------------------
ファイルアップロードによる登録
---------------------------------
++++++++++++++++++++++++++++++
対応ファイル形式
++++++++++++++++++++++++++++++

.. math::
  E_{\rm x} \left[ \rho \right] = \int d\boldsymbol{r} \rho(\boldsymbol{r})
  \varepsilon_{\rm x} \left[ \rho \right] (\boldsymbol{r})

.. math::
  \varepsilon_{\rm x} \left[ \rho \right](\boldsymbol{r})
  = -\frac{3}{4} \left( \frac{3}{\pi} \right)^\frac{1}{3}
                 \left( \rho(\boldsymbol{r}) \right)^\frac{1}{3}

.. math::
  v_{\rm x} \left[ \rho \right](\boldsymbol{r})
  & = & \frac{ \delta E_{\rm x}\left[ \rho \right] }{ \delta\rho(\boldsymbol{r}) }
  = \varepsilon_{\rm x} \left[ \rho \right](\boldsymbol{r})
  -\frac{1}{4} \left( \frac{3}{\pi} \right)^\frac{1}{3}
               \left( \rho(\boldsymbol{r}) \right)^\frac{1}{3}
  \\
  & = & -\left( \frac{3}{\pi} \right)^\frac{1}{3}
         \left( \rho(\boldsymbol{r}) \right)^\frac{1}{3}
  = \frac{4}{3} \varepsilon_{\rm x} \left[ \rho \right](\boldsymbol{r})

.. math::
  v_{\rm x}^{\sigma} \left[ \rho^\alpha, \rho^\beta \right](\boldsymbol{r})
  & = & \frac{ \delta E_{\rm x} \left[ \rho^\alpha, \rho^\beta \right] }
         { \delta\rho^{\sigma}(\boldsymbol{r}) }
  = \left. \frac{ \delta E_{\rm x}\left[ \rho \right] }
                { \delta\rho(\boldsymbol{r}) } \right|_{\rho=2\rho^\sigma}
  \\
  & = & -\left( \frac{3}{\pi} \right)^\frac{1}{3}
  \left( 2\rho^\sigma(\boldsymbol{r}) \right)^\frac{1}{3}


+++++++++++++++++++++++++
スピン分極パラメータ
+++++++++++++++++++++++++

:math:`\rho=\rho^\alpha+\rho^\beta` として、スピン分極パラメータ :math:`\zeta` を

.. math::
  \zeta = \frac{ \rho^\alpha - \rho^\beta }{ \rho }

で定義する。これを用いてスピン密度は

.. math::
  \rho^\alpha & = & \frac{1}{2} \left( 1 + \zeta \right) \rho
  \\
  \rho^\beta & = & \frac{1}{2} \left( 1 - \zeta \right) \rho

と書ける。スピン分極がある場合の交換エネルギーを\
:math:`\rho, \zeta` を用いて書き換える事を考える。\
この書き換えは、交換エネルギーに対しては特に必要ないが、\
相関エネルギーのスピン密度依存性を交換エネルギーと同じ形にとるという方針で導入するために必要となる。

++++++++++++++++++++++++++++++++++++
相関エネルギー＆ポテンシャル（PZ81）
++++++++++++++++++++++++++++++++++++

.. math::
  E_{\rm c} \left[ \rho, \zeta \right] = \int d\boldsymbol{r} \rho(\boldsymbol{r})
  \varepsilon_{\rm c}\left[\rho,\zeta\right](\boldsymbol{r})

.. math::
  \varepsilon_{\rm c}^{\rm U,P} =
  \frac{\gamma^{\rm U,P}} {1 + \beta_1^{\rm U,P} \sqrt{r_{\rm s}} + \beta_2^{\rm U,P}r_{\rm s}}
  \qquad \left( r_{\rm s} > 1 \right)

.. math::
  \varepsilon_{\rm c}^{\rm U,P} = A^{U,P} \ln{r_{\rm s}} + B^{\rm U,P}
  + C^{\rm U,P} r_{\rm s} \ln{r_{\rm s}} + D^{\rm U,P} r_{\rm s}
  \qquad \left( r_{\rm s} < 1 \right)