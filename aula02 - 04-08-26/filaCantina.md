# ADR-0002: Definir o funcionamento inicial do app da fila da cantina

## Status
Proposto

## Contexto
Observa-se que, no horário de almoço, a cantina do campus atinge sua capacidade
máxima, levando parte dos alunos a desistir de almoçar em razão do tempo de
espera na fila. Diante desse cenário, a coordenação propõe a implementação de um
aplicativo simples, por meio do qual o aluno reserve previamente o prato do dia
e, ao chegar, realize a retirada sem necessidade de aguardar na fila comum.

Cumpre destacar que o escopo do pedido permanece incompleto. Não há definição
quanto à forma de pagamento — se realizado pelo aplicativo ou presencialmente na
cantina — nem quanto ao procedimento a ser adotado nos casos em que um aluno
efetua a reserva e não comparece. Ademais, considerando que a operação da
cantina conta com estrutura reduzida — uma pessoa no caixa e duas na cozinha —,
depreende-se que a solução não pode depender de esforço operacional adicional
significativo.

## Decisão
Estabeleceram-se três decisões para a primeira versão do sistema:

1. Definiu-se que o foco principal do aplicativo será a redução da fila no
   horário de almoço.
2. Determinou-se que o pagamento permanecerá fora do escopo da primeira versão,
   continuando a ser realizado presencialmente na cantina.
3. Optou-se por não implementar, nesta primeira versão, cobrança automática de
   taxa para os casos de reserva sem comparecimento.

## Alternativas Consideradas
- **Inclusão de todas as funcionalidades já na primeira versão**: descartada por
  tornar a primeira versão mais complexa do que o necessário.
- **Priorização da garantia de disponibilidade de comida**: alternativa
  considerada, porém entendida como secundária diante da constatação de que o
  problema mais evidente do cenário é a fila.
- **Criação de multa automática para ausências**: descartada em razão da
  inexistência de definição prévia dessa regra por parte da coordenação.

## Consequências
- A primeira versão torna-se mais simples de ser testada.
- O aplicativo passa a concentrar-se no problema central percebido pelo aluno,
  qual seja, a fila.
- O pagamento presencial simplifica a operação inicial, ainda que mantenha parte
  do processo já existente.
- A questão relativa às reservas sem comparecimento permanece sem solução
  definitiva.
- Torna-se possível observar, em um primeiro momento, se a reserva de fato
  contribui para a melhoria da rotina, antes da introdução de novas regras.

## Justificativa das decisões

### Decisão 1: priorização da redução da fila
Essa decisão fundamenta-se no **Princípio 1 de Hooker**, segundo o qual o
sistema deve gerar valor real para o usuário. No contexto analisado, verifica-se
que o valor mais direto para o aluno consiste em não gastar tempo à espera na
fila.

### Decisão 2: exclusão do pagamento da primeira versão
Essa decisão fundamenta-se no **Princípio 2 de**, segundo o qual devem
ser deixados de fora do escopo inicial os elementos que não são essenciais para
validar a ideia central do sistema. Como o objetivo principal desta versão é
verificar se a reserva reduz a fila, o pagamento não precisa ser resolvido
agora — trata-se de uma funcionalidade adicional, e não do núcleo da proposta.
Por essa razão, optou-se por mantê-lo fora do escopo, o que reduz a
complexidade de implementação e permite testar a hipótese central de forma mais
rápida e viável.

### Decisão 3: não definição de multa automática nesta etapa
Essa decisão também se fundamenta no **Princípio 2**, uma vez que essa regra
permanece em aberto. Em vez de se estabelecer uma solução definitiva
prematuramente, optou-se por registrar o problema e postergar essa definição
para etapa posterior.

---
*Autor(es): Alex Pierre, Alexander Martins, Arthur Filipe, Caio Araujo, Clara Beatriz*
*Data: 04/08/2026*