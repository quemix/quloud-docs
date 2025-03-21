==============================
原子構造モデリング
==============================

------------------------------------
基本モデリング
------------------------------------

.. math::
  E_{\rm TF}\left[ \rho \right]
  = C_{\rm F} \int d\boldsymbol{r} \left( \rho(\boldsymbol{r}) \right)^{5/3}
  + \int d\boldsymbol{r} v(\boldsymbol{r}) \rho(\boldsymbol{r})
  + E_{\rm H} \left[ \rho \right]

.. math::
  C_{\rm F} = \frac{3}{10} \left( 3\pi^2 \right)^{2/3}

最小化すべき汎関数は、電子数に対する制約条件を付けて

.. math::
  F_{\rm TF}\left[ \rho \right]
  = C_{\rm F} \int d\boldsymbol{r} \left( \rho(\boldsymbol{r}) \right)^{5/3}
  + \int d\boldsymbol{r} v(\boldsymbol{r}) \rho(\boldsymbol{r})
  + E_{\rm H} \left[ \rho \right]
  - \mu \left( \int d\boldsymbol{r} \rho(\boldsymbol{r}) - N \right)

となる。電子数に対する制約条件の項は以下のモデルでも全て共通である。

------------------------------------
表面スラブモデル
------------------------------------

.. math::
  E_{\rm TFD}\left[ \rho \right]
  = C_{\rm F} \int d\boldsymbol{r} \left( \rho(\boldsymbol{r}) \right)^{5/3}
  + \int d\boldsymbol{r} v(\boldsymbol{r}) \rho(\boldsymbol{r})
  + E_{\rm H} \left[ \rho \right]
  - C_{\rm x} \int d\boldsymbol{r} \left( \rho(\boldsymbol{r}) \right)^{4/3}

.. math::
  C_{\rm x} = \frac{3}{4} \left( \frac{3}{\pi} \right)^{1/3}

-----------------------------------------
界面モデリング
-----------------------------------------

.. math::
  T_{\rm W}\left[ \rho \right] = C_{\rm W}
  \int d\boldsymbol{r}
  \frac{\left| \nabla\rho(\boldsymbol{r}) \right|^2}{\rho(\boldsymbol{r})}

.. math::
  C_{\rm W} = \frac{\hbar^2}{8m}

Thomas-Fermi-Weiszacker model

.. math::
  E_{\rm TF\lambda W}\left[ \rho \right]
  = E_{\rm TF}\left[ \rho \right] + \lambda T_{\rm W}\left[ \rho \right]

Thomas-Fermi-Dirac-Weiszacker model

.. math::
  E_{\rm TFD\lambda W}\left[ \rho \right]
  = E_{\rm TFD}\left[ \rho \right] + \lambda T_{\rm W}\left[ \rho \right]

-----------------------------------------------------
分子挿入
-----------------------------------------------------

.. math::
  \frac{ \delta T_{\rm W}\left[ \rho \right] }{\delta \rho(\boldsymbol{s})}
  &= - C_{\rm W}
  \frac{\left| \nabla\rho(\boldsymbol{s}) \right|^2}{\left(\rho(\boldsymbol{s})\right)^2}
  + C_{\rm W}
  \int d\boldsymbol{r}
  \frac{1}{\rho(\boldsymbol{r})}
  \frac{ \delta }{\delta \rho(\boldsymbol{s})}
  \left| \nabla\rho(\boldsymbol{r}) \right|^2 \\
  &= - C_{\rm W}
  \frac{\left| \nabla\rho(\boldsymbol{s}) \right|^2}{\left(\rho(\boldsymbol{s})\right)^2}
  + 2C_{\rm W}
  \int d\boldsymbol{r}
  \frac{\nabla\rho(\boldsymbol{r})}{\rho(\boldsymbol{r})}
  \cdot
  \nabla \delta(\boldsymbol{r}-\boldsymbol{s}) \\
  &= - C_{\rm W}
  \frac{\left| \nabla\rho(\boldsymbol{s}) \right|^2}{\left(\rho(\boldsymbol{s})\right)^2}
  - 2C_{\rm W}
  \int d\boldsymbol{r}
  \delta(\boldsymbol{r}-\boldsymbol{s})
  \nabla
  \cdot
  \left(
  \frac{\nabla\rho(\boldsymbol{r})}{\rho(\boldsymbol{r})}
  \right) \\
  &= C_{\rm W}
  \frac{\left| \nabla\rho(\boldsymbol{s}) \right|^2}{\left(\rho(\boldsymbol{s})\right)^2}
  - 2C_{\rm W}
  \frac{\nabla^2\rho(\boldsymbol{s})}{\rho(\boldsymbol{s})}


-----------------------------------------------------
孤立分子のスーパーセル
-----------------------------------------------------

.. math::
  T_{\rm W}\left( \rho_1, \rho_2, \cdots, \rho_{N_{\rm grid}} \right) = C_{\rm W}
  \sum_{i=1}^{N_{\rm grid}}
  \frac{ \left(g^x_i\right)^2 + \left(g^y_i\right)^2 + \left(g^z_i\right)^2 }{\rho_i}
  \Delta V

.. math::
  g_i^{\xi} = \sum_{j=1}^{N_{\rm grid}} C^{\xi}_{ij} \rho_j
  \quad
  \left( \xi = x,y,z \right)

汎関数微分

.. math::
  \frac{\partial T_{\rm W}}{\partial \rho_p}
  = &- C_{\rm W} \Delta V
  \frac{ \left(g^x_p\right)^2 + \left(g^y_p\right)^2 + \left(g^z_p\right)^2 }{\rho_p^2} \\
  &+ 2 C_{\rm W} \Delta V \sum_{i=1}^{N_{\rm grid}}
  \frac{ g^x_i C_{ip}^x + g^y_i C_{ip}^y + g^z_i C_{ip}^z }{\rho_i}



