---
reviewed_on: "2024-09-20"
---

# Mixing problem differential equations

In a room containing $50 \text{m}^3$ of air with a CO content of $0.2\%$, pure air is made to flow in at a rate of $2 \text{m}^3$ per minute. The well-mixed air flows out of the room at the same rate of $2 \text{m}^3$ per minute. If $x(t)$ is the amount of CO in cubic meters after $t$ minutes, after how many minutes will the amount of CO in the room have been reduced to half?

---

For a time $t$, the rate of change of the air in the room $\frac{ dx }{ dt }$ must be equal to the rate at which the air enters the room minus the rate at which it leaves. That is, the differential equation that models this problem is given by:

$$
\frac{ dx }{ dt } = v_i - v_o
$$

Where $v_i$ and $v_o$ are the rates of entry and exit of the substance, with units in $\frac{ \text{amount} }{ t }$.

Additionally:

$$
v_i = \text{rate of air entry } \left ( \frac{ \text{volume} }{ t }  \right ) \times \text{concentration upon entry} \left ( \frac{ \text{amount} }{ \text{volume} } \right ) \\[10 pt]
v_o = \text{rate of air exit } \left ( \frac{ \text{volume} }{ t }  \right ) \times \text{concentration upon exit } \left ( \frac{ \text{amount} }{ \text{volume} } \right ) \\[10 pt]
$$

- We assume that there is no transformation or loss of air in the room.

- If we assume that the mixture in the room is homogeneous, the concentration of the output is equal to the concentration in the room.

    $$
    C(t) = \frac{ x(t) }{ V(t) } \quad (1)
    $$

    Where $x(t)$ is the amount of substance at time $t$ and $V(t)$ is the total volume in the room at that time $t$.

$$
C(t) = \frac{ x(t) }{ 50 \text{m}^3 }
$$

$$
v_i = \frac{ 2 \text{m}^3 }{ \text{min} } * 0 = 0 \\[10 pt]
v_o = \frac{ 2 \text{m}^3 }{ \text{min} } \frac{ x(t) }{ 50 \text{m}^3 } = \frac{ x(t) }{ 25 \text{min} \text{m}^3 }
$$

> Pure air is entering.

Using $(1)$.

$$
\frac{ dx }{ dt } = -\frac{ 1 }{ 25 } x(t) \quad \int \frac{ dx }{ x } = \int { -\frac{ 1 }{ 25 } dt } \\[10 pt]
\ln | x | = -\frac{ 1 }{ 25 } t + C \\[10 pt]
x = e^{ -\frac{ 1 }{ 25 } t + C } = Ce^{ -\frac{ 1 }{ 25 } t } \quad (2)
$$

> In this case $V(t) = 50 \text{m}^3$, i.e., $V(t)$ does not vary, it is a constant.

We also know that:

$$
x(0) = 50 \frac{ 0.2 }{ 100 } = \frac{ 1 }{ 10 } \quad (3)
$$

With $(2)$ and $(3)$ we can get $C$.

$$
x(0) = Ce^{ -\frac{ 1 }{ 25 } (0) } = \frac{ 1 }{ 10 } \quad C = \frac{ 1 }{ 10 } \\[10 pt]
x(t) = \frac{ 1 }{ 10 } e^{ -\frac{ 1 }{ 25 } t }
$$

The half amount of CO in the room is:

$$
\frac{ x(0) }{ 2 } = \frac{ 1 }{ 20 }
$$

$$
\frac{ 1 }{ 10 } e^{ -\frac{ 1 }{ 25 } t } = \frac{ 1 }{ 20 } \quad e^{ -\frac{ 1 }{ 25 } t } = \frac{ 1 }{ 2 } \quad -\frac{ 1 }{ 25 } t = \ln \frac{ 1 }{ 2 } \\[10 pt]
t = -25 \ln \frac{ 1 }{ 2 } \approx 17.33 \text{ min }
$$
