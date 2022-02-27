# Consultas-Avanzadas

En este post trataremos de resolver tres consultas que podrían ser complicas de desarrollar de la forma tradicional, en el archivo de excel estan planteadas las situaciones

## Inicialmente analizaremos el concepto de CTE: Common Table Expression

Tomado de https://dev.mysql.com/doc/refman/8.0/en/with.html

To specify common table expressions, use a WITH clause that has one or more comma-separated subclauses. Each subclause provides a subquery that produces a result set, and associates a name with the subquery. The following example defines CTEs named cte1 and cte2 in the WITH clause, and refers to them in the top-level SELECT that follows the WITH clause:


WITH <br>
  cte1 AS (SELECT a, b FROM table1), <br>
  cte2 AS (SELECT c, d FROM table2) <br>
SELECT b, d FROM cte1 JOIN cte2 <br>
WHERE cte1.a = cte2.c; <br>

## Ejercicio Previo
Antes de empezar vamos a crer una consulta a la tabla sueldos que me traiga el segundo sueldo de cada equipo
A continuación se deja el script de creacion de la tabla

![tablaSueldos](https://user-images.githubusercontent.com/17502722/155868762-d757ed56-e877-450f-b576-8ed96fa6db81.png)

La consulta Select * from salaries, muestra lo siguiente:

![tablaSueldos1](https://user-images.githubusercontent.com/17502722/155868832-730f26fb-3ec7-4ba0-988c-2acb49163dcb.png)

La consulta que muestra el ranking segun el equipo es:

![tablaSueldos5](https://user-images.githubusercontent.com/17502722/155869169-e503e663-f191-4620-8d3f-320c565f4720.png)

El resultado por equipos es:

![tablaSueldos4](https://user-images.githubusercontent.com/17502722/155869146-a7ad646d-83bb-427a-af77-09d762226a08.png)


La consulta que responde a la pregunta es: 

![tablaSueldos2](https://user-images.githubusercontent.com/17502722/155869070-57d53543-a127-48d9-b0a2-501c68550536.png)

y el resultado es:

![tablaSueldos3](https://user-images.githubusercontent.com/17502722/155869090-42445b1f-257d-4f2c-b379-0ae337af8a2a.png)

Otra forma utilizando CTE:

![tablaSueldos6](https://user-images.githubusercontent.com/17502722/155869252-5bc30866-c9b7-4ef3-b540-0c64655b2721.png)

Da el mismo resultado

![tablaSueldos7](https://user-images.githubusercontent.com/17502722/155869284-14da0a6f-327f-4e42-b28f-dcc6cc5d84d6.png)

