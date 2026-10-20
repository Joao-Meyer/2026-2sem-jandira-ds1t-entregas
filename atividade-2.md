# Atividade — A rede que eu herdei

Você é o novo técnico de redes do **Patas & Cia**, um pet shop com consultório veterinário e banho e tosa. O técnico anterior, **Seu Germano**, foi embora da cidade e deixou só o **caderno** dele. O dono, **Seu Rogério**, quer a rede funcionando **exatamente como o caderno descreve** e, antes de gastar dinheiro, quer saber **se pode confiar nesse caderno**.

> Quem escreveu o caderno é uma pessoa, e pessoas erram. Nada aqui garante que ele está certo.

O trabalho tem seis partes. Todo o Packet Tracer é feito **no mesmo arquivo**, da Parte 2 em diante. Salve com frequência.

(registre com prints, sempre que a tabela pedir uma prova)

---

## O Patas & Cia

- **Loja:** balcão na frente e uma sala nos fundos, onde ficam os servidores.
- **Consultório veterinário:** colado na loja, a 8 m da sala dos fundos.
- **Banho e Tosa:** num galpão separado, a **120 m** da loja. O cabo até lá passa rente ao **motor do compressor** da câmara de rações e ao **quadro de força**.
- **Estacionamento:** a câmera de segurança fica a **40 m** do balcão.
- **Clientes:** usam o Wi-Fi da loja enquanto esperam.

---
---

# 📓 INÍCIO DO CADERNO DO SEU GERMANO

> **Tudo o que está entre este título e o "FIM DO CADERNO" foi escrito pelo Seu Germano.** O resto deste documento é o seu trabalho. O caderno pode conter erros.

## Rede interna

`192.168.30.0`, máscara `255.255.255.0`.

**Regra da casa:** servidores com final **10, 20, 30…**; computadores a partir de **101**; outros equipamentos (câmeras, notebooks…) a partir de **201**. O final **201** já é do notebook do Seu Rogério.

| Dispositivo | Onde fica | IPv4 | Máscara | DNS (IPv4) |
|---|---|---|---|---|
| Servidor-Agenda | sala dos fundos | 192.168.30.10 | 255.255.255.0 | — |
| Servidor-DNS | sala dos fundos | 192.168.30.20 | 255.255.255.0 | — |
| PC-Balcao | loja | 192.168.30.101 | 255.255.255.0 | 192.168.30.20 |
| PC-Consultorio | consultório | 192.168.33.102 | 255.255.255.0 | 192.168.30.20 |
| PC-Tosa | banho e tosa | 192.168.30.103 | 255.255.255.0 | 192.168.30.10 |

## Rede dos clientes

`192.168.40.0`, máscara `255.255.255.0`, sem DNS.

| Dispositivo | IPv4 | Máscara |
|---|---|---|
| Cliente-1 | 192.168.40.101 | 255.255.255.0 |
| Cliente-2 | 192.168.30.104 | 255.255.255.0 |

## Serviços

- **Servidor-Agenda:** página inicial "Agenda do dia", com o nome do Patas & Cia e três consultas (invente os nomes dos bichos). Endereço que os funcionários usam: `http://agenda.patasecia.local:8080`
- **Servidor-DNS:** `agenda.patasecia.local` → `192.168.30.11`

## Mapa de cabos

No Packet Tracer, use cabo de cobre em todos.

| De | Para | Distância | Meio anotado |
|---|---|---|---|
| SW-Loja | SW-Consultorio | 8 m | par trançado |
| SW-Consultorio | SW-Tosa | 120 m | par trançado |
| SW-Loja | SW-Clientes | 3 m | par trançado |

Servidor-Agenda, Servidor-DNS e PC-Balcao ligam no **SW-Loja**; PC-Consultorio no **SW-Consultorio**; PC-Tosa no **SW-Tosa**; Cliente-1 e Cliente-2 no **SW-Clientes**.

## Anotações do Seu Germano

1. A câmera do estacionamento (a 40 m do balcão) manda o vídeo para o PC-Balcao por Bluetooth.
2. Para o galpão do Banho e Tosa usei cabo de par trançado Cat5e, que passa rente ao motor do compressor e ao quadro de força. (No rótulo do cabo: "alcance máximo recomendado: 100 m".)
3. A agenda de consultas é P2P: todo mundo acessa ao mesmo tempo, então ninguém manda em ninguém.
4. A rede interna usa 192.168.30.0, que é uma faixa pública, e por isso o provedor consegue enxergar os nossos computadores.
5. Montei em estrela: se um setor ficar sem energia, os outros continuam funcionando normalmente.
6. Os clientes ficam em outra rede (192.168.40.0) para não alcançarem o PC do balcão nem o servidor da agenda.
7. O DNS existe para ninguém precisar decorar número: ele traduz o nome no endereço do servidor.
8. HTTP e DNS são protocolos da camada de Aplicação.
9. A máscara 255.255.255.0 quer dizer que os três primeiros números são a rede. Por isso 192.168.30.101 e 192.168.31.101 estão na mesma rede e conversam direto.
10. A porta padrão do HTTP é a 80, por isso quem digita `http://` e o nome do site não precisa escrever a porta.
11. A impressora de etiquetas está ligada ao PC-Balcao e compartilhada com o PC-Consultorio: o PC-Balcao faz papel de cliente e de servidor ao mesmo tempo, sem servidor dedicado.

