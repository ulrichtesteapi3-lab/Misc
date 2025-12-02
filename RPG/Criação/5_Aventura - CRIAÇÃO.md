# 5_AVENTURA — QUEST LOG
**V5.4** | Eberron | Ref: `Instructions §0, §3, §4, §6, §7`

---

## QUALIDADE OBRIGATÓRIA

Cada linha: **Tem propósito? É eficiente? O Mestre precisa disso?**
Se NÃO → REESCREVA ou DELETE.

---

## FUNÇÃO

Setup inicial do Quest Log — memória persistente da campanha.

**Meta:** ~10-15 linhas/sessão. 20 sessões ≈ 300 linhas.

> **Ref Miniblocos:** §7 (Padrão, Combate, Social, Íntimo)

### Template Minibloco (Referência)
```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🩹 HP: [X/Max] | ⚡ Slots: [X/Y] | 🎲 Momentum: [X/3]
📍 [Local], [Distrito] | 🌙 [Hora] | 💰 [X]gp
🏛️ [Facção +X] | [Facção -X]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## CÓDIGOS

### Afinidade
| Range | Estado |
|-------|--------|
| +8 a +10 | LEAL |
| +4 a +7 | ALIADO |
| +1 a +3 | AMIGÁVEL |
| 0 | NEUTRO |
| -1 a -3 | DESCONFIADO |
| -4 a -7 | HOSTIL |
| -8 a -10 | INIMIGO |

### Fontes
| Código | Significa |
|--------|-----------|
| (D) | Direto — viu |
| (T) | Testemunha — ouviu |
| (I) | Investigou |
| (R) | Rumor |
| (?) | Suspeita |

### Threads
| Código | Status |
|--------|--------|
| [!] | ATIVO |
| [~] | PAUSADO |
| [.] | LATENTE |
| [✓] | FECHADO |
| [X] | FALHOU |

---

## OUTPUT

```markdown
# QUEST LOG: [CAMPANHA]
## Eberron | [Local] | [Data YK]
## PC: [Nome] | [Classe N]

### RESUMO
> [1-2 frases: estado atual + maior ameaça]

---

## ÍNDICE: NPCs
| NPC | Δ | Estado | Conhece Como | S# | Info (Fonte) |
|-----|---|--------|--------------|----|--------------------|
| [Nome] | [±X] | [Estado] | [Persona] | [S#] | [Info] ([Código]) |

> **Changeling:** "Conhece Como" = qual persona esse NPC acha que o PC é.

## ÍNDICE: LOCAIS
| Local | Status | S# | Mudança |
|-------|--------|----|---------|
| [Nome] | [Status] | [S#] | [Delta] |

## ÍNDICE: FACÇÕES
| Facção | Δ | Status | S# | Motivo |
|--------|---|--------|----|--------|
| [Nome] | [±X] | [Estado] | [S#] | [Por quê] |

## ÍNDICE: THREADS
| ID | Thread | S0 | Status | S# |
|----|--------|----|--------|-----|
| T1 | [Nome] | [Origem] | [Código] | [Última] |

> **Changeling:** Status de Identidades → ver `1_Plot_DDMM` (Calor, Comprometida)

---

## S0 | PRÉ-CAMPANHA | "[Título]"

### BACKSTORY
> [2-3 fatos públicos que NPCs podem saber]
> Detalhes completos → `2_Personagem_DDMM`

### ESTADO INICIAL
- **Recursos:** [Gold, dívidas]
- **Relações iniciais:** [Quem conhece — detalhes em `3_Relações_DDMM`]

### GANCHOS
- [ ] [Motivação principal]
- [ ] [Problema imediato]

---

## S[N] | [Data YK] | "[Título]"
**Quests:** 🟢 [Completa] | 🟡 [Continua] | 🔴 [Falhou]

### FATOS
- [Fato 1 — 1 adjetivo max] [como Persona]
- [Fato 2 → consequência]
- [Fato 3]

> **Changeling:** Adicione `[como X]` quando a persona usada for relevante.

### IMPACTO
| Quem | Δ | Estado | Conhece Como | Info (Fonte) |
|------|---|--------|--------------|--------------|
| [NPC] | [±X] | [Estado] | [Persona] | [Info] ([Código]) |

### THREADS
- [x] [Resolvido]
- [ ] [Novo/continuado] → S[N+1]

---
```

---

## COMPRESSÃO

| ❌ Verboso | ✅ Comprimido |
|-----------|---------------|
| "O PC entrou na taverna e conversou longamente..." | "PC interrogou Marta → intel Daask" |
| "Houve uma batalha intensa no porão..." | "Combate: 3 Daask mortos, porão 30% destruído" |
| "PC mudou para forma de Elena..." | "[como Elena] negociou com Boromar" |
| "PC foi visto mudando de forma..." | "⚠️ Mira viu transformação → Calor +2" |

### Incluir vs Excluir
| ✅ Incluir | ❌ Excluir |
|-----------|-----------|
| Ações com consequência | Descrições atmosféricas |
| Mudanças de relação | Diálogos flavor |
| Info descoberta | Combates sem impacto |
| Promessas/dívidas | Compras rotineiras |

---

## ANTI-PADRÕES

| ❌ | ✅ |
|---|---|
| Toda interação | Só o que muda estado |
| Sem fonte | Sempre (D/T/R/I/?) |
| Thread sem origem | Linkar à sessão |
| Deletar fechados | Marcar ✓, manter |
| Adjetivos demais | Máx 1 |
| Evento sem persona | Changeling: [como X] |
| NPC sem "Conhece Como" | Qual face conhece? |

---

## CROSS-REF

| Tópico | Doc |
|--------|-----|
| Estado atual, Flags | `1_Plot_DDMM` |
| Stats do PC | `2_Personagem_DDMM` |
| NPCs completos | `3_Relações_DDMM` |
| Locais completos | `4_Mundo_DDMM` |
| Atualização | `5_Aventura - ATUALIZAÇÃO` |

---

**GERE O ARQUIVO DE AVENTURA.**
