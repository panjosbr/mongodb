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
