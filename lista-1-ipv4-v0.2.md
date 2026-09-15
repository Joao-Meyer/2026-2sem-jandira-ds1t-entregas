## 1 — Converta cada número para a base pedida.

| # | Valor | Converter para |
|---|---| --- |
| a | `200` | binário |
| b | `45` | binário |
| c | `128` | binário |
| d | `00010101` | decimal |
| e | `11111111` | decimal |
| f | `11011111` | decimal |

---

## 2 - Para cada endereço, diga se ele é **público** ou **privado**.

| # | Endereço IP |
|---|---|
| a | `10.45.2.8` |
| b | `200.147.32.10` |
| c | `172.20.5.1` |
| d | `8.8.8.8` |
| e | `192.168.50.30` |

---

## 3 — Para cada endereço, a partir da máscara, identifique **a parte de rede** e **a parte de host**.

| # | Endereço IP | Máscara |
|---|---| --- |
| a | `172.16.8.34` | /24 |
| b | `200.180.90.15` | /24 |
| c | `10.20.5.9` | /8 |
| d | `172.16.8.34` | /16 |
| e (bônus) | `192.168.1.130` | /30 |

---

## 4 — Diga o que cada endereço abaixo representa (loopback, broadcast, ou "não é especial").

| # | Endereço | Rede | Máscara |
|---|---| --- | --- |
| a | `127.0.0.1` | `10.0.0.1` | /24 |
| b | `192.168.1.255` | `192.168.1.0` | /24 |
| c | `172.16.8.34` | `172.16.8.0` | /24 |

---

## 5 — Dado o endereço e a máscara, calcule o **endereço de broadcast** da rede.

| # | Endereço IP |  Máscara |
|---|---| --- |
| a | `10.20.30.5` |  /24 |
| b | `192.168.4.77` |  /24 |
| c | `10.5.20.100` |  /8 |
| d | `172.16.50.7` | /16 |

---

## 6 — Para cada par, com a máscara indicada, diga se os dois dispositivos estão **na mesma rede local** ou em **redes diferentes**.

| # | Endereço A | Endereço B | Máscara |
|---|---|---|---|
| a | `192.168.1.10` | `192.168.1.200` | /24 |
| b | `192.168.1.10` | `192.168.2.10` | /24 |
| c | `10.0.5.20` | `10.0.5.250` | /24 |
| d | `10.20.30.40` | `10.20.99.5` | /8 |
| e | `172.16.5.10` | `172.17.5.10` | /16 |
| f | `172.16.5.10` | `172.16.200.50` | /16 |
| g | `192.168.5.15` | `192.168.5.240` | /24 |
| h | `172.31.10.5` | `172.31.10.250` | /16 |
| i | `9.255.255.254` | `10.0.0.1` | /8 |
| j | `172.16.0.1` | `172.16.255.254` | /16 |