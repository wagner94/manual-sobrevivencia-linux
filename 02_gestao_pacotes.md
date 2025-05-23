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

---

> Mantém o sistema actualizado e instala apenas o que for necessário. Um sistema limpo é um sistema estável.
