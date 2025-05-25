# Gestão de Pacotes

A instalação e actualização de software no Linux é geralmente feita através de gestores de pacotes. O gestor utilizado depende da distribuição.

## Distribuições baseadas em Debian/Ubuntu (APT)

| Comando | Descrição |
|--------|-----------|
| `sudo apt update` | Actualiza a lista de pacotes disponíveis. |
| `sudo apt upgrade` | Actualiza os pacotes instalados. |
| `sudo apt install nome-do-pacote` | Instala um novo pacote. |
| `sudo apt remove nome-do-pacote` | Remove um pacote instalado. |
| `sudo apt autoremove` | Remove pacotes desnecessários. |
| `apt search palavra` | Pesquisa por pacotes. |

## Distribuições baseadas em Red Hat/CentOS/Fedora (DNF/YUM)

| Comando | Descrição |
|--------|-----------|
| `sudo dnf install nome-do-pacote` | Instala um pacote. |
| `sudo dnf update` | Actualiza todos os pacotes. |
| `sudo dnf remove nome-do-pacote` | Remove um pacote. |

## Distribuições baseadas em Arch Linux (Pacman)

| Comando | Descrição |
|--------|-----------|
| `sudo pacman -Syu` | Actualiza o sistema. |
| `sudo pacman -S nome-do-pacote` | Instala um pacote. |
| `sudo pacman -R nome-do-pacote` | Remove um pacote. |

## Pacotes Snap e Flatpak

| Comando | Descrição |
|--------|-----------|
| `snap install nome` | Instala um pacote Snap. |
| `flatpak install repositório nome` | Instala um pacote Flatpak. |



Cheat Sheet – APT vs DNF vs Zypper

Ação / Tarefa                        | apt (Debian/Ubuntu)           | dnf (Fedora)                   | zypper (openSUSE)
------------------------------------|-------------------------------|--------------------------------|-------------------------------
Atualizar lista de pacotes         | sudo apt update               | sudo dnf check-update          | sudo zypper refresh
Atualizar pacotes instalados       | sudo apt upgrade              | sudo dnf upgrade               | sudo zypper update
Atualização completa do sistema    | sudo apt full-upgrade         | sudo dnf upgrade               | sudo zypper dup
Buscar pacotes                     | apt search nome               | dnf search nome                | zypper search nome
Instalar pacote                    | sudo apt install pacote       | sudo dnf install pacote        | sudo zypper install pacote
Remover pacote                     | sudo apt remove pacote        | sudo dnf remove pacote         | sudo zypper remove pacote
Limpar pacotes não usados          | sudo apt autoremove           | sudo dnf autoremove            | sudo zypper remove --clean-deps
Ver info de um pacote              | apt show pacote               | dnf info pacote                | zypper info pacote
Listar pacotes instalados          | apt list --installed          | dnf list installed             | zypper se --installed-only
Adicionar repositório              | add-apt-repository ppa:...    | dnf config-manager --add-repo URL | zypper ar URL apelido
Remover repositório                | editar sources.list manual    | dnf config-manager --disable   | zypper rr apelido
Histórico de transações            | cat /var/log/apt/history.log  | dnf history                    | zypper history
Reverter uma transação             | N/A                           | dnf history undo <id>          | zypper install -f pacote_antigo
Bloquear pacote                    | sudo apt-mark hold pacote     | sudo dnf mark exclude pacote   | zypper addlock pacote
Desbloquear pacote                 | sudo apt-mark unhold pacote   | sudo dnf mark removeexclude pacote | zypper removelock pacote
Ver o que vai ser instalado        | apt install -s pacote         | dnf install --assumeno pacote  | zypper install --dry-run pacote


---

> Mantém o sistema actualizado e instala apenas o que for necessário. Um sistema limpo é um sistema estável.