# 📓 FIM DO CADERNO DO SEU GERMANO

---
---

## Parte 1 — O que me cheira mal?

Antes de abrir o Packet Tracer, releia as **anotações** do caderno com desconfiança. Para cada uma, diga se está **✔ certa** ou **✘ errada**. Se estiver errada, escreva o que está errado e como deveria ser. (Cuidado: tem anotação certa no meio, e não precisa justificar as certas. Na 5, confira com o mapa de cabos.)

| # | Assunto da anotação | ✔ ou ✘ | Se ✘: o que está errado e como deveria ser |
|---|---|---|---|
| 1 | Câmera do estacionamento | | |
| 2 | Cabo até o galpão | | |
| 3 | Tipo de comunicação da agenda | | |
| 4 | Faixa de endereços da rede interna | | |
| 5 | Desenho da rede | | |
| 6 | Rede dos clientes | | |
| 7 | O que o DNS faz | | |
| 8 | Camada de HTTP e DNS | | |
| 9 | Máscara e rede | | |
| 10 | Porta do HTTP | | |
| 11 | Impressora compartilhada | | |

> Esta parte é só palpite: **o Packet Tracer é a prova.** Guarde suas respostas para comparar depois.

---

## Parte 2 — Montar do jeito que está escrito

Monte a rede **exatamente como o caderno manda**, inclusive o que você achou estranho na Parte 1. Só assim o Seu Rogério vai ver o que acontece com o caderno do jeito que ele está.

- 4 switches, 5 computadores/servidores da rede interna e 2 clientes, com os nomes do caderno;
- todos os endereços **IPv4** e o **DNS Server** de cada computador, como na tabela;
- no **Servidor-DNS**, o serviço **DNS** ligado com o registro do caderno;
- no **Servidor-Agenda**, a página "Agenda do dia" no serviço **HTTP**.

**Suspeitas na montagem** (algo que você notou digitando e que não notou na Parte 1):

| Onde | O que me chamou a atenção |
|---|---|
| | |

> **Só siga para a Parte 3 quando o PC-Balcao abrir a página pelo endereço IP do Servidor-Agenda** (`http://192.168.30.10`).

---

## Parte 3 — Os testes do Seu Rogério

O Seu Rogério montou uma lista de testes. Para cada um, ele escreveu o que **espera** que aconteça. Faça cada teste e preencha as duas últimas colunas.

> Atenção: em alguns testes o Seu Rogério **espera que não funcione**. Nesses, "deu o esperado" quer dizer que **falhou**.

| # | Teste | O Seu Rogério espera | O que aconteceu | Deu o esperado? (✔/✘) |
|---|---|---|---|---|
| 1 | No PC-Balcao: `ping 192.168.30.10` | funciona | | |
| 2 | No PC-Consultorio: `ping 192.168.30.10` | funciona | | |
| 3 | No PC-Tosa: `ping 192.168.30.10` | funciona | | |
| 4 | No PC-Balcao, abrir `http://agenda.patasecia.local:8080` | abre a agenda | | |
| 5 | No PC-Tosa, abrir `http://agenda.patasecia.local` | abre a agenda | | |
| 6 | No PC-Consultorio, abrir `http://agenda.patasecia.local` | abre a agenda | | |
| 7 | No Cliente-1: `ping 192.168.40.102` | funciona | | |
| 8 | No Cliente-1: `ping 192.168.30.101` | **não funciona** | | |
| 9 | No Cliente-1, abrir `http://192.168.30.10` | **não abre** | | |
| 10 | No Cliente-2, abrir `http://192.168.30.10` | **não abre** | | |
| 11 | **Desligue o SW-Consultorio** (clique no switch, aba **Physical**, botão de energia) e, no PC-Tosa: `ping 192.168.30.10`. O Seu Rogério diz: "o banho e tosa não pode parar por causa do consultório". | funciona | | |

Depois do teste 11, **ligue o SW-Consultorio de novo.**

---

## Parte 4 — Por que falhou?

Um teste que deu ✘ tem pelo menos um defeito por trás. **Um mesmo defeito pode derrubar mais de um teste, e um teste pode cair por mais de um defeito**: só considere um teste resolvido quando ele passar de verdade.

**4a. Investigação.** Para cada teste que **não deu o esperado**, escreva **o que você testou, na ordem, e o que viu em cada passo** (por exemplo: "ping pelo IP → ..., abri pelo IP → ...").

| Teste | Minha investigação, passo a passo |
|---|---|
| | |

