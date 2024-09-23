# Concurrency vs parallelism

## Paralelismo

Se refiere a la **ejecución simultánea** de varios procesos computacionales. Esto significa que se requieren varios medios de ejecución física: varios procesadores (o un procesador con varios núcleos) o varias computadoras (sistemas distribuidos) y la suficiente memoria para mantenerlos.

> Los procesos pueden estar relacionados entre ellos, para realizar una misma tarea, o no.

## Concurrencia

La composición de elementos (funciones, procesos, programas, etc.) que se ejecutan independientemente, pero **interactúan entre sí**.

> No necesariamente se ejecutan al mismo tiempo.

---

Los lenguajes tienen diferentes maneras de permitirte aprovechar los recursos de cómputo para crear programas concurrentes y paralelos:

- Hilos: subprocesos que se coordinan entre sí, que ocupan menos memoria que un proceso normal y comparten memoria con otros hilos y con el proceso padre.

- Procesos: programas que corren en su propio espacio de memoria independientemente de otros procesos. Lo que hace un proceso no le afecta a otro, por lo que hay que diseñar y mantener maneras de comunicarlos.

---

**La concurrencia tiene que ver con el diseño del software, mientras que el paralelismo tiene que ver con la ejecución**.
