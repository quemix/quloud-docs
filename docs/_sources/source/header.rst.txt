========================================
ヘッダーメニュー（各種管理）
========================================

バルク結晶中の全ての原子核またはイオンが作るポテンシャルについて考える。
原点に置かれた１個の原子 :math:`a` が作るポテンシャルを

------------------------------
おしらせ
------------------------------

.. math::
  v_a (\boldsymbol{r}) = v_a ( \left| \boldsymbol{r} \right| ) = v_a(r)
  :label: loc1

とし、球対称性（原点からの距離のみに依存する事）を仮定する。
通常、物質科学では、原子核が作る裸のクーロンポテンシャル（ :math:`=-Z_a/r` ）か、
閉殻になっている内殻電子と原子核を一緒にしたイオンが作るポテンシャルしか考えないので、
実際上球対称ポテンシャル以外を扱うケースはまずない。

------------------------------
ヘルプ
------------------------------

:math:`\boldsymbol{R}_a` をユニットセル内の原子位置とし、
:math:`\boldsymbol{R}` を任意の格子並進ベクトルとする。
このとき、バルク結晶中の全ての原子が点 :math:`\boldsymbol{r}` に作るポテンシャルは

.. math::
  v(\boldsymbol{r}) = \sum_{\boldsymbol{R}} \sum_{a=1}^{N_{\rm atom}}
  v_a (\boldsymbol{r}-\boldsymbol{R}_a-\boldsymbol{R})
  :label: loc2

と書ける。この関数は格子ベクトルの周期性を持つ。すなわち

------------------------------
ポイント & ストレージ
------------------------------

