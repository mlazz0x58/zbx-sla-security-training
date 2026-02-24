# Tratamento Inadequado de Erros (HTTP 500)

## Descrição

Erros internos não tratados podem ser explorados através de manipulação de parâmetros inválidos.

---

## Cenário Observado

- Valores extremos geraram HTTP 500
- Ausência de validação de entrada
- Exceções não tratadas adequadamente

---

## Riscos

- Divulgação de lógica interna
- Enumeração de comportamento
- Aumento de superfície de ataque

---

## Implementação Recomendada

```python
from rest_framework.exceptions import ValidationError


def safe_division(a, b):
    if b == 0:
        raise ValidationError("Parâmetro inválido")

    return a / b
```

## Diretrizes Técnicas

- Validar tipos e limites
- Retornar 4xx quando aplicável
- Centralizar tratamento de exceções
- Evitar exposição de stack trace