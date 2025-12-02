# 4_MUNDO — PATCH ATLAS
**V6.4** | Eberron | Ref: `Instructions §0, §1.2, §5 (Manifest Zones, Custos), Apêndice C`

---

## QUALIDADE OBRIGATÓRIA

Cada linha: **Tem propósito? É eficiente? O Mestre precisa disso?**
Se NÃO → REESCREVA ou DELETE.

---

## FUNÇÃO

Processar **DELTAS** em locais após sessões. APENAS homebrew ou modificações.

**Local Novo?** → Use `4_Mundo - CRIAÇÃO`.

---

## SEPARAÇÃO

| Aqui (`4_Mundo`) | Outro Doc |
|------------------|-----------|
| Descrição física | Eventos → `1_Plot` |
| Status, Controle | NPCs → `3_Relações` |
| Sensorial atualizado | — |

---

## SKIP — Quando NÃO Atualizar

- PC visitou canônico sem modificar (IA pesquisa)
- Homebrew existente não mudou
- Mudança foi só de NPC (→ `3_Relações`)
- Evento sem impacto físico (→ `1_Plot`)

---

## TRIGGERS

| Trigger | Prioridade | Ações |
|---------|------------|-------|
| 🔴 Homebrew destruído/conquistado | ALTA | Status + Sensorial |
| 🔴 Novo homebrew descoberto | ALTA | Criar entrada |
| 🟡 Canônico modificado | MÉDIA | Criar/atualizar DELTA |
| � Manifest Zone descoberta | MÉDIA | Efeitos mecânicos (§5) |
| 🟢 Persona nova usada em local | BAIXA | Atualizar "Persona Usada" |
| 🟢 Rota/Custo descoberto | BAIXA | Adicionar em ROTAS |

---

## OUTPUT

```markdown
# PATCH ATLAS: Sessão [N]
## Campanha: [Nome] | [Data YK]

---

## RESUMO

| Local | Δ | Status | Persona Usada |
|-------|---|--------|---------------|
| [Nome] | [Mudança] | [Antes→Depois] | [Qual] |

---

### [LOCAL] — PATCH
**Status:** [Antes] → [Depois] | **Controle:** [Se mudou]

#### Sensorial *(se mudou)*
- **Visual:** [Nova descrição]
- **[Outro sentido]:** [Se relevante]

#### Changeling *(se aplicável)*
- **Persona usada:** [Antes → Depois]
- **Frequentadores sabem?** [S/N]

// Motivo: [Evento] - S[N]
```

---

## TEMPLATES

### Homebrew Modificado
```markdown
### [LOCAL] — PATCH
**Status:** [X] → [Y] | **Controle:** [Se mudou] | **Persona:** [Qual usa aqui]

#### Sensorial
- **Visual:** [O que mudou]

#### Estrutura *(se setores mudaram)*
| Setor | Mudança |
|-------|---------|
| [Nome] | [Destruído/Descoberto] |

// Motivo: [Combate/Evento] - S[N]
```

### Novo Delta Canônico
```markdown
### [LOCAL] — DELTA
**Base:** [Nome oficial]

| Aspecto | Cânone | Agora |
|---------|--------|-------|
| [Campo] | [Era] | [É] |

// Motivo: [O que causou] - S[N]
```

### Descoberto (Expandir depois)
```markdown
### [LOCAL] — DESCOBERTO
**Tier Sugerido:** [T1/T2/T3] | **Controle:** [Quem]
**Visual:** [Primeira impressão]

> Expandir em `4_Mundo - CRIAÇÃO` se importante.
```

### Nova Rota

> **Ref:** Custos → Instructions §5

```markdown
### ROTA — DESCOBERTA
| De | Para | Método | Tempo | Custo |
|----|------|--------|-------|-------|
| [A] | [B] | [Skycoach/Rail/Pé] | [X] | [1sp/mi ou 5gp/100mi] |

// Descoberto: S[N]
```

---

## CENÁRIOS CHANGELING

| Cenário | Ações |
|---------|-------|
| PC usou nova persona em local | Atualizar "Persona Usada" |
| PC foi visto transformando | "Frequentadores sabem?" = Sim |
| Local associado a persona queimada | ⚠️ Acesso comprometido |

---

## ANTI-PADRÕES

| ❌ | ✅ |
|---|---|
| Canônico não modificado | Ignorar (IA pesquisa) |
| NPCs moradores | → `3_Relações` |
| Eventos sem impacto físico | → `1_Plot` |
| Sem nível vertical (Sharn) | SEMPRE especificar |
| Local sem "Persona Usada" | Changeling: qual forma? |

---

## VALIDAÇÃO

- [ ] Só homebrew ou deltas?
- [ ] Altitude especificada (Sharn)?
- [ ] Changeling: "Persona Usada" atualizada?
- [ ] Sem NPCs (→ `3_Relações`)?

---

**GERE O PATCH.**
