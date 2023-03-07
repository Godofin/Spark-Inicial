# Spark-Inicial

## Comandos Iniciais do PySpark

### Importando CSV

```
df = spark.read.csv('diretório')
```

### Visualizando dados

```
df.limit(X).show()
```

### Visualizando dados como DataFrame

```
df.limit(X).toPandas()
```

## PySpark SQL

### Comando Select

```
df.select('*').show(5, False)
```

### Comando Alias

```
df.select('*').alias("Name").show(5, False)
```

### Comando OrderBy

```
df\
  .select('c1', 'c2')\
  .orderBy('c1', ascending=False)\
  .show(5, False)
```

### Comandos de Filtros

- Usando Where
```
df\
  .where("c1==50")\
  .show(5)
```

- Usando Filter
```
df\
  .select("c1")\
  .filter(c1.startswith("****"))\
  .filter(c1.endswith("***"))\
  .limit(10)\
  .toPandas()
```

### Comando Like

```
df\
  .where(f.upper(df.data).like('%RESTAURANTE'))\
  .show(truncate=False)
```
### Joins em PySpark

- Inner Join

```
tab1.join(tab1, 'colunaIntersecção', how='inner')\
    .sort('id')\ ##Denominador
    .show()
```


- Left Join

```
tab1.join(tab1, 'colunaIntersecção', how='left')\
    .sort('id')\ ##Denominador
    .show()
```

- Right Join

```
tab1.join(tab1, 'colunaIntersecção', how='right')\
    .sort('id')\ ##Denominador
    .show()
```

- Full Join

```
tab1.join(tab1, 'colunaIntersecção', how='full')\
    .sort('id')\ ##Denominador
    .show()
```


## Realizando Querys com SQL

- Para realizar querys no padrão de escrita SQL, basta usar o comando abaixo, e acrescentar sua query entre os parênteses.
```
spark.sql('QUERY')
```

