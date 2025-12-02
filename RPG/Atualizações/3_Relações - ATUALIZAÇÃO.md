# 3_RELAÇÕES — PATCH SOCIAL
**V5.4** | Eberron | Ref: `Instructions §0, §3, §4, §8`

---

## QUALIDADE OBRIGATÓRIA

Cada linha: **Tem propósito? É eficiente? O Mestre precisa disso?**
Se NÃO → REESCREVA ou DELETE.

---

## FUNÇÃO

Processar **DELTAS** em NPCs após sessões. APENAS o que MUDOU.

**NPC Novo?** → Use `3_Relações - CRIAÇÃO`.

---

## ESTRUTURA DO ARQUIVO (Referência)

| Tier | Quem | Linhas | Sentidos | Fala |
|------|------|--------|----------|------|
| **T1** | Amantes, família | 60-100 | 5 | Diálogos longos |
| **T2** | Aliados, rivais | 30-50 | 3 | Diálogos médios |
| **T3** | Contatos | 10-20 | 1-2 | Máx 2 frases |

### Seções por Tier
| Tier | Seções Obrigatórias |
|------|---------------------|
| **T1** | Identidade, Eberron, Changeling, Aparência (5 sentidos), Personalidade, Dinâmica, Perfil Íntimo |
| **T2** | Identidade, Aparência (3 sentidos), Personalidade, Dinâmica, Íntimo (se aplicável) |
| **T3** | Visual (1 linha), Personalidade (2 traços), Eberron (breve), Valor, Marco |

---

## SEPARAÇÃO

| Aqui (`3_Relações_DDMM`) | Outro Doc |
|--------------------------|-----------|
| Afinidade, Tensões | Localização → `1_Plot_DDMM` |
| Perfil Íntimo | Agenda, Missões → `1_Plot_DDMM` |
| Dinâmica, Shadow | Flags de Plot → `1_Plot_DDMM` |

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
| � **Promoção de Tier** | — | Expandir seções (ver abaixo) |
| 🟡 Cena Íntima | +1 a +2 | Perfil Íntimo + Gaze |
| 🟡 Revelação | ±1 | Shadow atualizado |
| 🟡 Voz/Padrão de Fala | — | Atualizar Voz por Nação (§3) |
| 🟢 Changeling: Conheceu nova persona | — | "Conhece Como" atualizado |
| 🟢 Rebaixamento de Tier | — | Compactar (manter essência) |

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

> **Ref:** Gaze + Arquétipos → §8

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

> ⚠️ **CROSS-REF OBRIGATÓRIO:** Se NPC descobriu Changeling → `1_Plot_DDMM` Intel Inimiga + Calor da persona

---

## ANTI-PADRÕES

| ❌ | ✅ |
|---|---|
| Localização aqui | → `1_Plot_DDMM` |
| Δ < ±2 | Ignorar (não significativo) |
| NPC novo | → `3_Relações - CRIAÇÃO` |
| Sem "Conhece Como" | SEMPRE incluir (Changeling) |
| Patch sem evento | O que causou a mudança? |
| Cena íntima sem Gaze | Gaze (§8) |
| NPC sem Voz | Tom por Nação (§3) |
| Promoção sem expandir | T3→T2: +Dinâmica, +3 sentidos |

---

## VALIDAÇÃO

- [ ] Só NPCs que MUDARAM (Δ ≥ ±2)?
- [ ] Todo NPC tem "Conhece Como"?
- [ ] Cenas íntimas têm Perfil Íntimo + Gaze (§8)?
- [ ] NPC T1/T2 tem Voz por Nação (§3)?
- [ ] Changeling descoberto → `1_Plot_DDMM`?
- [ ] Promoção de Tier: Seções expandidas conforme novo Tier?

---

## PROMOÇÃO DE TIER

### T3 → T2
**Gatilho:** NPC ganha protagonismo (aliado, rival, interesse romântico)

```markdown
### [NOME] — PROMOÇÃO T3 → T2
**Novo Tier:** T2 | **Motivo:** [Por que importa mais agora]

#### EXPANDIR (copiar estrutura T2):
- [ ] Identidade: +Shadow, +Eberron completo
- [ ] Aparência: 1 → 3 sentidos (Visual, Voz, Marcante)
- [ ] Personalidade: +Gatilho principal
- [ ] Dinâmica: +Natureza, +Tensão, +Want/Need
- [ ] Changeling: +"Se descobrir?"
- [ ] Íntimo: Se potencial romântico → adicionar seção

// Motivo: [Evento que elevou importância] - S[N]
```

### T2 → T1
**Gatilho:** NPC vira amante, família, ou central à trama

```markdown
### [NOME] — PROMOÇÃO T2 → T1
**Novo Tier:** T1 | **Motivo:** [Por que é círculo íntimo]

#### EXPANDIR (copiar estrutura T1):
- [ ] Identidade: Tabela completa + Role narrativo
- [ ] Eberron: Tabela (Nação, Casa, Dragonmark, Guerra)
- [ ] Changeling: Tabela completa (Conhece, Sabe?, Se descobrir?, Outras personas)
- [ ] Aparência: 3 → 5 sentidos (adicionar Cheiro, Tato, Presença)
- [ ] Personalidade: +Amor (como demonstra afeto)
- [ ] Dinâmica: +Poder, expandir Tensão, Want/Need separados
- [ ] Perfil Íntimo: Tabela COMPLETA (Arquétipo, Dinâmica, Gaze, Kinks, Limites, Zonas, Aftercare)

// Motivo: [Evento que tornou íntimo] - S[N]
```

---

## CROSS-REF

| Tópico | Doc |
|--------|-----|
| Estado atual, Flags | `1_Plot_DDMM` |
| Stats do PC | `2_Personagem_DDMM` |
| Locais homebrew | `4_Mundo_DDMM` |
| Log de sessões | `5_Aventura_DDMM` |
| Criação original | `3_Relações - CRIAÇÃO` |

---

**GERE O PATCH SOCIAL.**
