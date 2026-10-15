式 (E.13) に含まれる外国短期金利の積分を、外国numeraire \(N_f\) の比に置き換え、さらに式 (E.12) を代入したものです。
一見かなり複雑ですが、実際には次の3段階で整理できます。
1. \(-\int_t^T r_f(u)du\) を \(N_f(t)/N_f(T)\) で書き換える。
2. 式 (E.12) を代入し、時点 \(t\) までの既知の部分と \(t\) 以降の確率積分に分ける。
3. 正規分布の指数期待値を計算し、\(\gamma_f\) によるquanto adjustmentが相関項を相殺することを確認する。
最終的には、
\[
\boxed{
P_f(t,T)
=
\frac{P_f(0,T)}{P_f(0,t)}
\exp\left[
-\bigl(H_f(T)-H_f(t)\bigr)z_f(t)
-\frac12\bigl(H_f^2(T)-H_f^2(t)\bigr)\zeta_f(t)
\right]
}
\]

という、外国通貨自身のLGM zero-bond formulaが再び得られます。
それでは、途中を省略せずに追います。
1. まずE.13の外国金利項を変換する
式 (E.10) は、
\[
\begin{aligned}
N_f(t)=N_f(0)\exp\Bigg[
&\int_0^t r_f(u)du
+\frac12\int_0^tH_f^2(u)\alpha_f^2(u)du\\
&+\int_0^tH_f(u)\gamma_f(u)du
+\int_0^tH_f(u)\alpha_f(u)dW_f(u)
\Bigg]
\end{aligned}
\]

でした。
これを時点 \(T\) と \(t\) について引き算すると、
\[
\begin{aligned}
\log\frac{N_f(T)}{N_f(t)}
={}&
\int_t^T r_f(u)du
+\frac12\int_t^T H_f^2(u)\alpha_f^2(u)du\\
&+\int_t^T H_f(u)\gamma_f(u)du
+\int_t^T H_f(u)\alpha_f(u)dW_f(u).
\end{aligned}
\]

したがって移項すれば、
\[
\boxed{
\begin{aligned}
-\int_t^T r_f(u)du
={}&
\log\frac{N_f(t)}{N_f(T)}
+\frac12\int_t^TH_f^2(u)\alpha_f^2(u)du\\
&+\int_t^TH_f(u)\gamma_f(u)du
+\int_t^TH_f(u)\alpha_f(u)dW_f(u).
\end{aligned}
}
\tag{A}
\]

この式 (A) が、今回の長い式の直接の出発点です。
E.13の指数に入っていた \(-\int r_f\) を、右辺で置き換えたわけです。
2. 次に \(N_f(t)/N_f(T)\) をE.12で書く
式 (E.12) は、
\[
\begin{aligned}
N_f(s)=\frac1{P_f(0,s)}
\exp\Bigg[
&H_f(s)\int_0^s\alpha_f(u)dW_f(u)\\
&+H_f(s)\int_0^s\gamma_f(u)du
+\frac12H_f^2(s)\zeta_f(s)
\Bigg]
\end{aligned}
\]

です。
時点 \(t,T\) の比を取ると、
\[
\begin{aligned}
\frac{N_f(t)}{N_f(T)}
={}&\frac{P_f(0,T)}{P_f(0,t)}
\exp\Bigg[
-H_f(T)\int_0^T\alpha_f dW_f\\
&+H_f(t)\int_0^t\alpha_f dW_f\\
&-H_f(T)\int_0^T\gamma_fdu
+H_f(t)\int_0^t\gamma_fdu\\
&-\frac12H_f^2(T)\zeta_f(T)
+\frac12H_f^2(t)\zeta_f(t)
\Bigg].
\end{aligned}
\]

これを式 (A) に代入すると、質問にある長い指数関数がそのまま現れます。
したがって、ここまでの変形は確率論的な近似を一切使っていません。単なる代数的な代入と整理です。

3. 長い指数を整理する
ここからが少し大変なところです。
記号を簡単にするため、
\[
\Delta H_f=H_f(T)-H_f(t)
\]

と置きます。
また、国内LGM measureの下では、
\[
z_f(t)
=
\int_0^t\gamma_f(u)du
+
\int_0^t\alpha_f(u)dW_f(u)
\]

でした。
3.1 Foreign Brownianの項
質問の式から、外国Brownianに関係する項を取り出すと、
\[
\begin{aligned}
&
-H_f(T)\int_0^T\alpha_f(u)dW_f(u)\\
&+H_f(t)\int_0^t\alpha_f(u)dW_f(u)\\
&+\int_t^TH_f(u)\alpha_f(u)dW_f(u).
\end{aligned}
\]

