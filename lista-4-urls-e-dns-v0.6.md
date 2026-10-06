## 1 — Destrinchando URLs

Para cada URL abaixo, preencha a tabela com as "peças" da URL. Se uma peça não existir na URL, escreva "—". Se a porta não estiver escrita, escreva qual é a porta padrão e marque como *(implícita)*.

| # | URL |
|---|---|
| a | `https://www.sp.gov.br` |
| b | `http://www.exemplo.com.br:8080/pagina` |
| c | `https://mail.google.com/mail` |
| d | `http://192.168.1.10:8080/index.html` |

**Tabela a preencher:**

| # | Protocolo | Subdomínio | Nome | Sufixo | Porta | Caminho |
|---|---|---|---|---|---|---|
| a | | | | | | |
| b | | | | | | |
| c | | | | | | |
| d | | | | | | |

---

## 2 — Para pensar (responda em 2-3 frases)

A URL d (exercício 1) tem algo diferente das outras três. O que muda quando a URL tem só um número de IP, em vez de um nome? O DNS é necessário nesse caso? Por quê?

---

## 3 — Quatro URLs de escolha livre

Escolha **quatro URLs reais** que você conhece ou usa (sites, serviços, páginas de pesquisa, o que quiserem) e destrinche do mesmo jeito. (Dica: Para ver a URL completa, abra a página no navegador e clique na barra de endereço)

Regras:
- As quatro URLs devem ser **diferentes entre si**: tente variar o sufixo (`.com`, `.com.br`, `.gov.br`, `.edu.br`, `.org`...), e se possível encontrar uma com subdomínio diferente de `www`.
- Pelo menos uma URL deve ter **caminho** (algo depois da primeira `/`).
- Se encontrar alguma com **porta escrita**, ótimo, vale destacar.

**Tabela a preencher:**

| # | URL escolhida | Protocolo | Subdomínio | Nome | Sufixo | Porta | Caminho |
|---|---|---|---|---|---|---|---|
| a | | | | | | | |
| b | | | | | | | |
| c | | | | | | | |
| d | | | | | | | |

---

## 4 — Detetive de DNS

Você recebeu uma rede **com problemas**: o nome `www.turma.local` não abre a página como deveria. Seu trabalho é investigar, descobrir o que está errado, corrigir e provar que funcionou.

**O arquivo do caso:** será fornecido pelo professor.

Dica: Abra no Packet Tracer **sem alterar nada antes de investigar**.

### Relatório do detetive

Preencha uma linha para cada problema que você encontrar. Se achar mais problemas do que linhas, acrescente linhas. (registre com prints, se possível)

| # | O que eu percebi (sintoma) | Onde eu olhei | Qual era a causa | Como eu corrigi |
|---|---|---|---|---|
| a | | | | |
| b | | | | |
| c | | | | |
| d | | | | |

### Prova final

Depois de corrigir tudo, faça os três testes abaixo no PC1 e escreva o resultado de cada um (registre com prints, se possível):

| Teste | Resultado |
|---|---|
| Abrir `www.turma.local` no navegador | |
| `ping www.turma.local` no Command Prompt | |
| `nslookup www.turma.local` no Command Prompt | |

---

## 5 — Meu domínio

1. Escolha um nome só seu para o sufixo da rede, no lugar de `turma` (por exemplo, `www.seunome.local`).
2. No servidor DNS, cadastre **dois nomes** para a sua rede, os dois apontando para o IP do servidor Web:
   - o nome principal, com `www` (por exemplo, `www.seunome.local`);
   - um segundo nome com **outro subdomínio** à sua escolha (por exemplo, `loja.seunome.local` ou `intranet.seunome.local`).
3. No servidor Web, edite a página para mostrar o seu nome.
4. No PC1 (e também no PC2), abra os dois nomes no navegador e confira se a página aparece (registre com prints, se possível).

**Para registrar:** destrinche os dois nomes que você criou.

| Nome completo (hostname) | Subdomínio | Nome | Sufixo | Domínio |
|---|---|---|---|---|
| | | | | |
| | | | | |