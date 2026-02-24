# Ausência de Rate Limiting em Autenticação

## Descrição

Ausência de limitação de tentativas permite ataques de força bruta e credential stuffing.

---

## Cenário Observado

- Login sem limitação de requisições
- Possibilidade de múltiplas tentativas consecutivas

---

## Riscos

- Comprometimento de contas
- Aumento da superfície de ataque

---

## Implementação Recomendada

```python
from ratelimit.decorators import ratelimit

@ratelimit(key='ip', rate='5/m', block=True)
def login_view(request):
    pass
```

## Diretrizes Técnicas

- Implementar rate limiting
- Logar tentativas falhas
- Monitorar comportamento anômalo
- Avaliar política de senha