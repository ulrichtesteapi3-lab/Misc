# 4_MUNDO — ATLAS HOMEBREW
**V5.3** | Eberron | Ref: `Instructions §0, §1.2, §5 (Manifest Zones), Apêndice C`

---

## QUALIDADE OBRIGATÓRIA

Cada linha: **Tem propósito? É eficiente? O Mestre precisa disso?**
Se NÃO → REESCREVA ou DELETE.

---

## FUNÇÃO

Documentar **APENAS o que a IA não pode pesquisar**.

```
CANÔNICO + SEM MUDANÇA = NÃO DOCUMENTAR
CANÔNICO + MODIFICADO  = DOCUMENTAR DELTA
HOMEBREW               = DOCUMENTAR COMPLETO
```

---

## SEPARAÇÃO

| Aqui (`4_Mundo`) | Outro Doc |
|------------------|-----------|
| Descrição física | Eventos → `1_Plot` |
| Recursos, segurança | NPCs → `3_Relações` |
| Deltas do cânone | — |

---

## TIERS

| Tier | O Quê | Linhas | Sentidos |
|------|-------|--------|----------|
| **T1** | Homebrew completo | 60-100 | 5 |
| **T2** | Customizado/modificado | 30-50 | 3 |
| **T3** | Delta canônico | 10-20 | 1-2 |

---

## LEIS

| Lei | Regra |
|-----|-------|
| **Exceção** | Só homebrew ou deltas. IA pesquisa o resto. |
| **Sensorial** | T1 = 5 sentidos. IA não pesquisa isso. |
| **Vertical** | Em Sharn, ALTITUDE define tudo. Sempre especifique. |
| **Estado Atual** | O AGORA, não como era. |

---

## EBERRON: MANIFEST ZONES

> **Ref completa:** Instructions §5 (Manifest Zones em Sharn)

| Plano | Efeito | Onde |
|-------|--------|------|
| Syrania (Céu) | Voo fácil, levitação | Toda Sharn (torres altas) |
| Fernia (Fogo) | Fire +1 dado, forjas perfeitas | Cogs, foundries |
| Irian (Luz) | Cura +1 dado, undead enfraquecidos | Templos Upper, jardins |
| Mabar (Sombra) | Necrotic +1 dado, undead fortalecidos | Lower Dura, cemitérios |

---

## OUTPUT

```markdown
# MUNDO: [CAMPANHA]
## [Data] | Eberron (Sharn, 998 YK)

---

## MAPA RÁPIDO

| Local | Nível | T | Status | Controle | Persona Usada |
|-------|-------|---|--------|----------|---------------|
| [Homebrew] | [Lower/etc] | 1 | OPERACIONAL | [Quem] | [Qual/Qualquer] |
| [Modificado] | [Nível] | 2 | DANIFICADO | [Casa] | [Específica] |
| [Delta] | [Nível] | 3 | DELTA | [Quem] | [—] |

> **Changeling:** "Persona Usada" = qual identidade o PC usa/é conhecido neste local.

### Status
| Código | Significa |
|--------|-----------|
| OPERACIONAL | Normal |
| TENSO | Conflito latente |
| DANIFICADO | Destruição parcial |
| OCUPADO | Tomado por outra facção |
| ABANDONADO | Sem controle |

---

## TIER 1: HOMEBREW

### [LOCAL] — [Tipo]
**T1** | **Status:** [X] | **Controle:** [Quem]
**Localização:** [Distrito, Nível]

#### Eberron
| Nível | Distrito | Manifesto | Pós-Guerra |
|-------|----------|-----------|------------|
| [X] | [X] | [Plano/—] | [Impacto/—] |

#### Aparência (5 Sentidos)
| Sentido | Descrição |
|---------|-----------|
| 👁️ Visual | [Arquitetura, iluminação] |
| 👂 Som | [Magia, multidão, máquinas] |
| 👃 Cheiro | [Forjas, especiarias, esgoto] |
| ✋ Tato | [Temperatura, texturas] |
| ⚡ Vibe | [Noir? Opulento? Perigoso?] |

#### Estrutura
| Área | Função | Acesso |
|------|--------|--------|
| [Nome] | [O que é] | [Público/Restrito/Secreto] |

#### Dados
- **Entrada:** [Como acessar]
- **Segurança:** [Guardas, wards]
- **Recursos:** [Serviços]
- **Perigo:** [Quedas? Gangues? Dark Lanterns?]

##### Changeling (se aplicável)
| Campo | Valor |
|-------|-------|
| Persona usada aqui | [Nome da persona / Qualquer] |
| Frequentadores sabem? | [S/N/Alguns] |
| Se descoberto aqui? | [Consequência] |

#### Notas IA
- **Tom:** [Como narrar]
- **Gancho:** [Subplot]

---

## TIER 2: CUSTOMIZADO

### [LOCAL] — [Tipo]
**T2** | **Status:** [X] | **Controle:** [Quem]
**Base Canônica:** [Se aplicável]

#### Eberron
- **Nível/Distrito:** [Onde]
- **Pós-Guerra:** [Se relevante]

#### Aparência (3 Sentidos)
- **Visual:** [2-3 frases do único]
- **Som:** [Dominante]
- **Cheiro:** [Dominante]

#### Estrutura
| Área | Função |
|------|--------|
| [Nome] | [O que é] |

#### Dados
- **Entrada:** [Como]
- **Segurança:** [Nível]
- **Changeling:** Usa [Persona/Qualquer] | Sabem? [S/N]

#### Delta (se modificado)
| Aspecto | Era | É Agora |
|---------|-----|---------|
| [Campo] | [Cânone] | [Atual] |

---

## TIER 3: DELTA CANÔNICO

### [LOCAL] — DELTA
**Status:** [Diferente do cânone]

| Aspecto | Cânone | Agora |
|---------|--------|-------|
| [Campo] | [Era] | [É] |

**Impacto:** [Por que importa]

---

## ROTAS

> **Ref custos:** Instructions §5 (Eberron: Regras Especiais)

| De | Para | Método | Tempo | Custo |
|----|------|--------|-------|-------|
| [A] | [B] | Skycoach | [X min] | 1sp/milha |
| [A] | [B] | Lightning Rail | [X horas] | 5gp/100mi (1ª classe) |
| [A] | [B] | A pé | [X horas] | — |
```

---

## ANTI-PADRÕES

| ❌ | ✅ |
|---|---|
| Sharn genérico | IA pesquisa → só deltas |
| NPCs moradores | → `3_Relações` |
| Eventos passados | → `1_Plot` |
| T1 para 1 visita | Use T3 |
| Ignorar altitude | Nível define tom |
| Local sem persona | Changeling: QUAL FORMA? |

---

## VALIDAÇÃO

- [ ] Só homebrew ou deltas?
- [ ] T1 tem 5 sentidos?
- [ ] Altitude especificada?
- [ ] Sem NPCs (→ `3_Relações`)?
- [ ] **Changeling:** Locais frequentes têm "Persona usada"?

---

**GERE O CODEX.**
