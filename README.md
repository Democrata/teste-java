# Teste Prático Java

Construir uma API Rest middleware para busca de CEP utilizando SPRING.

API aberta: Utilizar a API aberta [Via Cep](https://viacep.com.br/)

## Especificações
 - Desenvolver rotina que periodicamente busque na API aberta CEP’s aleatórios. (A cada minuto, buscar 5 CEP’s aleatórios);
 - Alterar as execuções de consultas nos tipos de retorno (XML, PIPED e JSON); 
 - Os retornos devem ser persistidos em banco de dados (preferencialmente Oracle). Guardar a data e hora que a consulta foi realizada;
 - Caso o CEP montado aleatoriamente já esteja persistido no banco de dados, deverá ser gerado uma nova combinação.
 - Criar endPoint para busca do CEP (apenas os dígitos) que deverá verificar se o CEP já está cadastrado no banco e, caso não esteja ou o tempo cadastrado seja superior a 5 minutos, deverá buscar na API aberta, persistir os dados no banco, e retornar a RESPONSE com os dados.
 - Criar endPoint para busca de todos os CEP’s, agrupando por estado (UF);
 - Criar endPoint para busca por estado (UF), agrupando por cidade;
 - Criar endpoint para busca por cidade;
 - A Response padrão da API deve ser em JSON;
 - O projeto deverá ter um readme explicando a estrutura, configuração necessária e como testar;
 - A entrega deverá ser feita via repositório compartilhado (github, gitlab, etc), via ZIP por e-mail ou link para download.

Abaixo estão exemplos de consulta na API aberta:
### XML
URL: [https://viacep.com.br/ws/01001000/xml/](https://viacep.com.br/ws/01001000/xml/)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<xmlcep>
    <cep>01001-000</cep>
    <logradouro>Praça da Sé</logradouro>
    <complemento>lado ímpar</complemento>
    <bairro>Sé</bairro>
    <localidade>São Paulo</localidade>
    <uf>SP</uf>
    <unidade></unidade>
    <ibge>3550308</ibge>
    <gia>1004</gia>
</xmlcep>
```
### PIPED
URL: [https://viacep.com.br/ws/01001000/piped/](https://viacep.com.br/ws/01001000/piped/)
```
cep:01001-000|logradouro:Praça da Sé|complemento:lado ímpar|bairro:Sé|
localidade:São Paulo|uf:SP|unidade:|ibge:3550308|gia:1004
```
### JSON
URL: [https://viacep.com.br/ws/01001000/json/](https://viacep.com.br/ws/01001000/json/)
```json
{
  "cep": "01001-000",
  "logradouro": "Praça da Sé",
  "complemento": "lado ímpar",
  "bairro": "Sé",
  "localidade": "São Paulo",
  "uf": "SP",
  "unidade": "",
  "ibge": "3550308",
  "gia": "1004"
}
```
