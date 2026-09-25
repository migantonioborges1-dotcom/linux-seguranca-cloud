# Tópico 04 — Atividade Prática Individual

## Segurança Inicial de Serviço Web

### 1. Identificação

**Atividade:** Sessão 4 — Atividade prática individual
**Nível:** Nível 2 — Intermédio
**Serviço analisado:** Nginx
**Sistema operativo:** Ubuntu Server

---

## 2. Objetivo

Esta atividade teve como objetivo aplicar medidas iniciais de segurança ao serviço web publicado no Tópico 3.

Foram realizadas as seguintes tarefas:

* identificação de serviços e portas;
* análise inicial da superfície de ataque;
* configuração do firewall UFW;
* definição das portas necessárias;
* validação das regras aplicadas;
* validação do funcionamento do Nginx após as alterações;
* documentação de medidas iniciais de hardening.

---

## 3. Estrutura

```text
atividade-individual/
├── evidencias/
├── comandos.txt
├── superficie-ataque.md
├── firewall.md
├── hardening.md
├── validacao.md
└── README.md
```

---

## 4. Portas autorizadas

| Porta  | Serviço | Finalidade                |
| ------ | ------- | ------------------------- |
| 22/TCP | SSH     | Administração do servidor |
| 80/TCP | HTTP    | Serviço web Nginx         |

A porta 443/TCP não foi autorizada porque o serviço HTTPS ainda não se encontra configurado.
Também utilizei a porta 8080 para o segundo servidor já que usei a porta 80  para o site do grupo.
---

## 5. Firewall

Foi configurado o UFW com as regras necessárias para manter o acesso administrativo e o funcionamento do serviço web.

O firewall foi ativado e posteriormente validado.

---

## 6. Validação

Após a ativação do firewall foram realizados testes para confirmar:

* estado do Nginx;
* validade da configuração;
* funcionamento do serviço HTTP;
* acesso através de localhost;
* acesso através do endereço IP da VM.

---

## 7. Evidências

As principais evidências encontram-se na pasta `evidencias/`.

| Evidência                 | Descrição                       |
| ------------------------- | ------------------------------- |
| 01-nginx-status.png       | Estado do serviço Nginx         |
| 02-portas.png             | Portas e serviços identificados |
| 03-ufw-status-inicial.png | Estado inicial do UFW           |
| 04-ufw-regras.png         | Regras configuradas             |
| 05-ufw-status-final.png   | Estado final do firewall        |
| 06-site-localhost.png     | Serviço acessível localmente    |
| 07-site-ip.png            | Serviço acessível pelo IP       |

---

## 8. Conclusão

A atividade permitiu aplicar medidas iniciais de segurança ao serviço web, nomeadamente através da identificação da superfície de ataque e configuração do firewall UFW.

Após as alterações, o serviço Nginx continuou operacional e acessível, demonstrando que as medidas de segurança foram aplicadas sem comprometer o funcionamento do serviço.

