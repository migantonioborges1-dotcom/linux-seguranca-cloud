# Análise da Superfície de Ataque

## 1. Objetivo

A análise da superfície de ataque teve como objetivo identificar os principais serviços e portas de rede disponíveis no servidor Ubuntu utilizado para publicar o serviço web desenvolvido no Tópico 3.

O serviço web utilizado é o **Nginx**.

## 2. Serviços identificados

Durante a análise foram identificados os principais serviços necessários ao funcionamento e administração do servidor.

| Porta | Protocolo | Serviço    | Finalidade                                                          |
| ----- | --------- | ---------- | ------------------------------------------------------------------- |
| 22    | TCP       | SSH        | Administração remota do servidor                                    |
| 80    | TCP       | HTTP/Nginx | Disponibilização do serviço web                                     |
| 443   | TCP       | HTTPS      | Não utilizado nesta implementação, caso não exista configuração TLS |

## 3. Portas necessárias

A porta 22/TCP é necessária para permitir a administração remota do servidor através de SSH.

A porta 80/TCP é necessária para disponibilizar o serviço web através do Nginx.

A porta 443/TCP apenas deverá ser disponibilizada quando o serviço estiver configurado para utilizar HTTPS.

## 4. Principais riscos identificados

### Risco 1 — Exposição de serviços desnecessários

A existência de serviços ou portas não utilizados aumenta a superfície de ataque do servidor.

### Risco 2 — Exposição do serviço SSH

A porta SSH é necessária para administração, mas representa uma superfície adicional que deve ser protegida através de autenticação adequada, atualização do sistema e, posteriormente, medidas adicionais de hardening.

### Risco 3 — Serviço web exposto

O Nginx está acessível através da rede para disponibilizar o serviço web. A aplicação e a configuração do servidor devem, por isso, ser mantidas atualizadas e corretamente configuradas.

## 5. Medida aplicada

Como medida inicial de segurança foi configurado o firewall UFW, permitindo apenas os serviços necessários à administração e disponibilização do serviço web.

As regras aplicadas permitem SSH e HTTP. HTTPS será permitido apenas quando estiver efetivamente configurado.

## 6. Conclusão

A análise permitiu identificar os principais pontos de exposição do servidor e estabelecer uma política inicial de redução da superfície de ataque através do firewall.

