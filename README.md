# Fipe
> Biblioteca em PHP para consultar a tabela Fipe :moneybag:

API de Consulta Tabela FIPE fornece preços médios de veículos no mercado nacional através de um serviço RESTful HTTP Json. Atualizada mensalmente com dados extraidos da tabela FIPE

A API está online desde 2015 e totalmente gratuíta. O que acha de me pagar um cafe? ☕

[![Make a donation](https://www.paypalobjects.com/pt_BR/BR/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/donate?hosted_button_id=9VA7QHGCAWUL2)

## IMPORTANTE



## API utilizada

A documentação da API utilizada pela biblioteca para obter os dados da Fipe está disponível [neste link](http://wrramerson.github.io/fipe/) e também pode ser encontrada no branch [gh-pages](https://github.com/wrramerson/fipe/tree/gh-pages) deste repositório.

## Classes e métodos
A biblioteca possui 3 classes para consultar a tabela Fipe, uma para cada tipo de veículo, são elas:
* `FipeCaminhoes` consulta a tabela de caminhões
* `FipeCarros` consulta a tabela de carros
* `FipeMotos` consulta a tabela de motos

Cada classe possui os seguintes métodos:
* `getMarcas()` retorna um array com os códigos e nomes das marcas do tipo de veículo escolhido
* `getModelos($codMarca)` retorna um array com o códigos e nomes dos modelos da marca informada
* `getAnos($codMarca, $codModelo)` retorna um array com os códigos e nomes dos anos de um modelo de veículo
* `getVeiculo($codMarca, $codModelo, $codAno)` retorna um array com os dados da tabela Fipe do veículo especificado

## Exemplos de uso
Veja um exemplo de como consultar as marcas de carros:
~~~php
<?php

use DeividFortuna\Fipe\FipeCarros;

$marcas = FipeCarros::getMarcas();

var_dump($marcas);
~~~

O código acima irá retornar um array:
~~~php
[
  [
    "nome": "Acura",
    "codigo": 1
  ], [
    "nome": "Agrale",
    "codigo": 2
  ],
  // etc...
]
~~~

Um exemplo funcional pode ser encontrado na pasta `exemplo` deste projeto.

## Licença
