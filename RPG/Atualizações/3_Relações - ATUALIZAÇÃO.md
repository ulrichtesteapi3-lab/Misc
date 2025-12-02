# 3_RELAÇÕES — PATCH SOCIAL
**V6.4** | Eberron | Ref: `Instructions §0, §3 (Vozes), §4, §8 (Male/Female Gaze, Arquétipos), Apêndice B/C/G`

---

## QUALIDADE OBRIGATÓRIA

Cada linha: **Tem propósito? É eficiente? O Mestre precisa disso?**
Se NÃO → REESCREVA ou DELETE.

---

## FUNÇÃO

Processar **DELTAS** em NPCs após sessões. APENAS o que MUDOU.

**NPC Novo?** → Use `3_Relações - CRIAÇÃO`.

---

## SEPARAÇÃO

| Aqui (`3_Relações`) | Outro Doc (`1_Plot`) |
|---------------------|----------------------|
| Afinidade, Tensões | Localização atual |
| Perfil Íntimo | Agenda, Missões |
| Dinâmica, Shadow | Flags de Plot |

---

## SKIP — Quando NÃO Atualizar

- NPC só disse "olá" ou foi cenário
- Interação não mudou afinidade (Δ < ±2)
- NPC novo (→ CRIAÇÃO)
- Mudança só de localização (→ `1_Plot`)

---

## TRIGGERS

| Trigger | Δ Típico | Ações |
|---------|----------|-------|
| 🔴 Traição/Conflito | -2 a -4 | Afinidade + Tensão + Flag |
| 🔴 Salvou vida | +2 a +3 | Afinidade + Dinâmica |
| 🟡 Cena Íntima | +1 a +2 | Perfil Íntimo + Gaze |
| 🟡 Revelação | ±1 | Shadow atualizado |
| 🟡 Voz/Padrão de Fala | — | Atualizar Voz por Nação (§3) |
| 🟢 Changeling: Conheceu nova persona | — | "Conhece Como" atualizado |
| 🟢 Mudança de Tier | — | Promover/Rebaixar |

---

## OUTPUT

```markdown
# PATCH SOCIAL: Sessão [N]
## Campanha: [Nome] | [Data YK]

---

## RESUMO

| NPC | Δ | Afinidade | Conhece Como | Flag |
|-----|---|-----------|--------------|------|
| [Nome] | [±X] | [Antes→Depois] | [Persona] | `FLAG` |

---

### [NOME] — PATCH T[X]
**Afinidade:** [X] → [Y] 🔺/🔻 | **Conhece Como:** [Persona]

#### Evento
- **S[N]:** [O que aconteceu] → [Impacto]

#### Perfil Íntimo *(se cena sexual)*

> **Ref:** Male/Female Gaze → Instructions §8

- **Quem Iniciou:** [NPC/PC/Mútuo]
- **Gaze Usado:** [Male/Female/Misto]
- **Revelado:** [Kink/Limite/Vocabulário]

#### Changeling *(se aplicável)*
- **Sabe que é Changeling?** [Antes → Depois]
- **Se descobrir:** [Reação]

// Motivo: [Justificativa] - S[N]
```

---

## TEMPLATES POR TIER

### T1 (30-50 palavras)
```markdown
### [NOME] — PATCH T1
**Afinidade:** [X] → [Y] | **Conhece Como:** [Persona]

#### Evento
- **S[N]:** [Evento detalhado + impacto emocional]

#### Tensão *(se nova)*
- **[Nome]:** [Descrição]

#### Íntimo *(se cena)*
- **Gaze:** [Male/Female/Misto]
- **Dinâmica:** [O que revelou]

// Motivo: [Justificativa]
```

### T2 (15-25 palavras)
```markdown
### [NOME] — PATCH T2
**Afinidade:** [X] → [Y] | **Conhece Como:** [Persona]
**S[N]:** [Evento breve] → [Impacto]
**Íntimo:** [Gaze] | [Kink/Dinâmica revelado] *(se cena)*
```

### T3 (1 linha)
```markdown
### [NOME] — T3
**Δ:** [±X] | **Conhece Como:** [Persona] | **S[N]:** [Evento mínimo]
```

---

## CENÁRIOS CHANGELING

| Cenário | Ações |
|---------|--------|
| NPC conheceu nova persona | Atualizar "Conhece Como" |
| NPC viu transformação | "Sabe Changeling?" = Sim + Reação |
| NPC suspeita | "Sabe?" = Suspeita |
| Persona queimada com NPC | -2 a -4, Tensão, `1_Plot` flag |

> ⚠️ **CROSS-REF OBRIGATÓRIO:** Se NPC descobriu Changeling → `1_Plot` Intel Inimiga + Calor da persona

---

## ANTI-PADRÕES

| ❌ | ✅ |
|---|---|
| Localização aqui | → `1_Plot` |
| Δ < ±2 | Ignorar (não significativo) |
| NPC novo | → `3_Relações - CRIAÇÃO` |
| Sem "Conhece Como" | SEMPRE incluir (Changeling) |
| Patch sem evento | O que causou a mudança? |
| Cena íntima sem Gaze | Male/Female Gaze (§8) |
| NPC sem Voz | Tom por Nação (§3) |

---

## VALIDAÇÃO

- [ ] Só NPCs que MUDARAM (Δ ≥ ±2)?
- [ ] Todo NPC tem "Conhece Como"?
- [ ] Cenas íntimas têm Perfil Íntimo + Gaze?
- [ ] NPC T1/T2 tem Voz por Nação?
- [ ] Changeling descoberto → `1_Plot`?

---

**GERE O PATCH.**
