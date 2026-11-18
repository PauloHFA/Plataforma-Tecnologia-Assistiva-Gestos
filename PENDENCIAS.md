# 📋 Pendências e Próximos Passos — Plataforma de Tecnologia Assistiva por Gestos (`GestoLivre`)

> Documento de rastreabilidade do backlog, melhorias sugeridas e itens pendentes para evoluções futuras da **Plataforma de Tecnologia Assistiva por Gestos (`GestoLivre`)**.

---

## 🚀 1. Backlog de Melhorias Futuras (Propostas)

### 1.1 Guia Sonoro e Feedback Auditivo para Acessibilidade Severa
- [ ] **Descrição:** Adicionar orientações por voz (*Text-to-Speech*) e bips sonoros (*Web Audio API*) durante calibrações de tremor e gravação de amostras.
- [ ] **Justificativa:** Pacientes com paralisia motora severa muitas vezes perdem o foco visual ao desviar os olhos para ler instruções na tela; o feedback sonoro garante autonomia completa.
- [ ] **Impacto:** Alto (Inclusão e usabilidade para deficiência visual associada).

### 1.2 Sincronização Criptografada de Perfis (E2EE Backup na Nuvem)
- [ ] **Descrição:** Módulo opcional de exportação/importação automática de perfis no Supabase/S3 com criptografia de ponta a ponta (AES-GCM baseada em senha - Zero Knowledge).
- [ ] **Justificativa:** Atualmente os perfis e modelos k-NN residem apenas no `IndexedDB` do navegador local. Trocas de computador exigem importação manual de arquivos `.gestolivre.json`.
- [ ] **Impacto:** Médio/Alto (Portabilidade segura de dados clínicos).

### 1.3 Relatório Terapêutico e Telemetria de Sessão
- [ ] **Descrição:** Painel analítico de uso diário gerando resumos em PDF/CSV com métricas de tempo ativo, taxa de acionamento por gesto, fadiga motora e estabilidade do cursor.
- [ ] **Justificativa:** Atende terapeutas ocupacionais e fonoaudiólogos que acompanham a evolução clínica de pacientes no uso da tecnologia assistiva.
- [ ] **Impacto:** Médio (Utilidade para clínicas de reabilitação).

---

## ✅ 2. O que já está Concluído (Status Atual)

- **Fundação & Core MVP (`@gestolivre/core`):** Normalização anatômica, classificador k-NN instantâneo, histerese, holdMs e perfis em IndexedDB.
- **Interface & Galeria (`@gestolivre/ui`):** Miniaturas de landmarks, galeria de amostras, contagem regressiva e auditoria WCAG 2.2 AA com `axe-core` (0 violações).
- **Acessibilidade Avançada:** Cursor de cabeça com *dwell click*, motor de varredura (scanning) 2D, rastreamento ocular por íris e calibrador adaptativo de tremores.
- **Desktop Bridge (`@gestolivre/bridge`):** Servidor WebSocket local seguro na porta `8765` e injeção nativa de eventos no SO (Windows, Linux, macOS).
- **PWA Offline e Exemplos:** Suporte offline completo (Service Worker) e 4 aplicações práticas de exemplo (Passador de slides, Comunicador CAA, Jogo do Dinossauro e Teclado Virtual por Varredura).

---

## 🛠️ 3. Dependências de Infraestrutura Externa
- Nenhuma dependência obrigatória de nuvem para funcionamento básico (roda 100% offline no navegador).
- Opcional: Servidor WebSocket local ativo (`gestolivre-bridge`) para injeção de teclas globais no sistema operacional.
