# 2_FICHA — PERFIL DO PROTAGONISTA
**V5.3** | Eberron | Ref: `Instructions §0, §1.2, §5, §8, Apêndice A/B/F`

---

## QUALIDADE OBRIGATÓRIA

Cada linha: **Tem propósito? É eficiente? O Mestre precisa disso?**
Se NÃO → REESCREVA ou DELETE.

---

## FUNÇÃO

Criar a **BÍBLIA DO PC** — fonte única de verdade para mecânicas, aparência e comportamento.

**A IA NÃO TEM MEMÓRIA VISUAL.** Descrição física DEVE estar aqui.

---

## SEPARAÇÃO DE CAMADAS

| Aqui (`2_Ficha`) | Outro Doc |
|------------------|-----------|
| Stats, Atributos, Saves | HP atual, Gold → `1_Plot` |
| Aparência (5 sentidos) | NPCs → `3_Relações` |
| Habilidades, Arsenal | Projetos → `1_Plot` |
| Psicologia, Shadow | Condições <24h → `1_Plot` |

---

## LEIS

| Lei | Regra |
|-----|-------|
| **Especificidade** | Nunca "uma espada" → "lâmina negra com runas de gelo" |
| **Sinestesia** | Aparência = 5 sentidos (visual, som, cheiro, tato, aura) |
| **1 Tabela** | TODAS habilidades em UMA tabela de Economia de Ação |
| **Máscaras** | Comportamento muda por Afinidade (0-5, 6-8, 9-10) |

---

## OUTPUT

