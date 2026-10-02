# Monitorização do Sistema

## 1. Objetivo

Este documento apresenta os procedimentos utilizados para monitorizar o estado do Ubuntu Server e verificar os principais recursos do sistema.

A monitorização teve como objetivo confirmar o funcionamento do servidor e identificar informações relevantes sobre o sistema, memória, armazenamento e serviço Nginx.

## 2. Identificação do sistema

Foram utilizados os seguintes comandos:

```bash
hostname
hostname -I
lsb_release -a
uname -a
```

Estes comandos permitem identificar o nome do servidor, os endereços IP, a versão do sistema operativo e a versão do kernel.

## 3. Tempo de atividade

O tempo de funcionamento do servidor foi verificado através de:

```bash
uptime
uptime -p
who -b
```

A informação permite verificar há quanto tempo o sistema está em funcionamento e quando ocorreu o último arranque.

**Evidência:** `evidencias/02-uptime.png`

## 4. Utilização da memória

A utilização da memória RAM foi verificada através de:

```bash
free -h
```

Foram observados os valores de memória total, utilizada, disponível e swap.

**Evidência:** `evidencias/03-memoria.png`

## 5. Espaço em disco

O espaço disponível foi verificado com:

```bash
df -h
df -h /
```

Esta verificação permite identificar a capacidade, utilização e espaço disponível nos sistemas de ficheiros.

**Evidência:** `evidencias/04-disco.png`

## 6. Verificação do Nginx

O estado do serviço web foi verificado através de:

```bash
sudo systemctl status nginx
systemctl is-active nginx
systemctl is-enabled nginx
```

Estas verificações permitem confirmar se o Nginx está ativo e configurado para iniciar automaticamente.

**Evidência:** `evidencias/05-nginx-status.png`

## 7. Portas de rede

As portas em utilização foram verificadas com:

```bash
sudo ss -lntp
sudo ss -lntp | grep nginx
```

A verificação permitiu identificar as portas utilizadas pelo Nginx.

**Evidência:** `evidencias/06-portas-nginx.png`

## 8. Teste HTTP

A disponibilidade do serviço foi confirmada através de:

```bash
curl -I http://localhost
```

Quando aplicável, também pode ser testada a segunda instância:

```bash
curl -I http://localhost:8080
```

**Evidência:** `evidencias/07-http.png`

## 9. Conclusão

Os procedimentos realizados permitiram obter uma visão geral do estado do servidor, dos seus principais recursos e do funcionamento do serviço Nginx.

