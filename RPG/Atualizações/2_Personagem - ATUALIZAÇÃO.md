# 2_PERSONAGEM — PATCH PÓS-SESSÃO
**V5.4** | Eberron | Ref: `Instructions §0, §1.2, §3, §4, §5, §8`

---

## QUALIDADE OBRIGATÓRIA

Cada linha: **Tem propósito? É eficiente? O Mestre precisa disso?**
Se NÃO → REESCREVA ou DELETE.

---

## FUNÇÃO

Processar **DELTAS** no personagem após sessões. APENAS o que MUDOU.

**Regra:** Se muda TODA sessão → `1_Plot_DDMM`. Se permanente/raro → aqui.

---

## ESTRUTURA DO ARQUIVO (Referência)

| Seção | Conteúdo |
|-------|----------|
| **Quick Ref** | TL;DR: HP Max, CA, Ataque, Conceito |
| **§1 Identidade** | Nome, Raça, Classe, Origem Eberron |
| **§2 Atributos** | FOR/DES/CON/INT/SAB/CAR, Saves, Perícias |
| **§3 Economia de Ação** | Tabela única: Passivas, Ações, Bônus, Reações, Limitados |
| **§4 Arsenal** | Armas, Equipamento (aparência + mecânica) |
| **§5 Aparência** | 5 sentidos, Vestuário, **Changeling: Personas** |
| **§6 Comportamento** | Máscaras por Afinidade, Gatilhos, Contradições |
| **§7 Perfil Sexual** | Arquétipo, Gaze, Preferências (se aplicável) |
| **§8 Notas IA** | Como descrever, Comportamentos automáticos, Erros a evitar |

---

## SEPARAÇÃO

| Aqui (`2_Personagem_DDMM`) | Outro Doc |
|---------------------------|----------|
| HP Máximo, Stats | HP atual, Gold → `1_Plot_DDMM` |
| Habilidades, Arsenal | Condições <24h → `1_Plot_DDMM` |
| Aparência, Cicatrizes | Projetos, Missões → `1_Plot_DDMM` |
| Changeling: Personas | Changeling: Calor → `1_Plot_DDMM` |
| — | NPCs → `3_Relações_DDMM` |

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
| 🔴 Level Up | ALTA | §2 Atributos, §3 Economia de Ação |
| 🔴 Novo Item | ALTA | §4 Arsenal, Quick Ref |
| 🟡 Cicatriz/Trauma | MÉDIA | §5 Aparência, §6 Gatilhos |
| 🟡 Changeling: Nova Persona | MÉDIA | §5 Changeling |
| 🟡 Changeling: Persona Comprometida | MÉDIA | §5 Changeling + `1_Plot_DDMM` |
| 🟢 Dragonmark Evoluiu | MÉDIA | Quick Ref, §1 Identidade |
| 🟢 Perfil Sexual Mudou | BAIXA | §7 Perfil Sexual |

---

## OUTPUT

```markdown
# PATCH: 2_PERSONAGEM
## v[X] → v[Y] | Sessão [N] | [Data]

---

## MUDANÇAS

| Seção | Tipo | Descrição |
|-------|------|-----------|
| [§X Nome] | [+/Δ/−] | [Breve] |

---

## [§X SEÇÃO COMPLETA]

[Conteúdo INTEIRO da seção — não só a linha]

// Motivo: [Evento] - S[N]

---

## CROSS-REF OBRIGATÓRIO

- [ ] `1_Plot_DDMM`: [Se flag/calor mudou]
- [ ] `3_Relações_DDMM`: [Se NPC novo]
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

> **Ref:** Voz conforme Nação → §3

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

// ⚠️ OBRIGATÓRIO → `1_Plot_DDMM`: Atualizar Intel Inimiga + Calor
```

### Perfil Sexual

> **Ref:** Arquétipos + Gaze → §8

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
| Gold/HP atual | → `1_Plot_DDMM` |
| Condição <24h | → `1_Plot_DDMM` |
| Sem justificativa | Sempre `// Motivo: S[N]` |
| Changeling sem cross-ref | `1_Plot_DDMM` Intel OBRIGATÓRIO |

---

## VALIDAÇÃO

- [ ] Só seções que MUDARAM?
- [ ] Quick Ref atualizado se stats mudaram?
- [ ] Changeling: Persona tem Nação/Voz (§3)?
- [ ] Changeling: `1_Plot_DDMM` cross-ref feito?
- [ ] Dragonmark: Flag em `1_Plot_DDMM`?

---

## CROSS-REF

| Tópico | Doc |
|--------|-----|
| Estado atual, Flags | `1_Plot_DDMM` |
| NPCs relacionados | `3_Relações_DDMM` |
| Locais homebrew | `4_Mundo_DDMM` |
| Log de sessões | `5_Aventura_DDMM` |
| Criação original | `2_Personagem - CRIAÇÃO` |

---

**GERE O PATCH DE PERSONAGEM.**
