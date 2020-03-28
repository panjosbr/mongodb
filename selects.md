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

## Consultas com OR

```
db.alunos.find({
    $or : [
        {"curso.nome" : "Jogos digitais"},
        {"curso.nome" : "Ciência da Computação"},
    ],
}).pretty()
```

## Consultas com OR e AND

```
db.alunos.find({
    $or : [
        {"curso.nome" : "Jogos digitais"},
        {"curso.nome" : "Ciência da Computação"},
    ],
    "nome" : "Paulo"
}).pretty()
```

## Consultas com IN

```
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
