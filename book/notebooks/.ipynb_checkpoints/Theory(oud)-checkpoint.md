::: {#3b97b17e-594f-4229-8615-8537876ff346 .cell .markdown}
# Theory
:::

::: {#071926b8-2ad4-4ab0-ba08-c3e0540cd63f .cell .markdown}
**Derivation of two level system**
:::

::: {#8eeced3e-31db-43d3-994d-69ccb07cbfba .cell .markdown}
The 2 level system we decided to model is a resonator-transmon system
which has been capacitively coupled, as can be seen in the figure below.
Part (a) shows the circuit design with the resonator part on the left
and the transmon on the right. In (b) is a simplified schematic of the
transmon device (not to scale). {cite:p}`Koch2007`
:::

::: {#43fb43e7-545c-474c-9a96-b35f482afdcd .cell .markdown}
![alt text](../figures/Coupling-a-transmon-to-a-resonator-a-Effective-circuit-diagram-showing-the-transmon.png)
:::

::: {#1d762924-8fbd-478b-abbe-bef761dd1ea4 .cell .markdown}
The 2 approximations that are going to be made to turn this system into
a 2-level system are:

1.  The resonator-transmon in it\'s current state has anhormonicity, but
    that doesn\'t exclude the higher excited states. For this to happen
    the system needs to be truncated. Luckely the anharmonicity creates
    a big gap between the first and second excited state, which makes
    truncation viable.
2.  Secondly the rotating wave approximation is going to be applied to
    get rid of counter rotating terms. This simplifies the model and
    allows us to analytically solve it, whoever this also makes it so
    the model fails in some cases.

The analytical solution will be derived with the help of J.Koch\'s paper
on charge-insensitive qubit design derived from the cooper pair box,
{cite}`Koch2007` and the lecture notes from L.DiCarlo,
\[cite\]`DiCarlo2025`.
:::

::: {#7f51312e-c3c2-4012-ba70-b0b8b439cdcc .cell .markdown}
Starting from the lagrangian we can derive the Jaynes-cummings
hamiltonian as follows:
:::

::: {#18ba8d9f-b25a-41f5-9ad4-399ece17a50b .cell .markdown}

$$\mathcal{L} = E_{capacitor}-E_{inductor}$$

$$E_{cap} = \frac{1}{2}C_{r}\dot{\Phi}_{r}^2 + \frac{1}{2}C_{t}\dot{\Phi}_{t}^2 + \frac{1}{2}C_{c}(\dot{\Phi}_{r}-\dot{\Phi}_{t})^2$$

$$E_{ind} = \frac{\Phi_{r}^2}{2L_{r}}-E_{J}(\Phi_{ext})\cos(2\pi\frac{\Phi_{t}}{\Phi_{0}}+\phi\Phi_{ext})$$
:::

::: {#63add2d1-8f06-4c63-a83e-97b9b242c0a1 .cell .markdown}
Here we have the subscripts for the resonator and transmon as $_{r}$ and
$_{t}$ respectively. The $\Phi_{i}$ terms represent the flux through the
top nodes, opposite to ground and seperated by the capacitors $C_{i}$.
$E_{J}$ represents the josephson energy tied to the transmon (squid
loop). The capacitor $C_{c}$, ($C_{g}$ in the figure), takes the roll of
the capacitive coupling between the 2 systems.
:::

::: {#95f51d4c-ac44-425e-951f-eb82022af6ea .cell .markdown}
To get the hamiltonian, we first calculate the variable charge
conjugates of the 2 fluxes:
:::

::: {#e2bc95d7-1879-434b-98ab-27b0e0663a99 .cell .markdown}

$$Q_{r}=\frac{\partial \mathcal{L}}{\partial \dot{\Phi}_{r}} = (C_r+C_c)\dot{\Phi}_r-C_{c}\dot{\Phi}_t$$

$$Q_{t}=\frac{\partial \mathcal{L}}{\partial \dot{\Phi}_{t}} = (C_t+C_c)\dot{\Phi}_t-C_{c}\dot{\Phi}_r$$
:::

::: {#a5db51dc-4e40-4c2f-99e3-08ef312f0bc2 .cell .markdown}
Use matrix notation: \$ H = Q\_{i}\^{T}\\dot{\\Phi}*i - \\mathcal{L} =
\\frac{1}{2}Q\^{T}C\^{-1}Q + E*{ind} \$

and

\$ C\^{-1} =\\frac{1}{(C_r+C_c)(C_t+C_c)-C\_{c}\^2}
\\begin{pmatrix}C_t+C_c & C_c \\ C_c & C_r+C_c \\end{pmatrix} \$ to get:
:::

::: {#e33f93a4-7a5c-4af3-9756-4ef29107a51d .cell .markdown}

$$H = \frac{1}{2}\frac{C_t + C_c}{C_{r}C_t + C_{r}C_c + C_{t}C_c} Q_r^{\,2}+ \frac{1}{2}\frac{C_r + C_c}{C_{r}C_t + C_{r}C_c + C_{t}C_c} Q_t^{\,2}+ \frac{C_c}{C_{r}C_t + C_{r}C_c + C_{t}C_c} Q_r Q_t + \frac{1}{2L_r} \Phi_r^2 - E_{J}(\Phi_{ext})\cos(2\pi\frac{\Phi_{t}}{\Phi_{0}}+\phi\Phi_{ext})$$
:::

::: {#ef7b89f4-3bb5-4e98-bfbe-f7199434d99c .cell .markdown}
This is the base hamiltonian for a resonator-transmon system, without
any assumptions or approximations. The $Q_i$ and $\Phi_i$ in this
hamiltonian are operators with commutation relation
$[Q_i,\Phi_i]= -i\hbar$.
:::

::: {#fc93bd31-8525-443e-b57b-1e30705b7bcc .cell .markdown}
Introduce effective capacitances:

Resonator:
$C_{r,eff} = \frac{1}{\frac{C_t + C_c}{C_{r}C_t + C_{r}C_c + C_{t}C_c}}$

Transmon:
$C_{t,eff} = \frac{1}{\frac{C_r + C_c}{C_{r}C_t + C_{r}C_c + C_{t}C_c}}$

Coupling:
$C_{c,eff} = \frac{1}{\frac{C_c}{C_{r}C_t + C_{r}C_c + C_{t}C_c}}$
:::

::: {#45e3e201-13f3-497a-b310-7d1ca339d3d2 .cell .markdown}
First we take a look at the resonator terms:

$$H_r = \frac{1}{2} C_{r,eff}Q_r^{\,2}+ \frac{1}{2L_r} \Phi_r^2$$

This is in the standard LC-resonator form. This hamiltonian can thus be
reduced to the standard form:

$$H_r = \hbar \omega_r (a^{\dagger} a+\frac{1}{2})$$

Discarding constant off-set gives:

$$H_r \approx \hbar \omega_r a^{\dagger} a$ with $\omega_r = \frac{1}{\sqrt{L C_{r,eff}}}$$
:::

::: {#9585680f-7c4d-46d8-b79e-3e4ebe709e38 .cell .markdown}
Next we expand the
$- E_{J}(\Phi_{ext})\cos(2\pi\frac{\Phi_{t}}{\Phi_{0}}+\phi\Phi_{ext})$
term using a taylor expansion:

$$cos(A) \approx 1-\frac{1}{2}A^2 +\frac{1}{24}A^4$$

Neglecting the constant off-set terms again gives:

$$- E_{J}(\Phi_{ext})\cos(2\pi\frac{\Phi_{t}}{\Phi_{0}}+\phi\Phi_{ext}) = \frac{1}{2}E_J(\phi)^2 +\frac{1}{24}E_J (\phi)^4$$
:::

::: {#132bc9ac-cecf-4c88-ac09-73413efa646e .cell .markdown}
Here the extra phase term in the cosine has been neglected and the
$\Phi_t$ has been substituted by the operator:

$\phi = 2 \pi \frac{\Phi_t}{\Phi_0}$ , (this is an operator with n).

The charge operator can then also be rewritten to the unitless operator
n:

$$Q_r = 2 e n_r$$

With commutator relation between them: $[\phi,n]=i$

Lastly, we introduce $E_c = \frac{e^2}{2 C_{t,eff}}$ , the charging
energy.
:::

::: {#1d24d034-4ffe-4153-8e44-8b39d94df8b0 .cell .markdown}
The hamiltonian then becomes:

$$H = \hbar \omega_r a^{\dagger} a - E_c(\frac{E_J}{2 E_c})^{\frac{1}{2}} (b^{\dagger}-b)^2 +\frac{1}{2} E_J (\frac{2 E_c}{E_J})^{\frac{1}{2}} (b^{\dagger}+b)^2 - \frac{1}{24} E_J (\frac{2 E_c}{E_J})(b^{\dagger}+b)^4 + \frac{i e}{2 C_{c,eff}} (\frac{E_J}{2 E_c})^{\frac{1}{4}} (\frac{\hbar C_{r,eff} \omega_r}{2})^\frac{1}{2} (b^{\dagger}-b)(a^{\dagger}-a)$$

Simplifying then gives:

$$H = \hbar \omega_r a^{\dagger} a - (\frac{E_J E_c}{2})^{\frac{1}{2}} (b^{\dagger}-b)^2 +(\frac{E_J E_c}{2})^{\frac{1}{2}} (b^{\dagger}+b)^2 - \frac{E_J}{12} (b^{\dagger}+b)^4 + \frac{i e}{2 C_{c,eff}} (\frac{E_J}{2 E_c})^{\frac{1}{4}} (\frac{\hbar C_{r,eff} \omega_r}{2})^\frac{1}{2} (b^{\dagger}-b)(a^{\dagger}-a)$$
:::

::: {#57e27936-a6b3-4826-9a01-73dcdbe18a3b .cell .markdown}
**Now comes the rotating wave approximation**, which states that only
states that preserve the eigenstate (/conserve energy) are good. Meaning
$AA$ and $A^{\dagger}A^{\dagger}$ are discarded.

This is only allowed in the limit of $E_J >> E_c$. (As will be simulated
later on).

(The approximation for the term $\frac{E_J}{12} (b^{\dagger}+b)^4$ then
becomes: $\frac{E_J}{12} (12 b^{\dagger}b + 6b^{\dagger}b^{\dagger}bb)$)
:::

::: {#68f87d92-ca76-4e6c-b9c5-465e438c0dab .cell .markdown}
$$H = \hbar \omega_r a^{\dagger} a + 2(\frac{E_J E_c}{2})^{\frac{1}{2}} (b^{\dagger}b+b b^{\dagger}) - \frac{E_J}{2} (2 b^{\dagger}b+b^{\dagger}b^{\dagger}bb) + \frac{i e}{2 C_{c,eff}} (\frac{E_J}{2 E_c})^{\frac{1}{4}} (\frac{\hbar C_{r,eff} \omega_r}{2})^\frac{1}{2} (-b^{\dagger}a-ba^{\dagger})$$
:::

::: {#43ed0c60-e4fa-4982-9017-132b265e80c3 .cell .markdown}
Use commutation relations and pauli matrix notation:

$[a,a^\dagger]=1$ &
$\sigma_z = \sigma_- \sigma_+ -\sigma_+ \sigma_- = b b^{\dagger} - b^{\dagger}b$
, aswell as defining the g factor:

$$g = -\frac{e}{2 C_{c,eff}} (\frac{E_J C_{r,eff}^2 \omega_r^2}{8 E_c \hbar ^2})^{\frac{1}{4}}$$
:::

::: {#6af88333-a512-4c45-9121-ec65ffcba545 .cell .markdown}
Split into 2 parts:

- Transmon
- Coupling

The **Coupling** term gives the straightforward hamiltonian:
$H= i \hbar g(a^\dagger \sigma_- + a\sigma_+)$.

The **transmon** part gives hamiltonian:
$H = ((8E_J E_c)^\frac{1}{2} -E_c) b^\dagger b - \frac{E_c}{2} b^\dagger b^\dagger bb$

Truncating the energy levels to 2 lowest gives:
$\hbar \omega_{01} = ((8E_J E_c)^\frac{1}{2} -E_c)$, so
$= \hbar \omega_{01} b^\dagger b - \frac{E_c}{2} b^\dagger b^\dagger bb$

Inputting density matrix form of ladder operators: $b^\dagger = |1><0|$
and $b = |0><1|$ and using that the states are diagonal: $<i|j> = 0$ for
$i \neq j$ and $1$ for $i = j$.

gives:
$\hbar \omega_{01} |1><0|0><1| - \frac{E_c}{2} |1><0|1><0|0><1|0><1| = \hbar \omega_{01} |1><1|$

Which depending on convention of $\sigma_z$ can be written as:
$= \frac{\hbar \omega_{01}}{2} (\sigma_z + I)$ , where $I$ is the unit
matrix and $\sigma_z =
\begin{pmatrix}
-1 & 0 \\
0 & 1
\end{pmatrix}$

(This unit matrix term can then again be disregarded as a constant
off-set)
:::

::: {#8b72e3d6-3e5d-47ce-9a08-42078437c17e .cell .markdown}
Combining everything then gives the end result:
:::

::: {#6b381291-b362-4c4e-bd89-3ef985dc0dc4 .cell .markdown}
$$H = \hbar \omega_r a^\dagger a + \frac{\hbar \omega_t}{2}\sigma_z +i\hbar g(a^\dagger \sigma_{-} + a\sigma_{+})$$
:::

::: {#32b0ee4b-4bff-4bcd-8eeb-9dcd7ccdf60d .cell .markdown}
This result is the same as derived in {cite}`Koch2007` eq(3.8). Which
reads:
$H_{eff}=\frac{\hbar \omega_{01}'}{2}\sigma_z + (\hbar \omega_{r}'+\hbar \chi \sigma_z)a^\dagger a$
:::

::: {#bdbb5a03-d976-47df-b177-d440d5eb2ddc .cell .markdown}
## The Rotating wave approximation and where it theoretically fails
:::

::: {#caaeb4fb-e743-4b07-bf0b-b14127513e95 .cell .markdown}
Until now the rotating wave approximation has only been applied to the
transmon-resonator system, but in essence it stays the same for all
2-level systems. The Jaynes-Cummings hamiltonian is described as:

- \$H = \\hbar \\omega a\^{\\dagger}a + E\_{1}S\_{11} + E\_{2}S\_{22} +
  \\frac{\\hbar}{2} \\Omega_1(a\^{\\dagger}S\_{12} + S\_{21}a) \$, for 2
  level atom states. (Shore, B. W., & Knight, P. L. 1993).
- $H = \omega_0 S_z + \omega a^{\dagger}a +\epsilon (a^{\dagger}S_{-} + S_{+}a)$,
  for 2 level photon system. (Ng, K. M., Lo, C. F., & Liu, K. L. 1999).

Without the rotating wave approximation, (with the counter rotating
terms), the hamiltonian
becomes:$H = \hbar \omega_r a^{\dagger}a + E_{1}S_{11} + E_{2}S_{22} + \frac{\hbar}{2} \Omega_1(a^{\dagger} + a)(S_{12}+S_{21})$.
(Shore, B. W., & Knight, P. L. 1993) & (Omolo, J. A. 2021).
:::

::: {#e8f08de3-48cd-4a95-90da-ce3f503eaa13 .cell .markdown}
The original approximation assumed that each photon change, balances out
an atomic change in such a way that the combination of photon energy and
atomic energy stayed constant. Jaynes and Cummings realized that, just
as with semiclassical theory, a more complete description of radiation
theory should include additional terms, (counter rotating terms).
(Shore, B. W., & Knight, P. L. 1993)
:::

::: {#6113d0c4-669c-4fe3-9d47-4bb0434f19f4 .cell .code}
``` python
```
:::