**4b. Causas.** Agora liste cada **causa** que você encontrou (cuidado para não contar a mesma causa duas vezes), em que **camada do TCP/IP** ela mora, por quê, e conserte no Packet Tracer.

| # | Causa | Camada do TCP/IP | Por que essa camada? | Como consertei | Testes que passaram a dar o esperado |
|---|---|---|---|---|---|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |

(registre com prints: um do sintoma e um do conserto, para cada causa)

> **O último teste da lista (o 11) tem uma causa que você só resolve na Parte 5.** Deixe-o por último.

**4c. Para pensar** (duas ou três linhas cada):

1. No PC-Consultorio, a luz do cabo estava verde e o switch "enxergava" o computador, mas o `ping` para o servidor falhava. Em que camada do TCP/IP o problema **não** estava, e em qual estava? Como você sabe?
2. Algum teste só passou **depois de dois consertos**? Qual, e por que um conserto não bastou?
3. No teste 10, o Seu Rogério esperava que a página **não** abrisse. Se ela abriu, por que isso é um defeito, e não uma boa notícia? Qual anotação do caderno esse resultado contradiz?

---

## Parte 5 — Consertando o projeto

**5a. O galpão.** O defeito do teste 11 não é de configuração: está no **desenho** da rede.

1. Por que o teste 11 falhou? Explique o que acontece com o PC-Tosa quando o SW-Consultorio apaga.
2. **No Packet Tracer**, mude a ligação do SW-Tosa para que o galpão e o consultório **não dependam um do outro**. Repita o teste 11 (desligando o SW-Consultorio) e confirme que agora passa.
3. O que sua rede **ganhou** com essa mudança? E qual é o **novo ponto fraco**, isto é, qual equipamento, se apagar, derruba mais coisas agora?
4. No mundo real, qual meio de transmissão você usaria até o galpão? Justifique usando **as três pistas** do enunciado (distância, interferência e o rótulo do cabo).

**5b. A câmera.** O Seu Germano ligou a câmera por Bluetooth, e você já viu na Parte 1 que isso não serve.

| Pergunta | Sua resposta e justificativa |
|---|---|
| Que meio de transmissão você usaria entre a câmera e a rede? | |
| Em qual das duas redes (30 ou 40) a câmera deve ficar, e por quê? | |
| Que endereço IPv4 ela receberia, seguindo a regra da casa? | |

**5c. A câmera no Packet Tracer.** O Packet Tracer não tem a câmera do Patas & Cia, então vamos **representá-la com um computador**, como já fizemos com o Wi-Fi dos clientes.

1. Coloque um computador chamado **Camera-Estacionamento**, ligado ao **SW-Loja** (o cabo faz o papel do meio que você escolheu na 5b).
2. Configure o endereço IPv4 e a máscara que você decidiu na 5b.
3. No **PC-Balcao**, faça `ping` para a câmera e registre o resultado.

Se o `ping` não responder, o problema está na sua resposta da 5b ou na configuração: descubra qual dos dois e corrija.

(registre com prints: a topologia com a câmera e o `ping`)

---

## Parte 6 — Entregando o trabalho

**6a. O caderno corrigido.** Deixe para o próximo técnico um caderno em que dá para confiar. Preencha com os valores **finais, depois dos seus consertos**.

| Dispositivo | IPv4 | Máscara | DNS (IPv4) |
|---|---|---|---|
| Servidor-Agenda | | | |
| Servidor-DNS | | | |
| PC-Balcao | | | |
| PC-Consultorio | | | |
| PC-Tosa | | | |
| Cliente-1 | | | |
| Cliente-2 | | | |
| Câmera do estacionamento | | | |

- **Registro no DNS:** `__________` → `__________`
- **Endereço que os funcionários devem digitar:** `__________`
- **Ligações entre os switches (como ficaram):** `__________`

**6b. A mensagem para o Seu Rogério** (4 a 6 linhas, **sem termos técnicos**). Responda à pergunta dele: **"posso confiar no caderno?"** Diga o que estava errado, o que você mudou e o que ele deve providenciar no mundo real.

---

## Extra (escolha um ou mais)

- **a)** No modo **Simulation**, abra `agenda.patasecia.local` no PC-Tosa (com tudo consertado) e acompanhe os pacotes. O que sai primeiro: a pergunta ao DNS ou o pedido da página? Por quê?
- **b)** Ainda no **Simulation**, refaça o teste 8 (Cliente-1 → PC-Balcao). Onde o pacote para? Quem "desiste" e por quê?
- **c)** O consultório quer uma página própria, com os horários dos veterinários. Coloque um **segundo servidor** no SW-Consultorio (final **30**, seguindo a regra da casa) e um nome para ele, como `consultorio.patasecia.local`. Teste a partir do PC-Balcao.

---

## Entrega

Reúna as tabelas preenchidas, as respostas, os prints e a mensagem na sua issue do GitHub.
