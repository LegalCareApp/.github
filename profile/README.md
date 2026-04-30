# Legal Care Hub - Estado Atual da Organização

![Legal Care Banner](https://raw.githubusercontent.com/LegalCareApp/.github/main/profile/banner.png)

> Atualizado em: 27/04/2026

Plataforma SaaS jurídica com arquitetura modular em múltiplos repositórios (Backend, Web, Mobile, Docs, Integrations, Infra e Design-System).

---

## Status do Ciclo Atual

| Repositório | Status Local | Observação |
| --- | --- | --- |
| Backend | Em validação | `nest build` não expôs erro no log capturado; a conclusão final do processo ficou limitada pela ferramenta. |
| Web | Validado | `next build` concluiu no ciclo atual após hardening de runtime e ajustes de lint/typecheck. |
| Mobile | Validado | `npx tsc --noEmit` concluiu sem erros visíveis no ciclo atual. |
| Docs | Sincronizado | README, matriz de cobertura e checklist de release atualizados. |
| .github | Sincronizado | Organização refletindo Sprint 07 e os artefatos de release. |
| Infra | Em hardening | Baseline de Node 22 documentado nos repositórios de app e na infraestrutura. |
| Design-System | Dependente | Continua como camada compartilhada para tipagem e UI. |

---

## Sprint Atual

**Sprint 07 — Integration & Hardening**

Foco principal:
- convergência de contratos entre Backend, Web e Mobile;
- checklist único de pre-produção;
- matriz de cobertura documental;
- alinhamento de runtime e DX.

Arquivos de referência:
- `Docs/Docs-main/sprints/sprint-07-integration-hardening.md`
- `Docs/Docs-main/release-readiness-checklist.md`
- `Docs/Docs-main/coverage-matrix.md`

---

## Artefatos de Release

- [Checklist de Release](../../Docs-main/Docs-main/release-readiness-checklist.md)
- [Matriz de Cobertura](../../Docs-main/Docs-main/coverage-matrix.md)
- [README da Documentação](../../Docs-main/Docs-main/README.md)
- [Guia de Telas / Coverage](../../Docs-main/Docs-main/pages-guide.md)

---

## Bloqueios e Próximos Passos

1. Sincronizar `functional-spec.md` e `pages-guide.md` com os contratos atuais da Sprint 07.
2. Criar `CONTRIBUTING.md` na documentação técnica.
3. Registrar um changelog da Sprint 07 com os artefatos de release.
4. Revalidar o backend até obter o fim do `nest build` de forma explícita.
5. Revalidar `expo start` no Windows após a padronização do Node 22.

---

## Arquitetura dos Repositórios

1. **Backend**: NestJS + Prisma + PostgreSQL
2. **Web**: Next.js + TypeScript
3. **Mobile**: Expo + React Native + NativeWind
4. **Docs**: Documentação técnica, roadmap e guias
5. **Integrations**: Proxies e conectores externos
6. **Infra**: IaC, pipelines e operação
7. **Design-System**: Tipos compartilhados e base visual

---

> Para onboarding técnico rápido, consulte os READMEs de cada repositório, o roadmap ativo em `Docs/sprints` e o checklist único de release.
