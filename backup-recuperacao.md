# Backup e Recuperação

## 1. Objetivo

Este documento apresenta o procedimento utilizado para criar uma cópia de segurança do conteúdo do serviço web e realizar um teste de recuperação.

## 2. Elementos selecionados

Foi selecionado o conteúdo do site desenvolvido no Tópico 3:

```text
~/linux-seguranca-cloud/topico-03/atividade-individual/site/
```

Também foi preservada a configuração do Nginx:

```text
/etc/nginx/sites-available/topico-03
```

## 3. Criação do diretório de backup

Foi criado o diretório:

```bash
mkdir -p ~/backups/topico-05
```

## 4. Backup do site

O conteúdo do site foi compactado através de:

```bash
tar -czvf ~/backups/topico-05/site-backup.tar.gz \
~/linux-seguranca-cloud/topico-03/atividade-individual/site
```

## 5. Backup da configuração do Nginx

A configuração foi copiada através de:

```bash
sudo cp /etc/nginx/sites-available/topico-03 \
~/backups/topico-05/topico-03-nginx.conf
```

## 6. Verificação do backup

Os ficheiros criados foram verificados com:

```bash
ls -lh ~/backups/topico-05/
```

**Evidência:** `evidencias/11-backup-criado.png`

## 7. Verificação do conteúdo

O conteúdo do arquivo comprimido foi verificado com:

```bash
tar -tzf ~/backups/topico-05/site-backup.tar.gz
```

**Evidência:** `evidencias/12-conteudo-backup.png`

## 8. Preparação da recuperação

Foi criada uma pasta independente:

```bash
mkdir -p ~/teste-restauracao
```

## 9. Restauração

O backup foi restaurado através de:

```bash
tar -xzvf ~/backups/topico-05/site-backup.tar.gz \
-C ~/teste-restauracao
```

Os ficheiros recuperados foram listados com:

```bash
find ~/teste-restauracao -type f
```

**Evidência:** `evidencias/13-restauracao.png`

## 10. Validação da recuperação

A comparação entre os ficheiros originais e recuperados foi realizada através de:

```bash
diff -rq \
~/linux-seguranca-cloud/topico-03/atividade-individual/site/ \
~/teste-restauracao/
```

Se o comando não apresentar qualquer saída, significa que não foram identificadas diferenças entre os conteúdos comparados.

Também pode ser verificado o número de ficheiros:

```bash
find ~/linux-seguranca-cloud/topico-03/atividade-individual/site/ -type f | wc -l
find ~/teste-restauracao/ -type f | wc -l
```

**Evidência:** `evidencias/14-validacao-restauracao.png`

## 11. Conclusão

O procedimento permitiu criar um backup do conteúdo do serviço web, verificar o seu conteúdo, restaurá-lo numa área independente e comparar os ficheiros recuperados com os ficheiros originais.

