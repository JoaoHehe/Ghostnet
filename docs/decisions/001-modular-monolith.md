# ADR 001: Monolito modular com check-worker separado

## Contexto
Sete microsserviços desde o início trariam muita infraestrutura e contratos antes de existir qualquer funcionalidade.

## Decisão
Começar com um core-api modular (identidade, monitoramento, alertas, tempo real) e um check-worker separado para executar os checks.

## Consequências
- Menos deploys e menos complexidade no começo.
- As fronteiras entre módulos precisam ser respeitadas para facilitar uma extração futura.
- O check-worker escala de forma independente porque faz I/O de rede imprevisível.