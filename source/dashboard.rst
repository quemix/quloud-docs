==============================
ダッシュボード（トップ画面）
==============================

.. image:: ./images/スクリーンショット\ 2024-09-04\ 170545.png
  :scale: 30%
  :align: center

------------------------------------
JOBS & MODELS
------------------------------------

スピン自由度を考慮した交換エネルギーの表式を考える。まず以下のように
:math:`\alpha` スピンと :math:`\beta` スピンがそれぞれある場合の和で書けると仮定する [#f1]_ 。

.. math::
  E_{\rm x} \left[ \rho^\alpha, \rho^\beta \right] = E_{\rm x} \left[ \rho^\alpha, 0 \right]
  + E_{\rm x} \left[ 0, \rho^\beta \right] 

スピン分極がない場合、すなわち

.. math::
  \rho^\alpha = \rho^\beta = \frac{\rho}{2}

という場合の交換エネルギーは

.. math::
  E_{\rm x} \left[ \frac{\rho}{2}, \frac{\rho}{2} \right]
    = E_{\rm x} \left[ \frac{\rho}{2}, 0 \right]
    + E_{\rm x} \left[ 0, \frac{\rho}{2} \right]

となる。また

.. math::
    E_{\rm x} \left[ \frac{\rho}{2}, 0 \right] = E_{\rm x} \left[ 0, \frac{\rho}{2} \right]

であると考えられる。スピン分極がない場合の交換エネルギーの表式
:math:`E_x \left[ \rho \right]` が分かっていれば

.. math::
  E_{\rm x} \left[ \rho \right] = E_{\rm x} \left[ \frac{\rho}{2}, \frac{\rho}{2} \right]

となるので、

.. math::
  E_{\rm x} \left[ \rho \right] = E_{\rm x} \left[ \frac{\rho}{2}, \frac{\rho}{2} \right]
  = 2E_{\rm x} \left[ \frac{\rho}{2}, 0 \right]
  = 2E_{\rm x} \left[ 0, \frac{\rho}{2} \right]

という関係が成り立つ。以上よりスピン分極がある場合の汎関数形は、\
スピン分極がない場合の式を用いて次のように書ける事がわかる。

.. math::
  E_{\rm x} \left[ \rho^\alpha, \rho^\beta \right]
    = \frac{1}{2} E_{\rm x} \left[ 2\rho^\alpha \right]
    + \frac{1}{2} E_{\rm x} \left[ 2\rho^\beta \right]


.. rubric:: 脚注
.. [#f1] 軌道や密度行列であれば容易に和で書き表す事ができるが、密度でも同様に書けるかは自明ではない。

-----------------------
PROJECTS
-----------------------
++++++++++++++++++++++++++++++
交換エネルギー＆ポテンシャル
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