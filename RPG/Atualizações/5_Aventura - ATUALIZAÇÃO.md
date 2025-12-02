# 5_AVENTURA — APPEND SESSÃO
**V5.4** | Eberron | Ref: `Instructions §0, §3, §4, §6, §7`

---

## QUALIDADE OBRIGATÓRIA

Cada linha: **Tem propósito? É eficiente? O Mestre precisa disso?**
Se NÃO → REESCREVA ou DELETE.

---

## FUNÇÃO

Adicionar **NOVA SESSÃO** ao Quest Log. ~10-15 linhas/sessão.

**Setup inicial?** → Use `5_Aventura - CRIAÇÃO`.

### Template Minibloco (Referência)
```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🩹 HP: [X/Max] | ⚡ Slots: [X/Y] | 🎲 Momentum: [X/3]
📍 [Local], [Distrito] | 🌙 [Hora] | 💰 [X]gp
🏛️ [Facção +X] | [Facção -X]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## SEPARAÇÃO

| Aqui (`5_Aventura_DDMM`) | Outro Doc |
|-------------------------|-----------|
| Fatos → Consequências | NPCs detalhados → `3_Relações_DDMM` |
| Impacto (Δ) | Locais detalhados → `4_Mundo_DDMM` |
| Threads | Changeling Calor → `1_Plot_DDMM` |

---

## SKIP — Quando NÃO Atualizar

- Sessão só RP social sem Δ
- Nenhum NPC/local/thread mudou
- Nenhum fato com consequência

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
---

## S[N] | [Data YK] | "[Título]"
**Quests:** 🟢 [Completa] | 🟡 [Continua] | 🔴 [Falhou]

### FATOS
- [Ação → consequência] [como Persona]
- [Descoberta → implicação]
- [Decisão → resultado]

### IMPACTO
| Quem | Δ | Estado | Conhece Como | Info (Fonte) |
|------|---|--------|--------------|--------------|
| [NPC] | [±X] | [ESTADO] | [Persona] | [Info] ([Código]) |

### THREADS
- [✓] [Resolvido] → [resultado]
- [!] [Novo/Continua] → S[N+1]

---

## PATCHES DE ÍNDICES

### NPCs (só mudanças Δ ≥ ±2)
| NPC | Δ | Estado | Conhece Como | S# |
|-----|---|--------|--------------|-----|
| [Mudou] | [±X] | [ESTADO] | [Persona] | S[N] |

### Threads (só novos ou mudança de status)
| ID | Thread | Status | S# |
|----|--------|--------|-----|
| T[X] | [Nome] | [Código] | S[N] |

### Identidades Changeling *(se Calor/Status mudou)*
| Persona | Calor | Comprometida? | S# |
|---------|-------|---------------|-----|
| [Nome] | [Antes→Depois] | [S/N/Suspeita] | S[N] |

> Cross-ref: Atualizar também em `1_Plot_DDMM` (Identidades)
```

---

## COMPRESSÃO

| ❌ Verboso | ✅ Comprimido |
|-----------|---------------|
| "O PC entrou na taverna e conversou longamente com..." | "PC interrogou Marta → intel Daask" |
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
| Qual persona usou | — |

---

## CHANGELING: TRACKING

1. **FATOS:** Adicionar `[como X]` quando persona for relevante
2. **IMPACTO:** Coluna "Conhece Como" OBRIGATÓRIA
3. **Calor mudou?** → Cross-ref `1_Plot_DDMM` (não duplicar aqui)

---

## CENAS ÍNTIMAS: TRACKING

> **Ref:** Gaze + Arquétipos → §8

Quando houver cena íntima, registrar nos FATOS:
```
- Cena íntima com [NPC] [como Persona] → Gaze: [M/F/Misto], [Kink/Dinâmica]
```

**Cross-ref:** `3_Relações_DDMM` Perfil Íntimo do NPC

---

## ANTI-PADRÕES

| ❌ | ✅ |
|---|---|
| Todo NPC mencionado | Só Δ ≥ ±2 |
| Atmosfera/flavor | Só fatos → consequência |
| Thread sem ID | Sempre T[X] |
| Sem fonte | Sempre (D/T/I/R/?) |
| Evento sem persona | Changeling: [como X] |
| Duplicar Calor | Calor → `1_Plot_DDMM` |

---

## VALIDAÇÃO

- [ ] Sessão ~10-15 linhas?
- [ ] Só NPCs Δ ≥ ±2?
- [ ] Todo NPC tem "Conhece Como"?
- [ ] Threads têm ID?
- [ ] Changeling eventos com `[como X]`?
- [ ] Calor mudou? → Patch Identidades + `1_Plot_DDMM`
- [ ] Cena íntima? → Gaze (§8) registrado + `3_Relações_DDMM`

---

## CROSS-REF

| Tópico | Doc |
|--------|-----|
| Estado atual, Flags | `1_Plot_DDMM` |
| Stats do PC | `2_Personagem_DDMM` |
| NPCs completos | `3_Relações_DDMM` |
| Locais completos | `4_Mundo_DDMM` |
| Criação original | `5_Aventura - CRIAÇÃO` |

---

**PROCESSE A SESSÃO.**
