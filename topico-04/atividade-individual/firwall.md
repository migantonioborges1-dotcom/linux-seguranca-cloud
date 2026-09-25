# Configuração do Firewall UFW

## 1. Objetivo

O objetivo desta atividade foi aplicar uma medida inicial de segurança ao servidor através da configuração do UFW (Uncomplicated Firewall).

## 2. Estado inicial

Inicialmente foi verificado o estado do UFW através do comando:

```bash
sudo ufw status verbose
```

O firewall encontrava-se inicialmente desativado.

**Evidência:** `03-ufw-status-inicial.png`

## 3. Regras aplicadas

Antes da ativação do firewall foram autorizadas as portas necessárias:

```bash
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
```

A porta 22/TCP foi autorizada para garantir a continuidade do acesso SSH.

A porta 80/TCP foi autorizada para permitir o funcionamento do serviço web Nginx.

A porta 443/TCP não foi autorizada porque o serviço HTTPS não se encontra configurado nesta implementação.

## 4. Ativação

O firewall foi ativado através de:

```bash
sudo ufw enable
```

## 5. Validação

Após a ativação, as regras foram verificadas através de:

```bash
sudo ufw status verbose
```

**Evidência:** `05-ufw-status-final.png`

## 6. Resultado

O firewall encontra-se ativo e permite apenas os serviços necessários identificados nesta atividade:

* SSH — 22/TCP;
* HTTP — 80/TCP.

Esta configuração reduz a exposição do servidor e constitui uma primeira medida de proteção da infraestrutura.