.. math::
  v(\boldsymbol{r}+\boldsymbol{R}') & = & \sum_{\boldsymbol{R}} \sum_{a=1}^{N_{\rm atom}}
  v_a (\boldsymbol{r}+\boldsymbol{R}'-\boldsymbol{R}_a-\boldsymbol{R})
  \\
  & = & \sum_{\boldsymbol{R}''} \sum_{a=1}^{N_{\rm atom}}
  v_a (\boldsymbol{r}-\boldsymbol{R}_a-\boldsymbol{R}'') = v(\boldsymbol{r})
  :label: loc3

となるので、フーリエ級数で表す事もできる。

------------------------------
グループ管理
------------------------------

.. math::
  v(\boldsymbol{r}) = \sum_{\boldsymbol{G}} v(\boldsymbol{G}) 
  e^{ i\boldsymbol{G} \cdot \boldsymbol{r} }
  :label: loc4

:math:`\boldsymbol{G}` は逆格子ベクトルであり、
全ての実格子ベクトル :math:`\boldsymbol{R}` に対して、

.. math::
  e^{i \boldsymbol{G} \cdot \boldsymbol{R}} = 1

という関係を満たすものになっている。

------------------------------
ユーザー管理
------------------------------

ユニットセルの体積を :math:`\Omega` とすると、フーリエ係数 :math:`v(\boldsymbol{G})` は次のように
計算される。

.. math::
  \frac{1}{\Omega} \int_{\Omega} d\boldsymbol{r}
  v(\boldsymbol{r}) e^{-i\boldsymbol{G}\cdot\boldsymbol{r}}
  = \frac{1}{\Omega} \sum_{\boldsymbol{G}'} v(\boldsymbol{G}')
  \int_{\Omega} d\boldsymbol{r}
  e^{ i \left( \boldsymbol{G}'-\boldsymbol{G} \right) \cdot \boldsymbol{r} }
  = v(\boldsymbol{G})
  :label: loc5

ここで、

.. math::
  \int_{\Omega} d\boldsymbol{r} e^{ i \boldsymbol{G} \cdot \boldsymbol{r} }
  =
  \left\{
  \begin{array}{cc}
  \Omega & \left(\boldsymbol{G} = 0 \right) \\
  0 & \left(\boldsymbol{G} \ne 0 \right)
  \end{array}
  \right.
  :label: loc6

となる事を用いた。もう一度、今度は :math:`v(\boldsymbol{r})` に :eq:`loc2` 式を代入して
フーリエ係数の計算を行なう。

.. math::
  v_\boldsymbol{G}
  & = &
  \frac{1}{\Omega} \int_{\Omega} d\boldsymbol{r}
  v(\boldsymbol{r}) e^{-i\boldsymbol{G}\cdot\boldsymbol{r}}
  \\
  & = &
  \frac{1}{\Omega} \sum_{\boldsymbol{R}} \sum_{a=1}^{N_{\rm atom}}
  \int_{\Omega} d\boldsymbol{r}
  v_a (\boldsymbol{r}-\boldsymbol{R}_a-\boldsymbol{R})
  e^{ -i \boldsymbol{G} \cdot \boldsymbol{r} }
  \\
  & = &
  \frac{1}{\Omega} \sum_{\boldsymbol{R}} \sum_{a=1}^{N_{\rm atom}}
  \int_{\Omega} d\boldsymbol{r}
  v_a (\boldsymbol{r}-\boldsymbol{R}_a-\boldsymbol{R})
  e^{ -i \boldsymbol{G} \cdot (\boldsymbol{r}-\boldsymbol{R}) }
  \\
  & = &
  \frac{1}{\Omega} \sum_{a=1}^{N_{\rm atom}}
  \int d\boldsymbol{r}
  v_a (\boldsymbol{r}-\boldsymbol{R}_a)
  e^{ -i \boldsymbol{G} \cdot \boldsymbol{r} }
  \\
  & = &
  \frac{1}{\Omega} \sum_{a=1}^{N_{\rm atom}}
  e^{ -i \boldsymbol{G} \cdot \boldsymbol{R}_a }
  \int d\boldsymbol{r}
  v_a (\boldsymbol{r})
  e^{ -i \boldsymbol{G} \cdot \boldsymbol{r} }

ここで積分範囲がユニットセル内の空間から全空間になっている事に注意する。最後の積分は、
平面波の多重極展開の式

.. math::
  e^{ i \boldsymbol{G} \cdot \boldsymbol{r} } =
  \sum_{l=0}^{\infty} \sum_{m=-l}^{l} 4\pi i^l j_l(Gr)
  Y_{lm}^*(\hat{G}) Y_{lm}(\hat{r})

を用いて次のように計算される
（ちなみに :math:`j_l` は球ベッセル関数、 :math:`Y_{lm}` は球面調和関数である）。

.. math::
  \int d\boldsymbol{r}
  v_a (\boldsymbol{r})
  e^{ -i \boldsymbol{G} \cdot \boldsymbol{r} }
  & = &
  \sum_{l=0}^{\infty} \sum_{m=-l}^{l} 4\pi (-i)^l Y_{lm}(\hat{G})
  \int_0^\infty dr r^2 v_a(r) j_l(Gr)
  \int d\hat{r}  \sqrt{4\pi} Y_{00}(\hat{r}) Y_{lm}^*(\hat{r})
  \\
  & = &
  4\pi \int_0^\infty dr r^2 v_a(r) j_0(Gr)  \equiv  4\pi v_a(G)

動径積分 :math:`v_a(G)` は、 :math:`v_a(r)` がクーロンポテンシャルの場合は

.. math::
  v_a(G) = -\frac{Z_a}{G^2}

と解析的に求められる。それ以外の場合、例えば擬ポテンシャル法で :math:`v_a(r)` 
が数値データとして与えられるような場合には、動径積分は数値積分で評価する必要がある。
その際、ポテンシャルは無限遠方まで有意な値を持つ（ :math:`\simeq -Z_a/r`）にも関わらず、
データは有限の距離までで打ち切られたものしか与えられない事に注意が必要である。

結果をまとめると、フーリエ係数 :math:`v(\boldsymbol{G})` は、

.. math::
  v(\boldsymbol{G}) =
  \frac{4\pi}{\Omega} \sum_{a=1}^{N_{\rm atom}}
  v_a(G)  e^{ -i \boldsymbol{G} \cdot \boldsymbol{R}_a }

という式で求める事ができる。これをフーリエ変換して実空間の関数に戻せば :math:`v(\boldsymbol{r})` 
が得られる。