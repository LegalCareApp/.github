# ⚖️ Legal Care Hub — Ecossistema Jurídico 360°

![Legal Care Banner](https://raw.githubusercontent.com/LegalCareApp/.github/main/profile/banner.png)

> **"Transformando a advocacia através da automação inteligente e design de alto impacto."**

Bem-vindo ao repositório central do **Legal Care Hub**, uma plataforma SaaS premium projetada para conectar advogados e clientes com máxima segurança, agilidade e produtividade.

---

## 🚀 Painel de Progresso (Live Status - Sprint 04)

| Módulo Core | Progresso Local | Status | Funcionalidades em Produção |
| :--- | :--- | :--- | :--- |
| **Backend API** | ██████████ 95% | 🟢 Estável | Auth JWT/RBAC, Chat, Agendamentos, Financeiro, Docs. |
| **Frontend Web** | █████████░ 92% | 🟢 Funcional | 23/25 Telas Ready, Dashboards Dinâmicos, Wizard de Casos. |
| **Mobile App** | ░░░░░░░░░░ 05% | 🔴 Pendente | Repositórios configurados, aguardando fase de UI nativa. |
| **Documentação** | ██████████ 100% | 🟢 Completo | Roadmaps de Sprints (1-4), Guias e Especs Funcionais. |

---

## 🗺️ Mapeamento de Interfaces (Web App - 23/25 Concluídas)

A interface Web foi desenhada com estética **Deep Blue & Gold**, focada em UX para alta performance jurídica.

*   [x] **Landing Page & Área Pública**: 6/6 telas (100% Concluído).
*   [x] **Área Administrativa (Admin)**: 5/5 telas (100% Concluído).
*   [x] **Área do Cliente**: 8/8 telas (100% Concluído).
*   [x] **Área do Advogado**: 4/6 telas (WIP: Detalhe do Caso, Perfil Profissional).
*   [x] **Deep Dashboards**: Dashboards que se adaptam dinamicamente ao cargo do usuário.
*   [x] **Interação Legal**: Sistema de Chat e Agenda unificado funcionando entre Cliente e Advogado.

---

## 📦 Arquitetura dos Repositórios

O ecossistema é dividido de forma modular para suportar alta escalabilidade:

1.  **[Backend](https://github.com/LegalCareApp/Backend)**: NestJS, Prisma, PostgreSQL, Redis.
2.  **[Web](https://github.com/LegalCareApp/Web)**: Next.js 14, Tailwind CSS, Recharts.
3.  **[Mobile](https://github.com/LegalCareApp/Mobile)**: React Native, Expo.
4.  **[Docs](https://github.com/LegalCareApp/Docs)**: Central de inteligência e Roadmaps detalhados.
5.  **[Integrations](https://github.com/LegalCareApp/Integrations)**: Proxy para APIs de tribunais e sistemas legados.

---

## 🏗️ Roadmap Estratégico (Scrum Methodology) 🎯

### 🟢 Sprint 01: Foundation
*   **Entrega**: Infraestrutura Docker, Auth JWT, Design System e Landing Page. (Concluído)

### 🟢 Sprint 02: Core & Automation
*   **Entrega**: Motor de Documentos (Templates), Dashboard do Advogado e Gestão de Casos. (Concluído)

### 🟢 Sprint 03: Admin & Global Management
*   **Entrega**: Área Administrativa completa, Moderação de Usuários e KPIs Globais. (Concluído)

### 🟢 Sprint 04: Client Area & Interaction
*   **Entrega**: Onboarding do Cliente (Wizard), Chat em Tempo Real, Carteira e Agendamentos. (Concluído)

### ⚪ Sprint 05: Mobile Foundation (Next Steps)
*   **Foco**: Início da conversão das funcionalidades core para React Native.

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