ここで、
\[
\int_0^T=\int_0^t+\int_t^T
\]

と分けると、
\[
\boxed{
\begin{aligned}
={}&
-\Delta H_f
\int_0^t\alpha_f(u)dW_f(u)\\
&-\int_t^T
[H_f(T)-H_f(u)]
\alpha_f(u)dW_f(u).
\end{aligned}
}
\]

になります。
3.2 Foreign driftの項
同様に、\(\gamma_f\) を含む項は、
\[
\begin{aligned}
&
-H_f(T)\int_0^T\gamma_f(u)du\\
&+H_f(t)\int_0^t\gamma_f(u)du\\
&+\int_t^TH_f(u)\gamma_f(u)du
\end{aligned}
\]

です。
整理すると、
\[
\boxed{
\begin{aligned}
={}&
-\Delta H_f\int_0^t\gamma_f(u)du\\
&-\int_t^T
[H_f(T)-H_f(u)]
\gamma_f(u)du.
\end{aligned}
}
\]

となります。
3.3 2つを合わせる
ここで、最初の項同士をまとめると、
\[
\begin{aligned}
&-\Delta H_f
\left[
\int_0^t\alpha_f(u)dW_f(u)
+
\int_0^t\gamma_f(u)du
\right]\\
&\qquad=
\boxed{-\Delta H_f z_f(t)}.
\end{aligned}
\]

これが重要です。
外国金利の状態変数 \(z_f(t)\) が自然に現れました。
残りの \(t\) から \(T\) までの部分は、
\[
-\int_t^T[H_f(T)-H_f(u)]
\left[
\gamma_f(u)du+\alpha_f(u)dW_f(u)
\right]
\]

です。
3.4 \(\zeta_f\) の項
次の3項をまとめます。
\[
\begin{aligned}
&
-\frac12H_f^2(T)\zeta_f(T)
+\frac12H_f^2(t)\zeta_f(t)\\
&+\frac12\int_t^TH_f^2(u)\alpha_f^2(u)du.
\end{aligned}
\]

ここで、
\[
\zeta_f(T)
=
\zeta_f(t)+\int_t^T\alpha_f^2(u)du
\]

を代入すると、
\[
\boxed{
\begin{aligned}
={}&
-\frac12
[H_f^2(T)-H_f^2(t)]\zeta_f(t)\\
&-\frac12\int_t^T
[H_f^2(T)-H_f^2(u)]
\alpha_f^2(u)du.
\end{aligned}
}
\]

となります。
ここでも、最終的に欲しいzero-bond formulaの
\[
-\frac12[H_f^2(T)-H_f^2(t)]\zeta_f(t)
\]

が現れました。

4. 期待値の計算に必要な項だけが残る
ここまでの整理で、
\[
\begin{aligned}
P_f(t,T)
={}&
\frac{P_f(0,T)}{P_f(0,t)}
\exp\left[
-\Delta H_fz_f(t)
-\frac12(H_f^2(T)-H_f^2(t))\zeta_f(t)
\right]\\
&\times \mathbb E_t^d[e^{A+B}]
\end{aligned}
\]

と書けます。
ここで \(A\) は将来のdeterministicな積分、\(B\) はGaussianな確率積分です。
式を短くするため、
\[
k(u)=H_f(T)-H_f(u),
\quad
b(u)=H_d(u)\alpha_d(u),
\quad
c(u)=\sigma_x(u)
\]

と置きます。
すると、
\[
\boxed{
\begin{aligned}
A=\int_t^T\Big[
&-k\gamma_f
-\frac12(H_f^2(T)-H_f^2(u))\alpha_f^2\\
&-\frac12c^2
-\frac12b^2
+\rho_{xd}bc
\Big]du
\end{aligned}
}
\]

および、
\[
\boxed{
B=
\int_t^T
\left[
-k\alpha_fdW_f
+c\,dW_x
-b\,dW_d
\right].
}
\]

となります。
ここで注意するのは、\(B\) に含まれる3つのBrownian motionが相関していることです。
5. Gaussianの指数期待値を計算する
\(B\) は条件付き平均0の正規確率変数なので、
\[
\boxed{
\mathbb E_t^d[e^{A+B}]
=
\exp\left(A+\frac12\operatorname{Var}_t(B)\right)
}
\]

です。
したがって、必要なのは \(B\) の分散です。
Brownian motion間の相関を、
\[
dW_f\,dW_x=\rho_{fx}dt
\]

\[
dW_f\,dW_d=\rho_{df}dt
\]

