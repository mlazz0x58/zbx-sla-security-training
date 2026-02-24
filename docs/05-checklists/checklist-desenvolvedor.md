# Checklist de Segurança – Desenvolvedores

## Controle de Acesso
- [ ] Endpoint valida permissões no backend?
- [ ] Perfil do usuário é verificado explicitamente?
- [ ] Existe segregação clara entre perfis?

## Validação
- [ ] Parâmetros possuem validação?
- [ ] Valores inválidos retornam 4xx?

## Tratamento de Erros
- [ ] Exceções são tratadas?
- [ ] Mensagens não expõem detalhes internos?

## Autenticação
- [ ] Existe rate limit?
- [ ] Tentativas falhas são logadas?

## Exposição de Informações
- [ ] Debug está desabilitado?
- [ ] Não há exposição de paths internos?