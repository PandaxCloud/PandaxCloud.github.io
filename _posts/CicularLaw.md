# Cicular Law

As mentioned before, there is an analogy here with the concentration of measure phenomenon, and many of the tools used in the latter (e.g. the moment method) will also appear here. Similarly, just as many of the tools from concentration of measure could be adapted to help prove the central limit theorem, several the tools seen here will be of use in deriving the semicircular law in Section 2.4.

* 这强烈暗示着如果我们要严格地证明$M$的specturm在$z$附近，我们需要对$\sigma_n(M-zI)$提供一个下界
* 对于Hermitian矩阵，基于它的moments
  $$
  \frac{1}{n}\operatorname{tr}(\frac{1}{\sqrt{n}}M_n)^k=\int_{\mathbf{R}}x^kd\mu_{\frac{1}{\sqrt{n}}M_n}(x)
  $$
  就可以完全明白$\mu_{\frac{1}{\sqrt{n}}M_n}$的分布
* 但对于non-Hermitian矩阵，$\mu_{\frac{1}{\sqrt{n}}M_n}$的support是复平面，虽然仍有
  $$
  \frac{1}{n}\operatorname{tr}(\frac{1}{\sqrt{n}}M_n)^k=\int_{\mathbf{R}}z^kd\mu_{\frac{1}{\sqrt{n}}M_n}(z)
  $$
  由于the space of complex polynomials $P(z)$不再具有good density properties，所以moments不能唯一决定spectral measure了

* 还是拿之前的$U_0$和$U_{\varepsilon}$举例，因为
  $$
  \operatorname{tr}(\frac{1}{\sqrt{n}}U_0)^k=\operatorname{tr}(\frac{1}{\sqrt{n}}U_{\varepsilon})^k=0\text{ for } k=1,\dots,n-1
  $$
  则有
  $$
  \int_{\mathbf{R}}z^kd\mu_{\frac{1}{\sqrt{n}}U_0}(z)=\int_{\mathbf{R}}z^kd\mu_{\frac{1}{\sqrt{n}}U_{\varepsilon}}(z)=0\text{ for } k=1,\dots,n-1
  $$
  可以看到有这么多的moments相等，$\mu_{\frac{1}{\sqrt{n}}U_0}$和$\mu_{\frac{1}{\sqrt{n}}U_{\varepsilon}}$是完全不一样的
* 即使考虑对所有$k$，$\int_{\mathbf{R}}z^kd\mu=0$，也会有uncountable的probability measures可能成为这个$\mu$，比如任意一个rotationally symmetric around the origin的

* 首先，建立一个polynomial lower bound asymptotically almost surely
  $$
  \sigma_n(\frac{1}{\sqrt{n}}M_n-zI)\ge n^{-C}
  $$
* 然后利用Stieltjes transform来证明用一个合适的度量，$\nu_{n,z}$和$\nu_z$的距离是$O(n^{-c})$



* $u$是一个non-commutative, tracial的probability space $(\mathcal{A},\tau)$的一个bounded element
* 对于每个复数$z$，记$(u-z)^*(u-z)$的spectral measure是$\nu_z$

* $\nu_z$就是一个在$[0,+\infty)$上的compactly supported probability measure，定义log potential

$$
f(z)=\frac{1}{2}\int_0^{\infty}\log xd\nu_z(x)
$$

* $f$在一些点上可能等于$-\infty$，所以引入

$$
f_{\varepsilon}(z)\coloneqq\frac{1}{2}\int_0^{\infty}\log (\varepsilon+x)d\nu_z(x)\quad\text{for }\varepsilon>0
$$

* 由monotone covergence theorem，当$\varepsilon\rightarrow 0$，$f_{\varepsilon}(z)$递减点点收敛到$f(z)$

* 根据Gelfand-Naimark theorem (Exercise 2.5.10)，并且把$\mathcal{A}$嵌入到在$L^2(\tau)$上的the space of bounded operators，这样一来我们可以得到一个functional calculus

$$
f_{\varepsilon}(z)=\frac{1}{2}\tau\left(\log\left(\varepsilon+(u-z)^*(u-z)\right)\right)
$$

* $\Delta f_{\varepsilon}$在零点处是non-negative。如果把$u$换成别的任何的复数，$\Delta f_{\varepsilon}$在每处都是non-negative。从而$f_{\varepsilon}$是subharmonic，令$\varepsilon\rightarrow 0$，可知$f$也是subharmonic
* 为$u$定义Brown measure $\mu=\mu_u$
  $$
  \mu\coloneqq\frac{1}{2\pi}\Delta f
  $$
这样一来，$\mu$是一个non-negative measure
* 由Green's theorem，我们可以得到Brown measure是一个probability measure
* Exercise 2.8.13说明了用Brown measure来理解asymptotic spectral measure的局限。我们之前考虑的$U_0$和$U_{\varepsilon}$在$n\rightarrow\infty$时，都converge in the sense of $*$-moments
  * 对于non-zero $\varepsilon$，$U_{\varepsilon}$的spectral measure收敛到$u$的Brown measure
  * 但当$\varepsilon=0$，就不是这样了

  概括来讲，Brown measure是那些“普通的”矩阵spectral measure的asymptotic limit，而对于一些个别的矩阵，就不是了
* 上述为一般情形下建立circular law的机制可以用于说明Brown measure也是other models的correct asymptotic spectral limit
* 这个定理主要依靠两件事。
  * a polynomial lower bound on the least singular value. 这是更关键的，而且目前更依赖the joint independence hypothesis，所以在更一般的情形下为最小奇异值得到下界值得关注
  * the use of Talagrand's inequality to control medium singular values
