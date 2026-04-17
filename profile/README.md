# ⚖️ Legal Care Hub — Ecossistema Jurídico 360°

![Legal Care Banner](https://raw.githubusercontent.com/LegalCareApp/.github/main/profile/banner.png)

> **"Transformando a advocacia através da automação inteligente e design de alto impacto."**

Bem-vindo ao repositório central do **Legal Care Hub**, uma plataforma SaaS premium projetada para conectar advogados e clientes com máxima segurança, agilidade e produtividade.

---

## 🚀 Painel de Progresso (Live Status)

| Módulo Core | Progresso Local | Status | Funcionalidades em Produção |
| :--- | :--- | :--- | :--- |
| **Backend API** | ████████░░ 80% | 🟢 Estável | Auth JWT/RBAC, Motor de Documentos, Gestão de Casos. |
| **Frontend Web** | ██████░░░░ 65% | 🔵 Funcional | Dashboard Financeiro, Gestor de PDFs, Pipeline Legal. |
| **Mobile App** | ░░░░░░░░░░ 05% | 🔴 Pendente | Repositórios configurados, aguardando inicialização Expo. |
| **Documentação** | ██████████ 100% | 🟢 Completo | Roadmaps de Sprints, Guias de Páginas e Arq. de Sistemas. |

---

## 🗺️ Mapeamento de Interfaces (Web App)

A interface Web foi desenhada com estética **Deep Blue & Gold**, focada em UX para alta performance jurídica.

*   [x] **Landing Page**: Vitrine institucional premium.
*   [x] **Dashboard Financeiro**: Visualização de KPIs com Recharts.
*   [x] **Gestor de Documentos**: Automação completa via Templates.
*   [x] **Pipeline de Processos**: Gestão de status e movimentações.
*   [x] **Portal de Acesso**: Login integrado com NextAuth.js.
*   [ ] **Agenda de Prazos**: Calendário dinâmico (Sprint 02).
*   [ ] **Central de Mensagens**: Chat em tempo real (Sprint 02/03).

---

## 📦 Arquitetura dos Repositórios

O ecossistema é dividido de forma modular para suportar alta escalabilidade:

1.  **[Backend](https://github.com/LegalCareApp/Backend)**: NestJS, Prisma, PostgreSQL, Redis.
2.  **[Web](https://github.com/LegalCareApp/Web)**: Next.js 14, Tailwind CSS, Recharts.
3.  **[Mobile](https://github.com/LegalCareApp/Mobile)**: React Native, Expo.
4.  **[Docs](https://github.com/LegalCareApp/Docs)**: Central de inteligência e Roadmaps.
5.  **[Integrations](https://github.com/LegalCareApp/Integrations)**: Proxy para APIs de tribunais e sistemas legados.

---

## 🏗️ Roadmap Estratégico (Scrum)

Seguimos um planejamento baseado em 3 Sprints críticas, visando o lançamento do MVP em 45 dias:

### 🔹 Sprint 01: Foundation
*   **Status**: 🟢 **CONCLUÍDO**
*   **Entrega**: Infraestrutura Docker, Auth JWT, Design System e Landing Page.

### 🔹 Sprint 02: Core & Automation
*   **Status**: 🔵 **EM ANDAMENTO (WIP)**
*   **Entrega**: Motor de Documentos (Templates), Dashboard Financeiro e Gestão de Casos.

### 🔹 Sprint 03: Scalability & Payments
*   **Status**: ⚪ **PENDENTE**
*   **Entrega**: Integração Stripe/Asaas, Chat WebSocket e App Mobile funcional.

---

## 🔒 Segurança e Compliance (LGPD)

O Legal Care Hub foi construído sob o princípio de *Privacy by Design*:
*   **Criptografia**: Dados em trânsito (TLS 1.3) e em repouso (AES-256).
*   **Sigilo Profissional**: Auditoria de logs e isolamento total de dados por advogado.
*   **Conformidade**: Ferramentas nativas para gestão de consentimento e direitos do titular (LGPD).

---

## 👥 Contribuição e Equipe

Este projeto é gerenciado internamente pela equipe técnica do **Legal Care App**.
*   **Arquiteto/Lead**: [Dev-RuiDiniz](https://github.com/Dev-RuiDiniz)
*   **Tecnologias**: TypeScript, NestJS, Next.js, React Native, Prisma.

---

> [!IMPORTANT]
> Para instruções de instalação local de cada módulo, consulte o README específico em cada repositório acima.
