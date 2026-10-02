# Manutenção e Validação do Serviço

## 1. Objetivo

Este documento apresenta os procedimentos básicos de manutenção e validação realizados no Ubuntu Server durante a atividade.

## 2. Verificação do serviço

O estado do Nginx foi verificado com:

```bash
sudo systemctl status nginx
systemctl is-active nginx
systemctl is-enabled nginx
```

O objetivo foi confirmar que o serviço se encontrava ativo e configurado para iniciar automaticamente.

## 3. Validação da configuração

A configuração do Nginx pode ser validada através de:

```bash
sudo nginx -t
```

Este procedimento permite verificar se existem erros de sintaxe na configuração antes de efetuar alterações ou recarregar o serviço.

## 4. Verificação das portas

Foram verificadas as portas de escuta:

```bash
sudo ss -lntp | grep nginx
```

## 5. Teste do serviço Web

A resposta HTTP foi validada através de:

```bash
curl -I http://localhost
```

Quando configurado, também pode ser utilizado:

```bash
curl -I http://localhost:8080
```

## 6. Validação após backup e recuperação

Depois do procedimento de recuperação, o serviço foi novamente validado através de:

```bash
sudo systemctl is-active nginx
curl -I http://localhost
```

O objetivo foi confirmar que a operação realizada na área de teste não interferiu no serviço web original.

**Evidência:** `evidencias/15-validacao-pos-backup.png`

## 7. Conclusão

As verificações realizadas permitiram confirmar o estado do Nginx, a validade da configuração e a disponibilidade do serviço HTTP antes e depois do procedimento de backup e recuperação.

