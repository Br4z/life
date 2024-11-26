# Discrete math exercises

1. Represente en lógica de predicados.

    1. Un estudiante de tu escuela ha vivido en Palmira.

    2. Todos los estudiantes de tu facultad saben programar en Java, Juan sabe programar en Java. Por lo tanto, Juan es un estudiante de tu facultad.

    3. A todos los estudiantes les gusta la comida italiana. A los estudiantes de tu facultad les gusta la comida china. Por lo tanto, a algunos estudiantes les gusta la comida italiana y la china.

2. Formalice en lógica de predicados y determine si la conclusión es válida usando deducción natural.

    1. Algunas personas comen frutas y verduras, todos los que comen frutas se alimentan bien. Pedro come verduras y frutas. Por lo tanto, Pedro se alimenta bien.

    2. Todo ejecutivo que sea poeta es un hombre imaginativo. Todo hombre imaginativo es amante del riesgo. Si todo amante del riesgo no es poeta, entonces, ningún poeta es amante del riesgo. Por consiguiente, si todo hombre imaginativo no es poeta, entonces, ningún ejecutivo es poeta.

    3. Ningún chico rubio quiere cantar. No hay ningún chico alto que no quiere cantar. Todos mis profesores son rubios. Por lo tanto, todos los profesores míos no son altos.

    4. Si Dios fuera capaz de evitar el mal y quisiera hacerlo, lo haría. Si Dios fuera incapaz de evitar el mal, no sería omnipotente; si no quisiera evitar el mal sería malévolo. Dios no evita el mal. Si Dios existe, es omnipotente y no es malévolo. Luego, Dios no existe.

        - Argumentos a variables preposicionales.

            - $C$: Dios es capaz de evitar el mal.

            - $Q$: Dios quiere evitar el mal.

            - $O$: Dios es omnipotente.

            - $M$: Dios es malévolo.

            - $P$: Dios evita el mal.

            - $E$: Dios existe.

        - Razonamiento.

            - $p_1$.

                $$
                \begin{array}{lr}
                    &(C \land Q) \implies P     & \\[10 pts]
                    &\lnot (C \land Q) \lor P    &\text{Definicion condicional} \\[10 pts]
                    &\lnot C \lor \lnot Q \lor P &\text{Ley de Morgan}
                \end{array}
                $$

            - $p_2$.

                $$
                \begin{array}{lr}
                    &(\lnot Q \implies \lnot O) \land (\lnot Q \implies M) & \\[10 pts]
                    &(Q \lor \lnot O) \land (Q \lor M)                               &\text{Definicion condicional}\\[10 pts]
                \end{array}
                $$

            - $p_3$: $\lnot P$.

            - $p_4$.

                $$
                    \begin{array}{lr}
                        &E \implies (O \land \lnot M)                      & \\[10 pts]
                        &\lnot E \lor (O \land \lnot M)                     &\text{Definicion condicional}\\[10 pts]
                        &(\lnot E \lor O) \land (\lnot E \lor \lnot M) &\text{Ley distributiva}
                    \end{array}
                $$

            $$
            (p_1 \land p_2 \land p_3 \land p_4) \implies \lnot E \quad \lnot[(p_1 \land p_2 \land p_3 \land p_4) \implies \lnot E] \\[10 pts]

            (p_1 \land p_2 \land p_3 \land p_4) \land E \quad S = \{p_1,p_2,p_3,p_4,E\} \\[10 pts]
            $$

            > Dividi el $p_2$ y $p_4$ en dos premisas.

            1. $\lnot C \lor \lnot Q \lor P$.

            2. $Q \lor \lnot O$.

            3. $Q \lor M$.

            4. $\lnot P$.

            5. $\lnot E \lor O$.

            6. $\lnot E \lor \lnot M$

            7. $E$.

            8. $O$: resolvente $(5,7)$.

            9. $M$: resolvente $(6,7)$.

            10. $\lnot O \lor M$: resolvente $(2,3)$.

            11. $O$: resolvente $(9,10)$.

            12. $\blacksquare$: resolvente $(8,11)$.

            Es **insatisfactible**, por lo tanto la fórmula original es **válida**.

3. Indique el valor de verdad de la expresión.

    1. $\exist x \; \exist y \quad (x + y = 6 \land x - y = 5)$.

    2. $\forall x \; \exist y \quad (x^2 < y)$.

    3. $\exist x \; \forall y \quad (x + y = 0)$.

4. Simboliza la siguiente expresión en lógica de predicados.

    Los números con el mismo sucesor son idénticos.

    > Simbolice usando $S(x,y):$ $x$ es el sucesor de $y$.
