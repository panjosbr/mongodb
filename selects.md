*Alguns seletores: https://docs.mongodb.com/manual/reference/operator/query/#query-selectors

## Formata em json a busca
```javascript
db.alunos.find().pretty()
```

## Filtrar com uma condição

```javascript
db.alunos.find(
    {
        "nome" : "Panjos"
    }
).pretty()
```

## Filtrar com duas condições (semelhante ao join em sql)

```javascript
db.alunos.find(
    {
        "nome" : "Panjos",
        "habilidades.nome" : "ingles"
    }
).pretty()
```

## Consultas com OR

```javascript
db.alunos.find({
    $or : [
        {"curso.nome" : "Jogos digitais"},
        {"curso.nome" : "Ciência da Computação"},
    ],
}).pretty()
```

## Consultas com OR e AND

```javascript
db.alunos.find({
    $or : [
        {"curso.nome" : "Jogos digitais"},
        {"curso.nome" : "Ciência da Computação"},
    ],
    "nome" : "Paulo"
}).pretty()
```

## Consultas com IN

```javascript
db.alunos.find({
    "curso.nome": {
        $in: [
            "Ciência da Computação",
            "Jogos digitais",
            "Biomedicina"
        ],
    },
}).pretty()
```

## Consultas > - maior que - greater than

```javascript
db.alunos.find(
    {
        "notas" : { $gt : 5 }
    }
)

## Consultas > - menor que - less than

```javascript
db.alunos.find(
    {
        "notas" : { $lt : 5 }
    }
)
```

## Consultar apenas um

```javascript
db.alunos.findOne({
    "notas" : { $gt : 5 }
})
```

## Consulta com OrderBy

- 1 para crescente
- -1 decrescente

```javascript
db.alunos.find().sort({"nome" : 1})
```

## Consulta com OrderBy com limite

```javascript
db.alunos.find().sort({"nome" : 1}).limit(3)
```
