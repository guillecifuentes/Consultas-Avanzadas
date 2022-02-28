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

# Test 1

Se trata de la tabla line que almacena el turno de un grupo de personas para subirse al ascensor, la capacidad de este es de max 1000 libras de peso, la tarea de es crear una  consulta que muestre el nombre de la ultima persona en subirse en el primer viaje

El script de creacion de la tabla es:

<img width="265" alt="ascensorTabla" src="https://user-images.githubusercontent.com/17502722/155904473-95a14ab3-fff0-4a9a-863e-1a63c51b5ac4.png">

la tabla es:

<img width="313" alt="ascensorTabla1" src="https://user-images.githubusercontent.com/17502722/155904561-4014ed38-e23c-4acc-ac18-6bd7f5307ca6.png">

El resultado del Query debe arrojar "Thomas Jefferson"

## Manos a la obra

<img width="211" alt="ascensorTabla2" src="https://user-images.githubusercontent.com/17502722/155905044-f3269916-fd47-424c-bee3-b72870e47ac4.png">

<img width="73" alt="ascensorTabla3" src="https://user-images.githubusercontent.com/17502722/155905086-4c4a4147-5e55-4894-8591-f61535956fcd.png">

# Test 2
## Contar los tickets por obra en orden descendente

La primera tabla representa las obras, la segunda las reservaciones y la tercera el Query a realizar

<img width="900" alt="test2Tablas" src="https://user-images.githubusercontent.com/17502722/155905567-02400e76-9fd3-458a-a5f3-a7e71e8aca6b.png">

La consulta solicitada es:

<img width="293" alt="test2Query" src="https://user-images.githubusercontent.com/17502722/155905607-856a5437-c49e-451b-bb19-dcffbe1871e2.png">

El Resultado de esa consulta es:
<img width="324" alt="test2Resultado" src="https://user-images.githubusercontent.com/17502722/155905865-cf33e758-f676-4f00-85a4-dd7f4b2ff519.png">

Observe que el ultimo valor muestra null deberia mostrar 0

La nueva consulta seria:

<img width="286" alt="test2QueryOptimizada" src="https://user-images.githubusercontent.com/17502722/155905925-9948d20a-1f3c-47c8-8916-d1ae487a1db6.png">

Su resultado es:

<img width="238" alt="test2Resultado2" src="https://user-images.githubusercontent.com/17502722/155905937-f98f16ca-91aa-4c40-8bf1-a2e0341542f4.png">