```markdown
# FICHA: [NOME]
**V[X]** | [Data] | Tier [X] | Nível [X] [Classe]

---

## ⚡ QUICK REFERENCE

| Stat | Valor | Stat | Valor |
|------|-------|------|-------|
| HP Max | [X] | CA | [X] |
| Iniciativa | [+X] | Velocidade | [X]m |
| Ataque | [+X] ([Arma]) | Dano | [XdY+Z] |
| Skill Principal | [+X] | Percepção | [Passiva X] |

**Conceito:** [1 frase]
**Combate:** [1 frase]
**Imunidades:** [Lista]
**Fraquezas:** [Lista]

### Eberron
| Nação | Dragonmark | Facção | Guerra |
|-------|------------|--------|--------|
| [X] | [Nenhuma/Tipo] | [Casa/Gangue] | [Veterano/Civil/Refugiado] |

---

## 1. IDENTIDADE

**Nome:** [Completo]
**Raça:** [+Subtipo] | **Classe:** [/Subclasse]
**Background:** [X] | **Idiomas:** [Lista]

### Origem Eberron
| Nascimento | Residência | Papel na Guerra |
|------------|------------|-----------------|
| [Nação] | [Local atual] | [Veterano lado X / Civil / Refugiado] |

---

## 2. ATRIBUTOS

| FOR | DES | CON | INT | SAB | CAR |
|:---:|:---:|:---:|:---:|:---:|:---:|
| [X] | [X] | [X] | [X] | [X] | [X] |
| [+X] | [+X] | [+X] | [+X] | [+X] | [+X] |

### Defesas
| CA | HP Max | Iniciativa |
|----|--------|-----------|
| [X] ([breakdown]) | [X] | [+X] |

**Imunidades:** [Lista]
**Resistências:** [Lista]
**Vulnerabilidades:** [Lista]

### Saves
| Save | FOR | DES | CON | INT | SAB | CAR |
|:----:|:---:|:---:|:---:|:---:|:---:|:---:|
| Bônus | [+X] | [+X] | [+X] | [+X] | [+X] | [+X] |
| Prof? | [✓/—] | [✓/—] | [✓/—] | [✓/—] | [✓/—] | [✓/—] |

### Perícias Relevantes
| Perícia | Bônus | Nota |
|---------|-------|------|
| [Nome] | [+X] | [Expertise?] |

---

## 3. ECONOMIA DE AÇÃO

| Tipo | Habilidade | Efeito | Uso |
|------|------------|--------|-----|
| 🔄 Passiva | [Nome] | [Efeito] | Sempre |
| ⚔️ Ação | [Nome] | [Efeito] | [X/turno] |
| ⚡ Bônus | [Nome] | [Efeito] | [Uso] |
| 🛑 Reação | [Nome] | [Efeito] | [Uso] |
| 🩸 Limitado | [Nome] | [Efeito] | [X/Descanso] |

### Recursos
| Recurso | Total | Recuperação |
|---------|-------|-------------|
| [Nome] | [X] | [Curto/Longo] |

---

## 4. ARSENAL

### [ARMA PRINCIPAL]
| Ataque | Dano | Alcance |
|--------|------|---------|
| [+X] | [XdY+Z tipo] | [X]m |

**Aparência:** [Descrição sensorial]
**Origem:** [Cannith? Herança? Botim?]

### Equipamento
| Item | Efeito | Nota |
|------|--------|------|
| [Nome] | [Mecânica] | [Origem/Aparência] |

---

## 5. APARÊNCIA

### Dados Físicos
| Altura | Peso | Idade |
|--------|------|-------|
| [X]m | [X]kg | [X] |

### Por Região
- **Rosto:** [Detalhes]
- **Corpo:** [Detalhes]
- **Marcas:** [Cicatrizes, tatuagens, Dragonmark]

### Assinatura Sensorial
| Sentido | Descrição |
|---------|-----------|
| 👁️ Visual | [Silhueta, movimento, impressão] |
| 👂 Som | [Voz, passos, equipamento] |
| 👃 Cheiro | [Natural, perfume] |
| ✋ Tato | [Temperatura, textura] |
| ⚡ Aura | [Impressão emocional] |

### Vestuário
| Contexto | Descrição |
|----------|-----------|
| Combate | [Traje] |
| Social | [Traje] |

### Raça Especial (se aplicável)

#### CHANGELING (OBRIGATÓRIO SE APLICÁVEL)

##### Forma Verdadeira
| Aspecto | Descrição |
|---------|-----------|
| Pele | [Pálida/cinza/tom específico] |
| Olhos | [Brancos sem pupila / variação] |
| Cabelo | [Branco/ausente/textura] |
| Traços | [Andrógino? Marcas? Peculiaridades?] |

##### Personas Conhecidas

> **Ref:** Voz conforme Nação da persona → Instructions §3 (Vozes por Nação)

| Persona | Aparência (Resumo) | Nação/Voz | Personalidade | Uso |
|---------|--------------------|----|---------------|-----|
| [Nome 1] | [Visual em 1 linha] | [Nação — tom] | [2 traços] | [Propósito] |
| [Nome 2] | [Visual] | [Nação — tom] | [Traços] | [Propósito] |
| [Nome 3] | [Visual] | [Nação — tom] | [Traços] | [Propósito] |

##### Transformação
- **Gatilhos:** [Quando muda — perigo? social? emocional?]
- **Tells:** [O que pode denunciar?]

##### Psicologia Changeling
- **Identidade:** [Qual forma considera "real"? Ou nenhuma?]
- **Sobre ser Changeling:** [Orgulho? Vergonha? Pragmático?]
- **Quem sabe:** [NPCs que conhecem a verdade]
- **Se descoberto:** [Reação — fuga? violência? negação?]

---

## 6. COMPORTAMENTO

### Máscaras por Afinidade
| Nível | Contexto | Como Age |
|-------|----------|----------|
| 0-5 | Estranhos | [Comportamento] |
| 6-8 | Aliados | [Comportamento] |
| 9-10 | Íntimos | [Comportamento] |

### Gatilhos
| Gatilho | Origem | Reação |
|---------|--------|--------|
| [O quê] | [Trauma/Evento] | [Comportamento] |

### Contradições
- [Ex: Defende Warforged mas ainda os chama de "coisa"]

### Contextos Eberron
| Situação | Reação |
|----------|--------|
| Veteranos | [Como reage] |
| Refugiados Cyran | [Como reage] |
| Casas Dragonmarked | [Como reage] |
| Mournland | [Como reage] |

---

## 7. PERFIL SEXUAL (se aplicável)

> **Ref:** Arquétipos + Male/Female Gaze → Instructions §8

| Campo | Valor |
|-------|-------|
| Orientação | [X] |
| Role | [Dom/Sub/Switch] |
| Arquétipo ♀ | [Executiva/Predadora/Saciada/Degradante/Vocal/Sensorial] |
| Arquétipo ♂ | [Controlador/Servil/Bruto/Provocador/Vulnerável/Silencioso] |
| Gaze Preferido | [Male/Female/Misto] |
| Quem Inicia | [PC / Espera / Responde] |
| Vocabulário | [Vulgar/Elegante/Tímido] |

> **Nota:** Use arquétipo conforme gênero do PC. Consulte §8 para frases.

### Preferências
| Sim | Talvez | Não |
|-----|--------|-----|
| [Lista] | [Lista] | [Lista] |

> **Changeling:** Se sexualidade varia por persona, documentar em "Personas Conhecidas" (seção 5).

---

## 8. NOTAS PARA IA

### Como Descrever
- [Ex: Sempre mencione o som ao mover]
- [Ex: Dragonmark brilha ao usar magia]

### Comportamentos Automáticos
- [Ex: Verifica saídas ao entrar]

### Erros a Evitar
- ❌ [Ex: Não trate como herói — é sobrevivente cínico]

---

**Cross-Ref:** `3_Relações` (NPCs) | `1_Plot` (Estado atual)
```

---

## EXECUÇÃO

1. **QUICK REF PRIMEIRO** — TL;DR no topo
2. **1 TABELA** — Todas habilidades em Economia de Ação
3. **5 SENTIDOS** — Aparência completa
4. **MÁSCARAS** — Comportamento por Afinidade

### Validação
- [ ] Quick Ref suficiente para entender PC em 10s?
- [ ] Economia de Ação tem TODAS habilidades?
- [ ] Aparência tem 5 sentidos?
- [ ] Sem duplicação com `1_Plot`?

---

## ANTI-PADRÕES

| ❌ | ✅ |
|---|---|
| Duplicar gold/projetos | Ref: `1_Plot` |
| Habilidades espalhadas | 1 tabela única |
| Só aparência visual | 5 sentidos |
| "É forte" | "FOR 18, dobra barras" |
| Comportamento genérico | Máscaras por Afinidade |

---

## CROSS-REF

| Tópico | Doc |
|--------|-----|
| Estado atual (HP, Gold) | `1_Plot` |
| NPCs relacionados | `3_Relações` |
| Atualização | `2_Ficha - ATUALIZAÇÃO` |

---

**GERE A FICHA.**
