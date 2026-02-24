# Causas Raiz e Falhas de Processo

Esta seção consolida os fatores estruturais e processuais que contribuíram para a ocorrência das vulnerabilidades identificadas durante o Web Penetration Test do ZBX-SLA.

O objetivo não é atribuir responsabilidade individual, mas identificar pontos de melhoria no processo de desenvolvimento.

---

## 1. Confiança Excessiva no Frontend

### Observado
- Controle de visibilidade implementado apenas na interface.
- Ausência de validação explícita de autorização no backend.

### Impacto
- Violação do princípio do menor privilégio.
- Possibilidade de acesso direto a endpoints via requisições manuais.

### Ação Corretiva
- Tornar obrigatória validação de permissão no backend.
- Incluir verificação de autorização como item obrigatório em PR.

---

## 2. Ausência de Checklist de Segurança no Desenvolvimento

### Observado
- Funcionalidades entregues sem validação estruturada de segurança.
- Falta de padronização mínima para endpoints.

### Impacto
- Vulnerabilidades recorrentes.
- Falhas básicas não identificadas durante desenvolvimento.

### Ação Corretiva
- Implementar checklist obrigatório antes do merge.
- Integrar checklist ao template de Pull Request.

---

## 3. Code Review sem Foco em Segurança

### Observado
- Revisões focadas majoritariamente em lógica funcional.
- Ausência de validação explícita de controle de acesso.

### Impacto
- Falhas estruturais passaram despercebidas.
- Risco sistêmico não identificado preventivamente.

### Ação Corretiva
- Criar etapa formal de Security Review.
- Definir critérios mínimos de validação para autorização e autenticação.

---

## 4. Falta de Modelagem de Ameaças

### Observado
- Novas funcionalidades implementadas sem análise de possíveis cenários de abuso.
- Ausência de identificação de superfícies de ataque.

### Impacto
- Endpoints expostos sem avaliação de risco.
- Falta de visão adversarial durante o desenvolvimento.

### Ação Corretiva
- Realizar modelagem simplificada de ameaças em novas features.
- Identificar: atores, ativos, superfícies de ataque e possíveis abusos.

---

## 5. Tratamento Reativo de Segurança

### Observado
- Segurança aplicada após identificação de vulnerabilidade.
- Ausência de integração com ciclo contínuo de melhoria.

### Impacto
- Correções pontuais sem visão sistêmica.
- Risco de regressão futura.

### Ação Corretiva
- Integrar segurança ao ciclo de desenvolvimento (Secure SDLC).
- Realizar retestes periódicos.
- Monitorar métricas de recorrência.

---

# Consolidação das Causas Raiz

As vulnerabilidades identificadas não decorrem de falhas isoladas, mas de lacunas estruturais no processo de desenvolvimento:

- Falta de validação sistemática de autorização
- Ausência de padrão mínimo de segurança
- Revisões sem critério formal de segurança
- Falta de visão adversarial durante desenvolvimento

---

# Próximos Passos Recomendados

1. Formalizar checklist de segurança como política interna.
2. Instituir revisão de autorização como critério de aceite.
3. Inserir treinamento técnico periódico.
4. Definir responsável por governança de segurança aplicacional.
5. Monitorar indicadores de recorrência de vulnerabilidades.