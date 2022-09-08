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

## DDL
```
CREATE TABLE tb_conta
(
    id         BIGINT AUTO_INCREMENT NOT NULL,
    nr_numero  INT                   NOT NULL,
    nr_senha   INT                   NOT NULL,
    nr_saldo   DOUBLE,
    tipo_conta VARCHAR(255),
    cliente_id BIGINT,
    CONSTRAINT pk_tb_conta PRIMARY KEY (id)
);

ALTER TABLE tb_conta
    ADD CONSTRAINT FK_TB_CONTA_ON_CLIENTE FOREIGN KEY (cliente_id) REFERENCES tb_cliente (id);

CREATE TABLE tb_cliente
(
    id           BIGINT AUTO_INCREMENT NOT NULL,
    numero       INT,
    nm_nome      VARCHAR(255),
    nr_documento VARCHAR(255),
    tipo_cliente VARCHAR(255),
    conta_id     BIGINT,
    CONSTRAINT pk_tb_cliente PRIMARY KEY (id)
);

ALTER TABLE tb_cliente
    ADD CONSTRAINT FK_TB_CLIENTE_ON_CONTA FOREIGN KEY (conta_id) REFERENCES tb_conta (id);
```
