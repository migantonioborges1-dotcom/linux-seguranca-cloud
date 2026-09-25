# Hardening Inicial do Serviço Web

## 1. Objetivo

Além da configuração do firewall, foram analisadas algumas medidas iniciais de hardening aplicáveis ao servidor Ubuntu e ao serviço Nginx.

## 2. Medidas aplicadas

### 2.1. Firewall

Foi ativado o UFW e foram permitidas apenas as portas necessárias para o funcionamento atual do serviço:

* 22/TCP — SSH;
* 80/TCP — HTTP.

### 2.2. Verificação da configuração do Nginx

Foi executado:

```bash
sudo nginx -t
```

para verificar a validade da configuração do Nginx.

### 2.3. Verificação do estado do serviço

Foi utilizado:

```bash
sudo systemctl status nginx --no-pager
```

para confirmar que o serviço permanece ativo.

### 2.4. Redução da superfície de ataque

Foram analisadas as portas em escuta através de:

```bash
sudo ss -tulpn
```

A política adotada consiste em evitar a exposição de serviços que não sejam necessários.

## 3. Medidas recomendadas para etapas seguintes

Como medidas de hardening adicional, recomenda-se:

* manter o Ubuntu e os pacotes atualizados;
* manter o Nginx atualizado;
* utilizar HTTPS com certificado TLS;
* reforçar a configuração SSH;
* preferir autenticação SSH por chave;
* desativar autenticação SSH por palavra-passe quando possível;
* impedir o login SSH direto do utilizador root;
* rever permissões dos ficheiros publicados;
* evitar a exposição de ficheiros de configuração e credenciais;
* utilizar cabeçalhos HTTP de segurança;
* implementar mecanismos de proteção contra tentativas excessivas de autenticação;
* monitorizar os logs do Nginx e do sistema.

## 4. Medidas deixadas para etapas seguintes

Algumas medidas dependem de configurações que não fazem parte do objetivo principal desta atividade, nomeadamente:

* implementação de HTTPS;
* endurecimento avançado do SSH;
* configuração de políticas adicionais do Nginx;
* monitorização e análise centralizada de logs;
* mecanismos adicionais de deteção e prevenção de intrusões.

## 5. Conclusão

A atividade permitiu aplicar medidas iniciais de hardening através da redução da superfície de ataque, configuração do firewall e validação do serviço Nginx.

