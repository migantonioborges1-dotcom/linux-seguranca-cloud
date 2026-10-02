# Continuidade Operacional

## 1. Objetivo

Este documento apresenta uma abordagem simplificada de continuidade operacional para o serviço web utilizado na atividade.

## 2. Serviço crítico

O Nginx foi considerado o principal serviço crítico por ser responsável pela publicação do conteúdo web.

## 3. Elementos importantes

Os principais elementos a preservar são:

* conteúdo do site;
* configuração do Nginx;
* diretórios necessários à publicação;
* configurações relevantes do serviço;
* backups atualizados.

## 4. Procedimento básico de recuperação

Em caso de perda dos ficheiros do serviço, deve ser seguido um procedimento semelhante ao realizado nesta atividade:

1. Identificar o backup disponível;
2. Verificar a integridade do backup;
3. Criar uma área temporária de recuperação;
4. Restaurar os ficheiros;
5. Verificar os ficheiros recuperados;
6. Validar a configuração do Nginx;
7. Testar o serviço HTTP;
8. Consultar os logs;
9. Confirmar o funcionamento do serviço.

## 5. Periodicidade

Para um ambiente de laboratório, recomenda-se realizar backups periódicos e antes de alterações significativas no servidor.

Em ambiente de produção, a periodicidade deverá ser definida de acordo com a criticidade dos serviços e os requisitos da organização.

## 6. Validação

Após uma recuperação, devem ser realizados testes como:

```bash
sudo nginx -t
sudo systemctl is-active nginx
curl -I http://localhost
```

Também podem ser consultados os logs:

```bash
sudo tail -n 30 /var/log/nginx/access.log
sudo tail -n 30 /var/log/nginx/error.log
```

## 7. Conclusão

A existência de backups testados e de um procedimento documentado de recuperação contribui para reduzir o impacto de uma eventual perda dos ficheiros do serviço web.

