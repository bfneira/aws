# DESAFIO BCI

## EJERCICIO 2

> De un *string* binario (conformado por ceros y unos) y retornar la cantidad de todos los *substrings* que tengan la misma cantidad de ceros y de unos, con la condición de que tanto los ceros como los unos de los *substrings* sean consecutivos

1. **ANÁLISIS**
    - Lo primero es entender lo que se pide. Básicamente es tomar todos los posibles *substrings* dado un *string* de entrada
    - Si consideramos el hecho de que los *substrings* que cumplen la condición debe tener la misma cantidad de ceros que de unos, entonces podemos **descartar** todos los ***substrings* impares**
    - Teniendo ya *substrings* pares dentro de nuestro grupo de "posibles candidatos", ahora debemos evaluar si cumplen la condición de tener la **misma cantidad** de **ceros y unos consecutivos**. Para ello, debemos tomar cada *substring* y evaluar su primer mitad. Si en esa primer mitad sólo tenemos unos, en la segunda mitad sólo debemos tener ceros, y viceversa
2. **EJEMPLO**
    - Supongamos que recibimos el *string* `011001`, acá todos los posibles *substrings* **pares** son:
        - `01`
        - `11`
        - `10`
        - `01`
        - `0110`
        - `1100`
        - `1001`
    - Notar que hay otros *substrings*, pero estos no nos sirven por ser impares y, en consecuencia, nunca tendrán la misma cantidad de ceros que de unos. Lo siguiente es tomar cada *substring* y analizar su primer mitad y su segunda mitad, de manera que si la primer mitad sólo tiene unos, la segunda sólo debe tener ceros. De esta forma evaluamos las dos condiciones: (a) que tengan la misma cantidad de ceros que de unos y (b) que los ceros y unos sean consecutivos. Para cada *substring* que cumpla, tendremos un contador para finalmente tener el total de *substrings* que cumplen lo solicitado
        - `01`. Primer mitad `0` ¿sólo unos/ceros? **Sí, sólo ceros**. Segunda mitad `1` ¿sólo unos? **Sí, sólo unos**. **Contador = 1**
        - `11` Primer mitad `1` ¿sólo unos/ceros? **Sí, sólo unos**. Segunda mitad `1` ¿sólo ceros? **No**
        - `10` Primer mitad `1` ¿sólo unos/ceros? **Sí, sólo unos**. Segunda mitad `0` ¿sólo ceros? **Sí, sólo ceros**. **Contador = 2**
        - `01` Primer mitad `0` ¿sólo unos/ceros? **Sí, sólo ceros**. Segunda mitad `1` ¿sólo unos? **Sí, sólo unos**. **Contador = 3**
        - `0110` Primer mitad `01` ¿sólo unos/ceros? **No**
        - `1100` Primer mitad `11` ¿sólo unos/ceros? **Sí, sólo unos**. Segunda mitad `00` ¿sólo ceros? **Sí, sólo ceros**. **Contador = 4**
        - `1001` Primer mitad `10` ¿sólo unos/ceros? **No**
        - **Contador final = 4**