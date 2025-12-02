# 4_MUNDO — PATCH ATLAS
**V5.4** | Eberron | Ref: `Instructions §0, §1.2, §5`

---

## QUALIDADE OBRIGATÓRIA

Cada linha: **Tem propósito? É eficiente? O Mestre precisa disso?**
Se NÃO → REESCREVA ou DELETE.

---

## FUNÇÃO

Processar **DELTAS** em locais após sessões. APENAS homebrew ou modificações.

**Local Novo?** → Use `4_Mundo - CRIAÇÃO`.

---

## ESTRUTURA DO ARQUIVO (Referência)

### Tiers
| Tier | O Quê | Linhas | Sentidos |
|------|-------|--------|----------|
| **T1** | Homebrew completo | 60-100 | 5 |
| **T2** | Customizado/modificado | 30-50 | 3 |
| **T3** | Delta canônico | 10-20 | 1-2 |

### Status
| Código | Significa |
|--------|----------|
| OPERACIONAL | Normal |
| TENSO | Conflito latente |
| DANIFICADO | Destruição parcial |
| OCUPADO | Tomado por outra facção |
| ABANDONADO | Sem controle |

---

## SEPARAÇÃO

| Aqui (`4_Mundo_DDMM`) | Outro Doc |
|-----------------------|-----------|
| Descrição física | Eventos → `1_Plot_DDMM` |
| Status, Controle | NPCs → `3_Relações_DDMM` |
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
| 🔴 Novo homebrew descoberto | ALTA | Template DESCOBERTO (expandir depois) |
| 🔴 **Promoção de Tier** | ALTA | Expandir seções (ver abaixo) |
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

> **Ref:** Custos → §5

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
| NPCs moradores | → `3_Relações_DDMM` |
| Eventos sem impacto físico | → `1_Plot_DDMM` |
| Sem nível vertical (Sharn) | SEMPRE especificar |
| Local sem "Persona Usada" | Changeling: qual forma? |
| Promoção sem expandir | T3→T2: +3 sentidos, +Estrutura |

---

## VALIDAÇÃO

- [ ] Só homebrew ou deltas?
- [ ] Altitude especificada (Sharn)?
- [ ] Changeling: "Persona Usada" atualizada?
- [ ] Sem NPCs (→ `3_Relações_DDMM`)?
- [ ] Promoção de Tier: Seções expandidas conforme novo Tier?

---

## PROMOÇÃO DE TIER

### T3 → T2
**Gatilho:** Local ganha importância (base de operações, esconderijo, ponto de encontro recorrente)

```markdown
### [LOCAL] — PROMOÇÃO T3 → T2
**Novo Tier:** T2 | **Motivo:** [Por que importa mais agora]

#### EXPANDIR (copiar estrutura T2):
- [ ] Eberron: +Nível/Distrito, +Pós-Guerra
- [ ] Aparência: 1-2 → 3 sentidos (Visual, Som, Cheiro)
- [ ] Estrutura: Tabela de Áreas/Funções
- [ ] Dados: +Entrada, +Segurança
- [ ] Changeling: +Persona usada, +Sabem?
- [ ] Delta: Se modificado do cânone, tabela Era/Agora

// Motivo: [Evento que elevou importância] - S[N]
```

### T2 → T1
**Gatilho:** Local vira central à campanha (quartel-general, local de confronto final, santuário)

```markdown
### [LOCAL] — PROMOÇÃO T2 → T1
**Novo Tier:** T1 | **Motivo:** [Por que é central]

#### EXPANDIR (copiar estrutura T1):
- [ ] Eberron: Tabela completa (Nível, Distrito, Manifesto, Pós-Guerra)
- [ ] Aparência: 3 → 5 sentidos (adicionar Tato, Vibe)
- [ ] Estrutura: Tabela com Acesso (Público/Restrito/Secreto)
- [ ] Dados: +Recursos, +Perigo
- [ ] Changeling: Tabela completa (Persona, Sabem?, Se descoberto?)
- [ ] Notas IA: +Tom, +Gancho

// Motivo: [Evento que tornou central] - S[N]
```

---

## CROSS-REF

| Tópico | Doc |
|--------|-----|
| Estado atual, Eventos | `1_Plot_DDMM` |
| Stats do PC | `2_Personagem_DDMM` |
| NPCs moradores | `3_Relações_DDMM` |
| Log de sessões | `5_Aventura_DDMM` |
| Criação original | `4_Mundo - CRIAÇÃO` |

---

**GERE O PATCH ATLAS.**
