# Broken Access Control (BAC)

## Descrição

Falhas de controle de acesso ocorrem quando o backend não valida adequadamente se o usuário autenticado possui permissão para acessar determinado recurso.

Relaciona-se ao OWASP Top 10 – A01:2021.

---

## Cenário Observado no ZBX-SLA

- Usuários com perfil restrito acessaram endpoints AJAX diretamente.
- O backend confiava na restrição do frontend.
- Não havia validação explícita de permissão.

---

## Riscos

- Exposição de informações internas
- Violação do princípio do menor privilégio
- Facilitação de reconhecimento interno

---

## Implementação Recomendada (Django REST Framework)

```python
from rest_framework.permissions import IsAuthenticated
from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework.exceptions import PermissionDenied


class FetchTriggersView(APIView):
    permission_classes = [IsAuthenticated]

    def get(self, request):
        if not request.user.has_perm("monitorings.view_triggers"):
            raise PermissionDenied("Usuário não possui permissão")

        return Response({"data": "resultado autorizado"})
```

## Diretriz Técnica

- Permissões devem ser verificadas no backend
- Nunca confiar exclusivamente em controles de interface
- Utilizar mecanismos nativos de autorização do framework