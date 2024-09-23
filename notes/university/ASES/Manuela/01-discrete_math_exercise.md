# Discrete math exercise

Determine usando inferencia si la conclusión de la siguiente fórmula proposicional es válida:

> Restricción: para este ejercicio **no** puede hacer uso de las reglas de adición, ni silogismo disyuntivo y **solo** puede usar una vez la regla de resolución.

$$
[(p \rightarrow q) \land (p \rightarrow (q \rightarrow r)) \land (q \rightarrow (r \rightarrow s))] \rightarrow (p \rightarrow s)
$$

## Negación de la fórmula

Queremos demostrar la validez por contradicción. Negamos la fórmula original.

$$
\neg \left( [(p \rightarrow q) \land (p \rightarrow (q \rightarrow r)) \land (q \rightarrow (r \rightarrow s))] \rightarrow (p \rightarrow s) \right)
$$

Aplicamos la negación al condicional.

$$
[(p \rightarrow q) \land (p \rightarrow (q \rightarrow r)) \land (q \rightarrow (r \rightarrow s))] \land \neg(p \rightarrow s)
$$

## Simplificación de la negación del condicional

$$
\neg(p \rightarrow s) \equiv p \land \neg s
$$

La fórmula resultante es

$$ [(p \rightarrow q) \land (p \rightarrow (q \rightarrow r)) \land (q \rightarrow (r \rightarrow s))] \land p \land \neg s
$$

## Descomponiendo los condicionales:

Usamos las equivalencias para los condicionales:

- $p \rightarrow q \equiv \neg p \lor q$.

- $p \rightarrow (q \rightarrow r) \equiv \neg p \lor (\neg q \lor r) \equiv \neg p \lor \neg q \lor r$.

- $q \rightarrow (r \rightarrow s) \equiv \neg q \lor (\neg r \lor s) \equiv \neg q \lor \neg r \lor s$.

La fórmula se transforma en

$$
(\neg p \lor q) \land (\neg p \lor \neg q \lor r) \land (\neg q \lor \neg r \lor s) \land p \land \neg s
$$

## Listar las cláusulas y aplicar resolución

Las cláusulas obtenidas son:

1. $\neg p \lor q$.

2. $\neg p \lor \neg q \lor r$.

3. $\neg q \lor \neg r \lor s$.

4. $p$.

5. $\neg s$.

6. $\neg q \lor \neg r$: resolvente $(3,5)$.

7. $\neg p \lor \neg q$: resolvente $(2,6)$.

8. $\neg q$: resolvente $(4,7)$.

9. $\neg p$: resolvente $(1,8)$.

10. $\blacksquare$: resolvente $(4,9)$.

Es **insatisfactible**, por lo tanto la fórmula original es **válida**.

---

1. $\neg p \lor q$.

2. $\neg p \lor \neg q \lor r$.

3. $\neg q \lor \neg r \lor s$.

4. $p$.

5. $\neg s$.

6. $\neg q \lor \neg r$: resolvente $(3,5)$.

La contradicción surge del hecho de que, por un lado, estamos forzados a aceptar que $q$ y $r$ son verdaderos (debido a las cláusulas 1, 2 y 4), pero, por otro lado, la cláusula obtenida por resolución ($\neg q \lor \neg r$) nos obliga a aceptar que al menos uno de ellos debe ser falso.
