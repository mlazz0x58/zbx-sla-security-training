# Exposição de Informações Sensíveis

## Descrição

Exposição indevida de dados técnicos ou internos a usuários não autorizados.

---

## Cenário Observado

- Enumeração de rotas
- Exposição de paths internos
- Mensagens detalhadas de erro

---

## Riscos

- Facilita ataques subsequentes
- Permite mapeamento detalhado da aplicação

---

## Diretrizes Técnicas

- Desabilitar debug em produção
- Padronizar mensagens genéricas
- Revisar retorno de exceções
- Revisar configurações de servidor