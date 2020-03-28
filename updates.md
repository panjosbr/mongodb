## Update

- primeiro parâmetro: condição
- segundo parâmetro: é novo objeto (substitui o anterior)

*** Atualiza apenas o primeiro registro encontrado na busca

```javascript
db.alunos.update(
    {
        "curso.nome" : "Ciência da computação"
    },
    {
        "nome" : "Ciências da computação"
    }
)
```

## Update especificando uma propriedade

```javascript
db.alunos.update(
    {"curso.nome" : "Ciências da Computação"},
    {
        $set : {
            "curso.nome" : "Ciencia da Computacao"
        }
    }
)
```

## UpdateAll - atualiza todos registros encontrados na busca

```javascript
db.alunos.update(
    {"curso.nome" : "Ciência da Computação"},
    {
        $set : {
            "curso.nome" : "Ciencia Da Computacao"
        }
    },
    {
        "multi" : true
    }
)
```

## Update by ID - adicionando um novo valor em um array

```javascript
db.alunos.update(
    {"_id" : ObjectId("5e76bb81ae0c3948dcd9d879")},
    {
        $push : {
            "notas" : 8.5
        }
    }
)
```

## Update by ID - adicionando mais de um valor em um array

```javascript
db.alunos.update(
    {"_id" : ObjectId("5e76bb81ae0c3948dcd9d879")},
    {
        $push : {
            "notas" : {
                $each : [8.5, 3]
            }
        }
    }
)
```
