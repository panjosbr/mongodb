# Criar um coleção

db.createCollection("alunos")

# Inserir dados em uma coleção

- COM aspas duplas
```javascript
db.alunos.insert(
    {
        "nome" : "Fulano",
        "data_nascimento" : new Date(1990, 10, 31),
        "curso" : {
            "nome" : "Ciência da Computação"
        },
        "notas" : [10.0, 9.0, 4.5],
        "habilidades" : [
            {
                "nome" : "inglês",
                "nível" : "intermediario"
            },
            {
                "nome" : "xadrez",
                "nível" : "avançado"
            }
        ]
    }
)
```

- SEM aspas duplas
```javascript
db.alunos.insert(
    {
        nome : "Fulana",
        data_nascimento : new Date(1990,10, 31),
        curso : {
            nome : "Biomedicina"
        },
        notas : [10.0, 9.0, 4.5],
        habilidades : [
            {
                nome : "inglês",
                nível : "iniciante"
            },
            {
                nome : "xadrez",
                nível : "iniciante"
            }
        ]
    }
)
```

## buscar alunos

```javascript
db.alunos.find()
```
- retorno
```javascript
{ "_id" : ObjectId("5e76bb81ae0c3948dcd9d879"), "nome" : "Fulano", "data_nascimento" : ISODate("1990-12-01T03:00:00Z"), "curso" : { "nome" : "Ciência da Computação" }, "notas" : [ 10, 9, 4.5 ], "habilidades" : [ { "nome" : "inglês", "nível" : "intermediario" }, { "nome" : "xadrez", "nível" : "avançado" } ] }

```

## remover alunos

```javascript
db.alunos.remove({
    "_id" : ObjectId("5e76bb81ae0c3948dcd9d879")
})
```