\[
dW_x\,dW_d=\rho_{xd}dt
\]

とします。
すると、
\[
\boxed{
\begin{aligned}
\operatorname{Var}_t(B)
=
\int_t^T\Big[
&k^2\alpha_f^2+c^2+b^2\\
&-2\rho_{fx}k\alpha_fc\\
&+2\rho_{df}k\alpha_fb\\
&-2\rho_{xd}bc
\Big]du.
\end{aligned}
}
\]

この計算では、一般的な
\[
\operatorname{Var}(X+Y+Z)
=
\operatorname{Var}(X)+\operatorname{Var}(Y)+\operatorname{Var}(Z)
+2\operatorname{Cov}(X,Y)
+2\operatorname{Cov}(X,Z)
+2\operatorname{Cov}(Y,Z)
\]

を使っているだけです。

6. 最後の相殺を確認する
今、
\[
A+\frac12\operatorname{Var}_t(B)
\]

を計算します。
まず、FXだけの項、
\[
-\frac12c^2+\frac12c^2=0
\]

が相殺します。
国内金利だけの項も、
\[
-\frac12b^2+\frac12b^2=0
\]

です。
さらに国内金利とFXの相関項も、
\[
\rho_{xd}bc-\rho_{xd}bc=0
\]

となります。
残るのは、
\[
\begin{aligned}
A+\frac12\operatorname{Var}_t(B)
=
\int_t^T\Big[
&-k\gamma_f\\
&-\frac12(H_f^2(T)-H_f^2(u))\alpha_f^2\\
&+\frac12k^2\alpha_f^2\\
&-\rho_{fx}k\alpha_fc\\
&+\rho_{df}k\alpha_fb
\Big]du.
\end{aligned}
\]

ここで、
\[
\begin{aligned}
&-\frac12(H_f^2(T)-H_f^2(u))\alpha_f^2
+\frac12k^2\alpha_f^2\\
&\qquad=
-kH_f(u)\alpha_f^2(u)
\end{aligned}
\]

という恒等式が成立します。
したがって、
\[
\boxed{
\begin{aligned}
A+\frac12\operatorname{Var}_t(B)
=
-\int_t^Tk(u)\Big[
&\gamma_f(u)
+H_f(u)\alpha_f^2(u)\\
&+\rho_{fx}\alpha_f(u)\sigma_x(u)\\
&-\rho_{df}\alpha_f(u)H_d(u)\alpha_d(u)
\Big]du.
\end{aligned}
}
\]

ここで第12章の重要な結果、
\[
\boxed{
\gamma_f
=
-H_f\alpha_f^2
-\rho_{fx}\alpha_f\sigma_x
+\rho_{df}H_d\alpha_d\alpha_f
}
\]

を代入します。
すると角括弧の中身は、
\[
\begin{aligned}
&
\underbrace{-H_f\alpha_f^2
+H_f\alpha_f^2}_{0}\\
&+
\underbrace{-\rho_{fx}\alpha_f\sigma_x
+\rho_{fx}\alpha_f\sigma_x}_{0}\\
&+
\underbrace{\rho_{df}H_d\alpha_d\alpha_f
-\rho_{df}H_d\alpha_d\alpha_f}_{0}.
\end{aligned}
\]

すべて相殺されます。
したがって、
\[
\boxed{
A+\frac12\operatorname{Var}_t(B)=0
}
\]

であり、
\[
\boxed{
\mathbb E_t^d[e^{A+B}]=1.
}
\]

7. 最終結果
よって、先ほどの式は、
\[
\boxed{
P_f(t,T)
=
\frac{P_f(0,T)}{P_f(0,t)}
\exp\left[
-\Delta H_fz_f(t)
-\frac12(H_f^2(T)-H_f^2(t))\zeta_f(t)
\right]
}
\]

となります。
これがE.3で示したい結論です。
つまり、FX・国内金利・外国金利をすべて相関させ、domestic LGM measureで評価しても、foreign zero bondの価格は外国LGMの標準形を維持することが確認できました。
そして、この計算が成立するために、
\[
\gamma_f
=
-H_f\alpha_f^2
-\rho_{fx}\alpha_f\sigma_x
+\rho_{df}H_d\alpha_d\alpha_f
\]

という特別なdriftが必要だったわけです。
特に重要なのは、\(\gamma_f\) が単なる数学上の便宜ではなく、確率的なFX換算と相関を考慮したときに、外国債券の価格が無裁定となるための補正である、という点です。
これでAppendix E.3の長い計算が、12.1のcross-currency LGMモデルと完全につながります。
