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
