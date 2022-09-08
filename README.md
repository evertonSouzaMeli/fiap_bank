## CLIENTE

### GET ALL CLIENTE BY TIPO_CLIENTE

[GET] - http://localhost:8080/cliente/get/FISICO

### GET CLIENTE BY NUMERO CONTA

[GET] - http://localhost:8080/cliente/get?numeroConta=0

### CADASTRAR CLIENTE

[POST] - http://localhost:8080/cliente/cadastrar
```
{
    "nome": "Nome",
    "documento": "000.000.000-00",
    "tipoCliente": "FISICO"
}
```

## CONTA

### CADASTRAR CONTA

[POST] - http://localhost:8080/conta/create
```
{
    "tipoConta": "POUPANCA",
    "cliente": {
        "numero": 0
    }
}
```
### DEPOSITAR

[POST] - http://localhost:8080/conta/depositar
```
{
    "numeroConta": 0,
    "senha": 0,
    "valor": 0.0
}
```

### SACAR

[POST] - http://localhost:8080/conta/sacar
```
{
    "numeroConta": 0,
    "senha": 0,
    "valor": 0.0
}
```
### SALDO

[POST] - http://localhost:8080/conta/saldo
```
{
    "numeroConta": 0,
    "senha": 0,
    "valor": 0.0
}
```
