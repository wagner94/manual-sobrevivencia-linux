# Permissões e Propriedade

O controlo de acesso no Linux é feito através de permissões associadas a ficheiros e pastas. Compreender e gerir estas permissões é fundamental para garantir a segurança e a organização do sistema.

## Tipos de permissões

Existem três tipos de permissões:

- **r** (read): leitura
- **w** (write): escrita
- **x** (execute): execução

Estas permissões aplicam-se a três categorias:

- **Utilizador** (owner)
- **Grupo** (group)
- **Outros** (others)

Exemplo:

```bash
-rwxr-xr--
Significa:

O proprietário pode ler, escrever e executar
O grupo pode ler e executar
Outros podem apenas ler

Comandos principais            Comando	Descrição
ls -l	Mostra as permissões e propriedades de ficheiros/pastas.
chmod	Altera permissões de ficheiros/pastas.
chown	Altera o proprietário e grupo de ficheiros/pastas.
chgrp	Altera apenas o grupo associado a um ficheiro/pasta.

Uso do chmod
Notação simbólica:

chmod u+x script.sh    # dá permissão de execução ao proprietário
chmod g-w ficheiro.txt # retira permissão de escrita ao grupo
chmod o=r ficheiro.txt # outros podem apenas ler

Notação numérica:
Valor	       Permissão
7	leitura + escrita + execução
6	leitura + escrita
5	leitura + execução
4	leitura
3	escrita + execução
2	escrita
1	execução
0	nenhuma

Exemplo:
chmod 755 script.sh
Significa: dono com todas as permissões, grupo e outros com leitura e execução.

Gerir permissões é uma responsabilidade essencial para evitar riscos de segurança e garantir o bom funcionamento do sistema.

---
