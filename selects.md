## Formata em json a busca
```
db.alunos.find().pretty()
```

## Filtrar com uma condição

```
db.alunos.find(
    {
        "nome" : "Panjos"
    }
).pretty()
```

## Filtrar com duas condições (semelhante ao join em sql)

```
db.alunos.find(
    {
        "nome" : "Panjos",
        "habilidades.nome" : "ingles"
    }
).pretty()
```
