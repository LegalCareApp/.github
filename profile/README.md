# Legal Care Hub - Estado Atual da Organizacao

![Legal Care Banner](https://raw.githubusercontent.com/LegalCareApp/.github/main/profile/banner.png)

> Atualizado em: 24/04/2026

Plataforma SaaS juridica com arquitetura modular em multiplos repositorios (Backend, Web, Mobile, Docs, Integrations, Infra e Design-System).

---

## Estado Atual Verificado (24/04/2026)

| Repositorio | Branch | Estado Git | Verificacao Tecnica | Status Atual |
| :--- | :--- | :--- | :--- | :--- |
| Backend | `main` | Sincronizado com `origin/main` | `npm run build` falha | Bloqueado |
| Web | `main` | Sincronizado com `origin/main` | `npm ci` falha por conflito de dependencias (`ERESOLVE`) | Bloqueado |
| Mobile | `main` | Sincronizado com `origin/main` | `npx tsc --noEmit` OK; `expo start` falha no runtime atual | Parcial |
| Docs | `main` | Sincronizado com `origin/main` | Documentacao existe, mas com partes desatualizadas sobre Mobile | Parcial |
| .github | `main` | Sincronizado com `origin/main` | README global atualizado para estado real | Em andamento |
| Integrations | `main` | Sincronizado com `origin/main` | Sem rotina de validacao automatizada confiavel no momento | Atenção |
| Infra | `main` | Sincronizado com `origin/main` | Base inicial presente; sem trilha completa de release gate | Atenção |
| Design-System | `main` | Sincronizado com `origin/main` | Tipos compartilhados presentes; falta esteira de build/test padronizada | Atenção |

---

## Bloqueios Atuais

1. Backend nao compila por incompatibilidades tipadas no modulo de documentos (`src/documents/documents.service.ts`).
2. Web nao instala dependencias com `npm ci` devido conflito entre `next-auth@4.0.0-next.26` e stack React atual.
3. Mobile inicia typecheck, mas falha em `expo start` no ambiente atual (Node 24 + Metro em Windows, erro ESM URL scheme).
4. Contratos consumidos por Mobile e Web nao estao plenamente convergentes no Backend (rotas e payloads ainda divergem em partes criticas).

---

## Proximo Sprint (Foco)

O proximo ciclo oficial esta definido como **Sprint 07 - Integracao e Hardening**, com foco em:

- convergencia de contratos API entre Backend, Web e Mobile;
- estabilizacao de build/instalacao/runtime em todos os repositorios;
- fechamento das lacunas funcionais de processos, chat, financeiro, perfil, push e documentos;
- checklist unico de readiness para pre-producao.

Arquivo fonte do roadmap:
- `Docs/sprints/sprint-07-integration-hardening.md`

Artefato PDF executivo:
- `C:\Users\RUI FRANCISCO\Desktop\Roadmap_LegalCare_Sprint07.pdf`

---

## Arquitetura dos Repositorios

1. **Backend**: NestJS + Prisma + PostgreSQL
2. **Web**: Next.js + TypeScript
3. **Mobile**: Expo + React Native + NativeWind
4. **Docs**: Documentacao tecnica, roadmap e guias
5. **Integrations**: Proxies e conectores externos
6. **Infra**: IaC, pipelines e operacao
7. **Design-System**: Tipos compartilhados e base visual

---

> Para onboarding tecnico rapido, consulte os READMEs de cada repositorio e o roadmap ativo em `Docs/sprints`.
