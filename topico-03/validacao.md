# Validação

## URLs testados

- http://localhost/topico-03/
- http://localhost/topico-03/sobre.html
- http://localhost/topico-03/style.css

## Forma de validação

A validação foi realizada através do navegador e do comando curl.

## Testes realizados

Foi testada a página inicial, a página Sobre, o carregamento
do ficheiro CSS e as ligações entre as páginas.

Também foi utilizado o comando:

curl -I http://localhost/topico-03/

O servidor respondeu com o estado HTTP 200 OK.

## Resultado dos testes

Os testes foram concluídos com sucesso.

A página inicial foi apresentada corretamente.
A página Sobre foi apresentada corretamente.
O ficheiro CSS foi carregado.
As ligações entre as páginas funcionaram.

## Evidências

As evidências encontram-se na pasta:

evidencias/

Incluem prints da estrutura criada, do estado do Nginx,
das páginas publicadas e dos testes realizados com curl.

## Observações

O serviço ficou acessível através do endereço localhost.
Quando disponível na rede local, também pode ser testado através
do endereço IP da máquina Linux.
