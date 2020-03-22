# Criar um coleção

db.createCollection("alunos")

# Inserir dados em uma coleção

- COM aspas duplas

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

- SEM aspas duplas
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

## buscar alunos

db.alunos.find()

## remover alunos

db.alunos.remove({
    "_id" : ObjectId("5e76bae0ae0c3948dcd9d878")
})
