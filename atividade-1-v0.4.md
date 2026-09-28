# Atividade — "Projete a Rede"

Você vai escolher um cenário fictício (entre os fornecidos) e projetar a rede dele do zero. No fim, você monta e testa a rede no Packet Tracer, com prints como prova de que ela funciona de verdade.

---

## Escolha o seu cenário

Escolha **um** dos quatro cenários abaixo — o que mais fizer sentido pra você. Não precisa ser o mesmo que o colega ao lado.

| Cenário | Contexto |
|---|---|
| **A — Clínica pequena com dois setores** | 1 computador da recepção (agendamentos) numa sub-rede, e 1 computador do consultório + 1 servidor de prontuários eletrônicos em outra — a recepção não deve conseguir acessar os prontuários. |
| **B — Laboratório de informática com dois setores** | 8 computadores de alunos + 1 computador da coordenação + 1 servidor central, no mesmo laboratório — mas a rede da coordenação precisa ficar separada da rede dos alunos. |
| **C — Coworking** | 2 empresas diferentes dividindo o mesmo espaço físico, cada uma com os próprios dispositivos — o tráfego de uma não pode ser visto pela outra. |
| **D — Prédio comercial de 3 andares** | 3 escritórios pequenos, um por andar, compartilhando a mesma estrutura do prédio, mas operando como empresas independentes entre si. |

---

## Fase 1 — A Arquitetura (Cliente-Servidor x P2P)

**Tarefa:** decida se a rede do seu cenário é majoritariamente Cliente-Servidor, P2P, ou uma combinação das duas — e justifique por escrito em 2-3 frases.

**Pergunta pra te ajudar a pensar:** existe algum dispositivo no seu cenário que só *serve*, nunca *pede*? E algum que faz as duas coisas?

---

## Fase 2 — A Topologia (as 6 topologias)

**Tarefa:** desenhe (no papel ou já no Packet Tracer) a topologia física da rede do seu cenário, escolhendo entre as seis vistas em aula (Ponto a Ponto, Barramento, Estrela, Anel, Árvore, Malha) — ou uma combinação, considerando os diferentes setores do seu cenário.

**Pergunta pra te ajudar a pensar:** dá pra ligar todos os dispositivos do seu cenário uns com os outros diretamente? Por quê (não)?

---

## Fase 3 — A Linguagem (camadas e encapsulamento)

**Tarefa:** escolha um envio de dado específico dentro do seu cenário (ex.: um funcionário mandando um arquivo pro servidor). Em vez de descrever cada camada de forma técnica e seca, escreva um parágrafo curto **na primeira pessoa**, como se você fosse o próprio pacote de dados contando a sua jornada: o que acontece com você em cada camada, na ida (Aplicação → Transporte → Internet → Acesso à Rede) e, se quiser, também na chegada, sendo desembrulhado na ordem inversa.

**Pergunta pra te ajudar a pensar:** qual camada garante que você chegue *inteiro*, mesmo sendo um arquivo grande? Qual garante que você chegue ao *dispositivo certo*?

---

## Fase 4 — Endereçamento (IPv4)

**Tarefa:** atribua um endereço IPv4 privado a cada dispositivo do seu cenário, definindo:
- a faixa privada escolhida (`192.168.x.x`, `172.16-31.x.x` ou `10.x.x.x`) e por que ela é adequada ao tamanho do cenário;
- o endereço de cada dispositivo;
- uma sub-rede `/24` diferente para cada setor do seu cenário, explicando por que isso os impede de se enxergar.

---

## Fase 5 — Verificação no Packet Tracer

**Tarefa:** monte a rede do seu cenário no Packet Tracer, usando só o que você já sabe fazer:

1. Adicione os desktops e o(s) switch(es) necessários.
2. Configure o IP e a máscara de sub-rede de cada desktop (Desktop → IP Configuration), usando os endereços que você definiu na Fase 4.
3. Teste a comunicação abrindo o terminal de um dos desktops (Desktop → Command Prompt)

Teste pelo menos um `ping` **dentro** do mesmo setor (deve funcionar) e um `ping` **entre** setores diferentes (deve falhar). Mesmo que os setores estejam ligados ao mesmo switch (ou a switches sem ligação entre eles), dispositivos em sub-redes diferentes não vão conseguir se pingar — é esse o próprio efeito de isolamento que você está demonstrando, e ele não exige nada além do IP e da máscara que você já configurou.

**Entrega desta fase:** tire prints de tela de cada teste de `ping`, com uma legenda curta dizendo o que cada um mostra (ex.: "ping do PC1 pro Servidor — sucesso" ou "ping do Andar 1 pro Andar 2 — falha esperada"). Um ping que falha onde deveria falhar também é parte da prova.

---

## Entrega final

Sua entrega deve reunir:

1. As respostas escritas das Fases 1 a 4.
2. Os prints de tela dos testes da Fase 5, com legenda em cada um.
3. A entrega deve ser feita no padrão de issues pelo github