# Análise de Logs

## 1. Objetivo

Este documento apresenta os procedimentos utilizados para consultar e analisar os registos do Ubuntu Server e do Nginx.

A análise dos logs permite acompanhar eventos do sistema e pedidos recebidos pelo serviço web.

## 2. Logs do sistema

Foram consultados os eventos recentes através de:

```bash
sudo journalctl -n 30 --no-pager
```

Também foram consultados os eventos registados durante o dia:

```bash
sudo journalctl --since today --no-pager
```

**Evidência:** `evidencias/08-logs-sistema.png`

## 3. Access log do Nginx

O registo de acessos foi consultado através de:

```bash
sudo tail -n 30 /var/log/nginx/access.log
```

O `access.log` permite observar os pedidos recebidos pelo servidor, os recursos solicitados e os códigos de resposta HTTP.

**Evidência:** `evidencias/09-nginx-access.png`

## 4. Error log do Nginx

O registo de erros foi consultado através de:

```bash
sudo tail -n 30 /var/log/nginx/error.log
```

Este ficheiro permite identificar mensagens relacionadas com erros ou ocorrências que necessitem de análise.

**Evidência:** `evidencias/10-nginx-error.png`

## 5. Identificação de eventos HTTP

Para identificar códigos HTTP relevantes foi utilizado:

```bash
sudo grep -E '" (200|301|302|400|403|404|500) ' \
/var/log/nginx/access.log | tail -n 20
```

A análise deve considerar o contexto do evento, evitando assumir que qualquer código diferente de 200 representa necessariamente uma falha de segurança.

## 6. Conclusão

A consulta dos logs permitiu verificar o funcionamento do sistema e do Nginx, bem como observar os pedidos HTTP processados pelo serviço.

