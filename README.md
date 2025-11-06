# ALED (Algorithms and Data Structures) Lab Session 3 - Solution

This repository contains the code for a Java application that performs a linear and a binary search to find a DNA sequence inside a reference genome. This code is the solution for this lab session: https://github.com/rgarciacarmona/ALED-lab3

## Respuestas a las preguntas

### Sección 1.6

- **¿Qué hacer el método `search()` de la clase `FASTAReader`? ¿Qué devuelve?:** Encuentra todas las veces que aparece el patrón que se le pasa como parámetro dentro de `content`. Devuelve una lista con la primera posición de todas las coincidencias.
- **¿Qué argumentos tendrá el método `main()`? ¿Qué función tiene cada uno?:** Dos. El primero es el nombre del fichero que contiene el genoma en el que se busca el patrón, y el segundo es el patrón a buscar.
- **Abra la carpeta `cromosomes` y observe los archivos que tiene dentro. ¿En qué formato están? ¿Qué información contienen?:** Están en formato FASTA, y contienen varios genomas.

### Sección 2.1

- **Según la notación O, ¿cuál es orden de complejidad del algoritmo de búsqueda que ha implementado?:** $O(n \cdot m)$, siendo `n` el tamaño del genoma (`content`) y `m` el tamaño del patrón (`pattern`).
- **Compare los tiempos obtenidos al buscar en un archivo de 600 KB con los obtenidos al buscar en un archivo de 60 MB. ¿Son consistentes con el orden del algoritmo?:** Sí, el tiempo crece conforme crece `n` (dos órdenes de magnitud, unas 100-300 veces, teniendo en cuenta ineficiencias), ya que en este caso `m` (el tamaño del patrón a buscar) no varía entre ambos archivos.

### Sección 2.2

- **Según la notación O, ¿ha cambiado el orden de complejidad del algoritmo tras este cambio?:** No, no ha cambiado, pues se considera el caso peor, en el que se tendrán que comparar siempre todas las letras del patrón.
- **Compare los tiempos obtenidos al buscar en un archivo de 600 KB con los obtenidos al buscar en un archivo de 60 MB. ¿Son consistentes con el orden del algoritmo? ¿Ha mejorado el caso peor de la búsqueda, o únicamente el caso medio?:** El tiempo sigue creciendo conforme crece `n`. No obstante, a pesar de que el orden de magnitud del cambio debe ser similar, ahora será un tiempo inferior dentro de ese rango. El caso peor no ha mejorado, pues en esta circunstancia el bucle `for` que itera sobre `m` da exactamente las mismas vueltas. Solo ha mejorado el caso medio.

### Sección 3

- **Según la notación O, ¿ha cambiado el orden de complejidad del algoritmo tras este cambio?:** No, no ha cambiado, pues se sigue iterando en ambos bucles `for` el mismo número de veces.
- **¿Ha cambiado apreciablemente el tiempo de ejecución?:** No, no ha cambiado.

### Sección 4.1

- **Según la notación O, ¿cuél es el orden de complejidad de la búsqueda ahora?:** $O(m \cdot \log{n})$, siendo `n` el tamaño del genoma (`content`) y `m` el tamaño del patrón (`pattern`).
- **¿Ha cambiado apreciablemente el tiempo de ejecución de la búsqueda? ¿A partir de cuántas búsquedas empieza a compensar ordenar?:** (Para este apartado ignoraremos `n`, que es mucho menor que `m`) Sí, considerablemente. La búsqueda es muchísimo más rápida. Como el proceso de ordenación tiene una complejidad de $O(n \cdot \log{n})$ y la búsqueda lineal (sin ordenar) una complejidad de $O(n)$, eso quiere decir que compensará ordenar a partir de $log{n}$ búsquedas. Esto puede determinarse matemáticamente o calcularse experimentalmente, que es lo que probablemente haya hecho usted durante la práctica.

### Sección 4.2

- **Según la notación O, ¿ha cambiado el orden de complejidad de la búsqueda al añadir este código nuevo?:** Técnicamente, sí, la complejidad ahora es $O(m \cdot \log{n} + k \cdot n )$, siendo `n` el tamaño del genoma (`content`), `m` el tamaño del patrón (`pattern`), y `k` el número de veces que aparece el patrón. No obstante, como `k` es un número mucho más pequeño que los otros dos, podría considerarse que la complejidad es $O(m \cdot \log{n})$. Es decir, la misma que antes.
- **¿Ha cambiado apreciablemente el tiempo de ejecución de la búsqueda?:** No, es prácticamente el mismo.
