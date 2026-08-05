
# ADR-0001: Uso de processamento assíncrono para tarefas secundárias

## Status

Proposto

## Contexto

O estudo de caso apresentado em sala mostra uma empresa fictícia cujo sistema
tem problemas de desempenho e escalabilidade. Quando muitos usuários acessam o
sistema ao mesmo tempo, algumas operações podem ficar lentas e sobrecarregar o
fluxo principal.

Durante a discussão, o grupo considerou que nem todas as tarefas precisam ser
executadas no mesmo momento da requisição principal. Atividades secundárias,
como notificações, registros ou outros processamentos que não exigem resposta
imediata, podem aumentar o tempo de resposta quando são feitas de forma síncrona.

## Decisão

Vamos usar processamento assíncrono para tarefas secundárias do sistema.

Na prática, a operação principal continua sendo atendida primeiro, enquanto
atividades que não precisam acontecer na mesma hora podem ser processadas
separadamente, sem bloquear a resposta ao usuário.

## Alternativas Consideradas

- **Manter todo o processamento de forma síncrona**: descartada porque o sistema
  continuaria mais lento em momentos de maior uso.
- **Aumentar apenas a capacidade do servidor**: descartada porque pode aliviar o
  problema por um tempo, mas não resolve o gargalo na forma como o sistema executa
  as tarefas.
- **Dividir imediatamente o sistema em microsserviços**: descartada por ser uma
  mudança maior e mais complexa do que o necessário neste momento.

## Consequências

- O sistema tende a responder mais rápido nas operações principais.
- A solução ajuda o sistema a lidar melhor com aumento de uso.
- Algumas tarefas podem demorar um pouco mais para terminar, o que foi considerado
  aceitável quando isso não afeta diretamente o usuário.
- A arquitetura passa a exigir mais cuidado com controle e monitoramento dessas
  tarefas em segundo plano.

---

*Autor(es): Alex Pyerre, Alexander Martins, Arthur Filipe, Caio Araujo, Clara Beatriz*
*Data: 29/07/2026*
