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

