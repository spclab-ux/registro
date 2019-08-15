# Desafio Registro SPC

**Importante**
Não realizar Fork desse repositório. Crie um repositório próprio. 

Sua missão é atender um grupo de lojistas que desejam realizar a manutenção
do cadastro de clientes inadimplentes. O layout, screenflow e assets (ícones e imagens) estão disponíveis aqui:

**Wireframe**
https://sketch.cloud/s/KWway/a/d73xRn/play

**Assets e layouts**
https://sketch.cloud/s/KWway

O acesso ao sistema começa na tela de login. Os campos utilizados serão Usuário
e Senha: spcteste01@spcbrasil.org.br e 123456 . A tela de login deverá validar
casos de usuário e senha inválidos (quaisquer valores diferentes desses). (não é necessário usar API)

Esse cadastro deve comportar as operações de consulta, inclusão, exclusão,
e atualização de registros seguindo as seguintes regras abaixo:

Os registros são compostos pelos seguintes campos:

**CPF:** Campo numérico(dígitos de 0 a 9), deve conter 11 dígitos.
Ex: 234.567.432-85. O campo poderá ser enviado à API como string(23456743285),
porém, deverá ser exibido com máscara(pontos e separadores).

**Nome:** Campo texto(String). Não é necessário separar nome e sobrenome.
Exemplo: João da Silva .

Valor da Dívida: Campo numérico, com duas casas decimais. 
**Exemplo:** 3450,00

**Contrato:** Campo numérico (dígitos de 0 a 9), deve conter 5 dígitos.
Exemplos: 00003, 12360

**Data de inclusão:** Data válida que indica a data da dívida, formatada em dd/mm/yy.

**Consultas:** Deverão ser feitas através de CPF. O campo CPF deverá conter máscara,
e permitir apenas a entrada de dígitos (0 a 9, sem separadores).

**Inclusões:** Todos os campos deverão ser preenchidos com seus respectivos valores.
A interface deverá prevenir erros (ex. campos em branco, entrada de caracteres
não condizentes com o tipo do campo, etc.)

**Exclusão:** A exclusão será feita através do botão de excluir("lata de lixo"), e
deverá alertar o usuário para confirmação(Deseja excluir o registro?)

**Atualização:** Ao clicar no ícone atualizar (linha), os dados deverão ser exibidos
numa tela modal similar à tela de inclusão. O único dado que não poderá ser
modificado será CPF.

**Alerts:** O mesmo layout de alert(Alerta) será emitido para operações de escrita e atualização. O texto dos alertas precisa ser criado, e deverá ser exibido conforme a sua respectiva operação(Ex: "Deseja excluir o registro xpto?", "Deseja incluir o usuário "Fulano da Silva"?", "Deseja alterar o registro xpto", etc.).  
 

## Documentação API Rest


## Endpoint
[http://5d52bcb73432e70014e6bc2c.mockapi.io/spc/](http://5d52bcb73432e70014e6bc2c.mockapi.io/spc/)

Tipo Requisição | Endereço | descrição
-----------------|----------|------------------
GET | /registro/ | retorna todos os registros
GET | /registro/{id} | retorna um registro
POST | /registro/ | inclui um novo registro
PUT | /registro/{id} | atualiza um registro
DELETE | /registro/{id} | excluir um registro

## Header
Content-Type: application/json
Accept: application/json

## Json de Exemplo

~~~json
{
    "nome": "João Rock",
    "cpf": "24905123070",
    "valorDivida": 22014.25,
    "dataInclusao": 1565704191,
    "numeroContrato": 71
}
~~~
