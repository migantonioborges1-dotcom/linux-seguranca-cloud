# Publicação do serviço web

## Nível escolhido

Nível 2 - Intermédio

## Rota escolhida

Nginx

## Ficheiros criados

- index.html
- sobre.html
- style.css

## Local de publicação

/var/www/html/topico-03/

## Servidor web

Nginx

## Processo de publicação

Foi criada uma estrutura de ficheiros HTML e CSS para o serviço web.
Posteriormente, foi criada a pasta de publicação no servidor Nginx e
os ficheiros foram copiados para:

/var/www/html/topico-03/

## Comandos principais utilizados

- nginx -v
- sudo systemctl status nginx
- sudo mkdir -p /var/www/html/topico-03
- sudo cp site/* /var/www/html/topico-03/

## Resultado obtido

O serviço web foi publicado com sucesso através do Nginx.
A página inicial, a página Sobre e o ficheiro CSS ficaram acessíveis.

## Limitações encontradas

A atividade foi realizada num ambiente Linux de laboratório. A
configuração foi mantida simples, uma vez que os temas de segurança,
hardening, firewall, logs, monitorização e cópias de segurança serão
aprofundados nos tópicos seguintes.
