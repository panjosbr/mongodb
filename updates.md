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