# Validação Após as Alterações

## 1. Objetivo

Após a configuração do firewall UFW, foram realizados testes para confirmar que o serviço Nginx continuava operacional e acessível.

## 2. Validação do Nginx

Foi executado:

```bash
sudo systemctl is-active nginx
```

Resultado esperado:

```text
active
```

Também foi validada a configuração:

```bash
sudo nginx -t
```

Resultado esperado:

```text
syntax is ok
test is successful
```

## 3. Validação do firewall

Foi executado:

```bash
sudo ufw status verbose
```

O resultado confirmou que o firewall se encontrava ativo e que as portas necessárias estavam autorizadas.

## 4. Teste HTTP local

Foi executado:

```bash
curl -I http://localhost
```

O servidor respondeu com um código HTTP válido, confirmando o funcionamento do serviço web.

## 5. Teste através do endereço IP

Foi executado:

```bash
curl -I http://10.90.27.181
```

O serviço respondeu corretamente através do endereço IP da VM.

Também foi realizado o teste através de um navegador utilizando:

```text
http://10.90.27.181
```

**Evidência:** `07-site-ip.png`

## 6. Resultado

Após a ativação do UFW, o serviço Nginx permaneceu operacional.

A administração através de SSH permaneceu autorizada pela porta 22/TCP e o acesso HTTP permaneceu disponível pela porta 80/TCP.

## 7. Conclusão

Os testes realizados demonstram que a aplicação das regras iniciais de firewall não interrompeu o serviço web publicado no Tópico 3.

