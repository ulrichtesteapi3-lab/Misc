# 2_FICHA — PATCH PÓS-SESSÃO
**V6.4** | Eberron | Ref: `Instructions §0, §1.2, §3 (Vozes), §5, §8, Apêndice A/B/F`

---

## QUALIDADE OBRIGATÓRIA

Cada linha: **Tem propósito? É eficiente? O Mestre precisa disso?**
Se NÃO → REESCREVA ou DELETE.

---

## FUNÇÃO

Processar **DELTAS** na ficha após sessões. APENAS o que MUDOU.

**Regra:** Se muda TODA sessão → `1_Plot`. Se permanente/raro → aqui.

---

## SEPARAÇÃO

| Aqui (`2_Ficha`) | Outro Doc (`1_Plot`) |
|------------------|----------------------|
| HP Máximo, Stats | HP atual, Gold |
| Habilidades, Arsenal | Condições <24h |
| Aparência, Cicatrizes | Projetos, Missões |
| Changeling: Personas | Changeling: Calor |

---

## SKIP — Quando NÃO Atualizar

- Stats não mudaram
- Nenhum item/habilidade nova
- Sem cicatriz/trauma permanente
- Sessão só RP sem impacto mecânico

---

## TRIGGERS

| Trigger | Prioridade | Seções |
|---------|------------|--------|
| 🔴 Level Up | ALTA | Stats, Economia de Ação, Recursos |
| 🔴 Novo Item | ALTA | Arsenal, Quick Ref |
| 🟡 Cicatriz/Trauma | MÉDIA | Aparência, Gatilhos |
| 🟡 Changeling: Nova Persona | MÉDIA | Seção Changeling |
| 🟡 Changeling: Persona Comprometida | MÉDIA | Seção Changeling + `1_Plot` |
| 🟢 Dragonmark Evoluiu | MÉDIA | Quick Ref, Seção Dragonmark |
| 🟢 Perfil Sexual Mudou | BAIXA | Seção 7 (Arquétipo, Gaze, Kinks) |

---

## OUTPUT

```markdown
# PATCH: 2_FICHA
## v[X] → v[Y] | Sessão [N] | [Data]

---

## MUDANÇAS

| Seção | Tipo | Descrição |
|-------|------|-----------|
| [Nome] | [+/Δ/−] | [Breve] |

---

## [SEÇÃO COMPLETA]

[Conteúdo INTEIRO da seção — não só a linha]

// Motivo: [Evento] - S[N]

---

## CROSS-REF OBRIGATÓRIO

- [ ] `1_Plot`: [Se flag/calor mudou]
- [ ] `3_Relações`: [Se NPC novo]
```

---

## PROCESSAMENTO

### Level Up
```markdown
### LEVEL UP: [N] → [N+1]
- HP Máx: [X] → [Y]
- Prof: +[X] → +[Y] (se mudou)
- Novas Habilidades: [Lista]
```

### Nova Cicatriz
```markdown
| Marca | Local | Origem | Significado |
|-------|-------|--------|-------------|
| [Descrição] | [Corpo] | S[N] | [O que representa] |
```

### Changeling: Nova Persona

> **Ref:** Voz conforme Nação → Instructions §3 (Vozes por Nação)

```markdown
| Persona | Aparência | Nação/Voz | Personalidade | Uso |
|---------|-----------|----------|---------------|-----|
| [Nome] | [Visual] | [Nação — tom] | [Traços] | [Propósito] |

// Motivo: [Por que criou] - S[N]
```

### Changeling: Comprometida
```markdown
| Persona | Status | Quem Sabe | S# |
|---------|--------|-----------|-----|
| [Nome] | ⚠️ QUEIMADA | [Quem descobriu] | S[N] |

// ⚠️ OBRIGATÓRIO → `1_Plot`: Atualizar Intel Inimiga + Calor
```

### Perfil Sexual

> **Ref:** Arquétipos + Male/Female Gaze → Instructions §8

```markdown
### PERFIL SEXUAL — PATCH

| Campo | Antes | Depois |
|-------|-------|--------|
| Arquétipo | [X] | [Y] |
| Gaze Preferido | [X] | [Y] |
| Kink Descoberto | — | [Novo] |
| Limite Descoberto | — | [Novo] |

// Motivo: [Cena íntima com NPC X] - S[N]
```

---

## ANTI-PADRÕES

| ❌ | ✅ |
|---|---|
| Só linha que mudou | Seção INTEIRA |
| Gold/HP atual | → `1_Plot` |
| Condição <24h | → `1_Plot` |
| Sem justificativa | Sempre `// Motivo: S[N]` |
| Changeling sem cross-ref | `1_Plot` Intel OBRIGATÓRIO |

---

## VALIDAÇÃO

- [ ] Só seções que MUDARAM?
- [ ] Quick Ref atualizado se stats mudaram?
- [ ] Changeling: Persona tem Nação/Voz?
- [ ] Changeling: `1_Plot` cross-ref feito?
- [ ] Dragonmark: Flag em `1_Plot`?

---

**GERE O PATCH.**
