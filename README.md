<div align="center">

  ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
  ![AWK](https://img.shields.io/badge/AWK-4EAA25?style=flat&logo=gnubash&logoColor=white)
  ![Shell](https://img.shields.io/badge/Shell_Script-121011?style=flat&logo=gnu-bash&logoColor=white)

</div>

<div align="center">
  
  # awk-from-zero

  <img width="775" height="402" alt="awk_from_zero" src="https://github.com/user-attachments/assets/2b89e7c3-2d56-4aa4-905f-3685ffb5ed14" />

</div>
<p></p>

Arquivos de exemplo utilizados no artigo **"Entendendo o comando AWK do absoluto zero"**, publicado no [Medium](#artigo)

## 📁 Arquivos

| Arquivo | Descrição |
|---|---|
| `books` | Lista de livros com ID, título, ano, autor e preço, separados por tabulação |
| `numbers` | Arquivo simples com valores numéricos para exemplos de operações matemáticas |
| `access.log` | Log de acesso simulado no formato Apache/Nginx para exemplos com expressões regulares |

## Como usar

Clone o repositório e siga os exemplos do artigo:

```bash
git clone https://github.com/seu-usuario/awk-artigo.git
cd awk-artigo
```

### Exemplos rápidos

**Listar apenas os títulos dos livros:**
```bash
awk -F "\t" '{print $2}' books
```

**Listar título e autor:**
```bash
awk 'BEGIN{FS="\t"} {print $2, "-", "Autor :", $4}' books
```

**Somar todos os valores do arquivo `numbers`:**
```bash
awk '
BEGIN { print "Iniciando processamento de soma" }
{ total += $1 }
END { print "O total foi:", total }
' numbers
```

**Filtrar livros com preço acima de 60:**
```bash
awk 'BEGIN{FS="\t"} {if ($NF > 60) print $0}' books
```

**Buscar linhas de um IP específico no log:**
```bash
awk '/^192.168.0.10/ {print $0}' access.log
```

**Usuários com `/bin/bash` como shell, ordenados:**
```bash
awk -F ":" '$7 == "/bin/bash" {print $1}' /etc/passwd | sort
```

## Artigo

[Leia o artigo completo no Medium](https://medium.com/@igor.scuculhadev/entendendo-o-comando-awk-do-absoluto-zero-608ac62475b5)

## Referências

- [GNU AWK Documentação oficial](https://www.gnu.org/software/gawk/manual/)
- Linux Eficiente na linha de comando — Daniel J. Barrett
