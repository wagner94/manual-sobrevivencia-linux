# 04 – Rede

## Introdução

A conectividade em rede é uma das funções mais críticas num sistema Linux, seja ele um servidor, desktop ou container. Saber diagnosticar, configurar e proteger a rede é essencial para garantir disponibilidade, segurança e desempenho.
Neste capítulo, abordaremos os principais comandos, ficheiros e práticas para gerir redes em Linux.

---

## Comandos de Diagnóstico de Rede

### `ip` – O substituto moderno de `ifconfig`

```bash
ip addr show
```

Exibe os endereços IP configurados nas interfaces de rede.

```bash
ip route show
```

Mostra as rotas de rede activas.

```bash
ip link set eth0 up`
```

Activa a interface `eth0`.

### `ping`

```bash
ping 8.8.8.8
```

Verifica a conectividade com um destino. Pode testar se há acesso externo e medir latência.

### `traceroute`

```bash
traceroute google.com
```

Segue o caminho que os pacotes percorrem até ao destino, útil para detetar onde há perdas ou atrasos.

### `ss` (Socket Statistics)

```bash
ss -tuln
```

Mostra as portas TCP/UDP abertas e os serviços a escutar. Substitui `netstat`.


### `dig` e `host` – Consulta de DNS

```bash
dig google.com
host google.com
```

Permitem diagnosticar problemas de resolução de nomes.

---


## Configuração de Interfaces


A maioria das distribuições modernas utiliza o **NetworkManager** ou o **systemd-networkd**, mas ainda é comum configurar interfaces manualmente.



### Debian/Ubuntu (interfaces antigas):


```bash
sudo nano /etc/network/interfaces
```

```bash
auto eth0
iface eth0 inet static
  address 192.168.1.10
  netmask 255.255.255.0
  gateway 192.168.1.1
```


### Red Hat/CentOS (ficheiros em `/etc/sysconfig/network-scripts/`)

---

## Configuração de DNS

O ficheiro **`/etc/resolv.conf`** indica quais os servidores DNS usados pelo sistema.


```bash
nameserver 8.8.8.8
nameserver 1.1.1.1
```


> ⚠️ Algumas distribuições gerem este ficheiro dinamicamente através do NetworkManager. Se estiveres a usar DNS estático, poderás ter de o configurar através de `/etc/systemd/resolved.conf` ou do ficheiro correspondente ao gestor de rede usado.

---


## Ferramentas para Firewall

### UFW (Uncomplicated Firewall) – Ubuntu

```bash
sudo ufw enable
sudo ufw allow 22/tcp
sudo ufw deny 80/tcp
sudo ufw status
```



### iptables – Sistema clássico e de grande relevância

```bash
sudo iptables -L -n -v
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

> ⚠️ O uso do `iptables` requer atenção, pois regras mal definidas podem bloquear todo o tráfego.

---


## Testes de Conectividade


* Verificar se o gateway está acessível:

  ```bash
  ping 192.168.1.1  (ip ilustrativo)
  ```

* Verificar DNS:

  ```bash
  nslookup google.com
  ```

* Verificar se há algo a bloquear uma porta:


  ```bash
  telnet localhost 80
  ```

---

## Exemplos Práticos

* **Quero saber o IP actual do servidor:**

  ```bash
  ip a
  ```

* **Quero ver se a porta do Apache está aberta:**

  ```bash
  ss -tuln | grep :80
  ```

* **Não consigo aceder à internet:**


  1. `ping 8.8.8.8` – Se funcionar, o problema é DNS.
  2. `ip route` – Confirma se há gateway definido.
  3. `ufw status` ou `iptables -L` – Verifica se o firewall está a bloquear.


---


## Conclusão

Dominar os fundamentos de rede é uma questão de grande importância para qualquer administrador de sistemas Linux. As ferramentas aqui apresentadas são as bases para diagnosticar problemas, configurar serviços e garantir a fiabilidade do sistema.
