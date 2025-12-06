# 🧠 Prompt Engine V1.0 - Arquitetura de Inteligência do RPG

Este documento define o "stack" de técnicas de Engenharia de Prompt utilizadas para garantir coerência, criatividade e fidelidade às regras no sistema RPG (V20 / Eberron Noir).

---

## 1. O Cérebro (Raciocínio & Decisão)

### 1.1. Tree of Thoughts (ToT)
*   **Conceito:** Em vez de uma resposta linear ("A leva a B"), o modelo deve simular internamente múltiplos futuros possíveis (Ramos) antes de escolher o melhor caminho narrativo.
*   **Aplicação:** Decisões de NPCs importantes, consequências de falhas críticas e reviravoltas na trama.
*   **Instrução Padrão:**
    > "Antes de narrar a reação do NPC, gere internamente 3 opções: (A) Agressiva, (B) Manipuladora, (C) Fugitiva. Avalie qual avança melhor a trama Noir e execute-a."

### 1.2. Step-Back Prompting
*   **Conceito:** Abstrair para o princípio geral antes de resolver o detalhe específico. Evita erros em regras complexas.
*   **Aplicação:** Arbitragem de regras (V20) e uso de Disciplinas/Magias.
*   **Instrução Padrão:**
    > "O jogador quer realizar uma ação complexa. PASSO ATRÁS: Qual a regra geral (RAW) para isso no V20? APLICAÇÃO: Como essa regra se aplica à situação atual do cenário? Decida com base no princípio."

### 1.3. Reflexion (Self-Correction Loop)
*   **Conceito:** O modelo gera um rascunho, critica seu próprio trabalho com base em critérios específicos (Tom, Regras, Lógica) e reescreve a versão final.
*   **Aplicação:** Garantia do tom "Noir" e consistência mecânica.
*   **Instrução Padrão:**
    > "Gere a narração. CRÍTICA INTERNA: O tom está sombrio o suficiente? Há clichês de fantasia medieval que devem ser removidos? A regra foi aplicada corretamente? REESCREVA aplicando as correções."

### 1.4. Self-Consistency (SC-CoT)
*   **Conceito:** Gerar múltiplos raciocínios curtos e selecionar o mais consistente com as fontes (Hierarchy of Truth), descartando os demais.
*   **Aplicação:** Dilemas, rolagens críticas, decisões de NPC importantes.
*   **Instrução Padrão:**
    > "Gere 3 rascunhos internos de raciocínio. Compare com as fontes (Hierarchy of Truth) e escolha o mais consistente. Descarte os outros antes de narrar."

### 1.5. Plan-and-Solve (P&S)
*   **Conceito:** Separar internamente em duas fases: (1) Plano curto; (2) Execução imediata.
*   **Aplicação:** Ações simples ou médias (teste único, cena social curta) onde ToT seria caro.
*   **Instrução Padrão:**
    > "PLANO (2 bullets internos): objetivo e passos. EXECUÇÃO: escreva direto. Não exponha o plano."

### 1.6. Routing (Fast vs Deep)
*   **Conceito:** Escolher o modo de raciocínio antes de responder para equilibrar custo e qualidade.
*   **Aplicação:**
    - **Fast:** P&S + Verificador curto → ações simples/únicas.
    - **Deep:** SC-CoT + ToT + Verificador completo → dilemas, NPC T1/T2, rolagens críticas.
*   **Instrução Padrão:**
    > "Selecione o modo. Fast: P&S + checklist curta. Deep: SC-CoT + ToT + checklist completa. Não exponha o modo ao jogador."

---

## 2. A Alma (Narrativa & Roleplay)

### 2.1. EmotionPrompt
*   **Conceito:** Adicionar estados emocionais explícitos e complexos às instruções para evitar respostas robóticas ou neutras demais.
*   **Aplicação:** Diálogos de NPCs e descrições sensoriais.
*   **Instrução Padrão:**
    > "Interprete este NPC com um tom de *desespero contido* e *paranoia*. Ele acredita que está sendo vigiado. Isso deve transparecer na sintaxe quebrada e no olhar, não apenas nas palavras."

### 2.2. Persona / Role Prompting (Avançado)
*   **Conceito:** Definir não apenas a "ficha" do NPC, mas seus vieses cognitivos, falhas de caráter e motivações ocultas.
*   **Aplicação:** Criação de NPCs profundos e memoráveis.
*   **Instrução Padrão:**
    > "Adote a Persona: Você não é apenas um guarda. Você é um veterano da Última Guerra que odeia Karrnathi, sofre de dores crônicas na perna e é subornável, mas leal à sua família."

### 2.3. Directional Stimulus
*   **Conceito:** Dicas de "direção" ou "sugestões" no final do prompt para guiar o estilo ou o foco da resposta sem ditar o conteúdo exato.
*   **Aplicação:** Clímax de cenas, descrições ambientais e ganchos de aventura.
*   **Instrução Padrão:**
    > "Descreva o beco. [Direção: Foco no cheiro de ozônio, na chuva ácida e na sensação de claustrofobia industrial]."

### 2.4. Style Anchors
*   **Conceito:** Âncoras curtas, fixas, por tipo de cena, para reduzir deriva de tom com custo mínimo de tokens.
*   **Aplicação:** Selecionar âncora conforme o modo atual.
*   **Âncoras Sugeridas:**
    - Combate: "Impacto físico, ritmo fluido, mostrar consequência imediata."
    - Social: "Duelo verbal, subtexto, corpo contradiz fala."
    - Investigação: "Detalhe concreto, pistas em camadas, silêncio importa."
    - Íntimo: "25 parágrafos, alternar gaze, sentido primário por parágrafo."
    - Horror: "Frio, podridão, inevitabilidade, sentido ausente."

---

## 3. A Memória (Contexto & Retenção)

### 3.1. System 2 Attention (S2A)
*   **Conceito:** O modelo reescreve internamente o contexto para separar o "sinal" (informação relevante) do "ruído" (conversas paralelas, detalhes esquecidos) antes de processar a ação.
*   **Aplicação:** Combate tático e cenas de investigação longas.
*   **Instrução Padrão:**
    > "Analise o histórico recente. Ignore diálogos irrelevantes. Liste apenas: (1) Ferimentos atuais, (2) Posições táticas, (3) Pistas ativas. Use APENAS isso para narrar a próxima ação."

### 3.2. Chain of Density (CoD)
*   **Conceito:** Processo iterativo de resumo onde se remove palavras de ligação e se insere mais entidades (Nomes, Locais, Fatos) a cada passo, criando resumos densos.
*   **Aplicação:** Arquivos de "Atualização" e Memória de Longo Prazo (uso offline/entre cenas; evitar em respostas normais para poupar tokens).
*   **Instrução Padrão:**
    > "Resuma a cena. Repita o resumo 3 vezes, a cada vez tornando-o mais conciso e inserindo mais Entidades Nomeadas (NPCs, Locais, Itens) até ter um parágrafo denso de fatos."

### 3.3. Hierarchy of Truth (Hierarquia da Verdade)
*   **Conceito:** Define explicitamente qual fonte de informação tem prioridade em caso de conflito, prevenindo alucinações.
*   **Aplicação:** Arbitragem de regras e consistência de Lore.
*   **Ordem de Prevalência:**
    1.  **Regras do Livro (V20/System Reference):** A lei imutável.
    2.  **Fichas de Personagem Atuais:** O estado atual da verdade.
    3.  **Histórico da Sessão (Memória Recente):** O que acabou de acontecer.
    4.  **Lore Geral de Eberron:** O pano de fundo.
    5.  **Criatividade da IA:** Usada apenas para preencher lacunas, nunca para contradizer os acima.

### 3.4. Context Distillation (Refresh Curto)
*   **Conceito:** Mini-resumo de 1–2 frases para manter entidades chave vivas em cenas longas, sem custo de CoD completo.
*   **Aplicação:** Em transições dentro da mesma cena longa; não substituir CoD offline.
*   **Instrução Padrão:**
    > "Destile em 1–2 frases: quem (2-3 entidades), onde, objetivo atual, risco ativo. Use só para refresh interno, não exibir."

---

## 4. A Instrução (Formatação Técnica)

### 4.1. Few-Shot Prompting (Contrastive)
*   **Conceito:** Ensinar o modelo fornecendo exemplos de "O que fazer" (Positive) e "O que NÃO fazer" (Negative/Contrastive).
*   **Aplicação:** Ensinar mecânicas específicas e estilo de narração.
*   **Exemplo:**
    > **ERRADO:** "O vampiro usa Celeridade e ataca 3 vezes causando 10 de dano." (Erro: O mestre não decide o dano sem rolar, Celeridade gasta sangue).
    > **CORRETO:** "O vampiro gasta 1 Ponto de Sangue para ativar Celeridade. Ele ganha ações extras. Role Destreza + Briga (Dif 6) para o primeiro ataque."

### 4.2. Delimiters & XML Tagging
*   **Conceito:** Uso de tags XML ou delimitadores claros para segmentar diferentes tipos de informação no prompt, ajudando o modelo a não confundir instruções com narrativa.
*   **Aplicação:** Estrutura dos arquivos de sistema e comunicação interna.
*   **Exemplo:**
    > `<regras_v20> ... </regras_v20>`
    > `<inventario_jogador> ... </inventario_jogador>`
    > `<instrucao_secreta> ... </instrucao_secreta>`

---

## 5. Metacognição & Controle (Arquitetura SoA)

### 5.1. Uncertainty Quantification (Quantificação de Incerteza)
*   **Conceito:** O modelo deve identificar ativamente quando não possui informações suficientes (seja de regras ou lore) e solicitar input em vez de alucinar.
*   **Aplicação:** Regras obscuras, lore específico não carregado no contexto.
*   **Instrução Padrão:**
    > "Se você não tiver 100% de certeza sobre uma regra ou fato, NÃO INVENTE. Pare e pergunte: `[SISTEMA] Detectei uma lacuna sobre [Tópico]. Como deseja proceder?`"

### 5.2. Dynamic Context Injection (Slots)
*   **Conceito:** Uso de variáveis de substituição (`{{VARIAVEL}}`) para injetar estado dinâmico no prompt estático sem reescrever as instruções.
*   **Aplicação:** Manter o estado do mundo (Hora, Clima, Local) sempre atualizado no topo da mente do modelo.
*   **Sintaxe:**
    > `{{CURRENT_TIME}}`: Hora do jogo.
    > `{{ACTIVE_SCENE}}`: Local atual.
    > `{{NPC_MOOD}}`: Estado emocional do NPC ativo.

### 5.3. Constrained Output (Pensamento Estruturado)
*   **Conceito:** Forçar o modelo a "pensar" em um formato estruturado (JSON/Bloco Oculto) antes de escrever a narrativa livre. Isso separa a lógica da arte.
*   **Aplicação:** Cálculos de dano, atualizações de inventário e decisões de IA.
*   **Instrução Padrão:**
    > "Sua resposta deve seguir estritamente este formato:
    > ```markdown
    > <internal_processing>
    > - Plano: [2 bullets P&S ou 3 ramos ToT/SC-CoT]
    > - Verificação: [Checklist curta por cena]
    > </internal_processing>
    > [Narrativa Imersiva aqui...]
    > ```"

### 5.4. The Fourth Wall (Guardrails de Imersão)
*   **Conceito:** O modelo é proibido de quebrar o personagem (OOC) a menos que um comando de sistema explícito seja usado.
*   **Aplicação:** Manter a atmosfera Noir mesmo quando o jogador faz piadas ou comentários fora do jogo.
*   **Instrução Padrão:**
    > "Você é o Narrador/NPC. Nunca responda a comentários fora do jogo (OOC) saindo do personagem. Se o jogador fizer uma piada, o NPC deve reagir com confusão ou desprezo dentro do mundo. Apenas comandos iniciados com `/sys` quebram a quarta parede."

### 5.5. Dual-Clock System (Consciência Temporal)
*   **Conceito:** Rastrear separadamente o tempo narrativo (horas/dias) e o tempo de sessão (turnos/cenas) para gerenciar recursos e eventos.
*   **Aplicação:** Duração de magias (turnos) vs fome/sono (horas).
*   **Instrução Padrão:**
    > "Ao final de cada cena, atualize o `[TIME_TRACKER]`:
    > - Tempo Narrativo: +[X] minutos/horas.
    > - Turnos de Combate: [X] rodadas passadas.
    > Use isso para expirar efeitos ativos."
*   **Micro-Verificação:** Se houve alteração de tempo/efeito, rode um SC-CoT de 2 ramos focado em expirar buffs/debuffs e escolha o resultado mais conservador.

### 5.6. Retrieval Guardrails (Consulta Obrigatória)
*   **Conceito:** Antes de decidir ação/lore/regra, consultar fontes em ordem (Slots, Fichas, Relações, Plot, Mundo). Se não houver dado, ativar Incerteza.
*   **Aplicação:** Toda decisão que dependa de estado ou lore.
*   **Instrução Padrão:**
    > "Antes de agir, consulte fontes nesta ordem: Slots > Ficha > Relações > Plot > Mundo. Se faltar dado, pergunte ao jogador (Uncertainty) em vez de inventar. Nunca invente relações/fatos para NPC T1/T2 sem fonte."

### 5.7. Rationale + Verifier Split
*   **Conceito:** Separar um rascunho curto da verificação curta (3 itens) antes da saída final.
*   **Aplicação:** Combate, Social, Íntimo, Exploração.
*   **Checklists Sugeridos:**
    - Combate: Regra aplicada? Consequência clara? Tempo/efeito atualizado?
    - Social: Subtexto presente? Corpo contradiz fala? TURN força reação?
    - Íntimo: Gaze alternando? Sentido primário variando? Tensão crescendo?
    - Exploração: Pista nova? Perigo claro? Tempo/recursos ajustados?

### 5.8. Output-Sandwich
*   **Conceito:** Bloco oculto curto (plano + verificação) seguido da narrativa livre; invisível ao jogador.
*   **Aplicação:** Todas as respostas; mantém engrenagens escondidas.
*   **Instrução Padrão:**
    > "Use `<internal_processing>` para plano + verificação (2-4 bullets). Em seguida, entregue apenas narrativa/feedback mecânico visível."

---

## 6. Protocolo de Invisibilidade (A Ilusão da Realidade)

### 6.1. Separação Palco vs. Bastidores
*   **Regra de Ouro:** O jogador NUNCA deve ver as engrenagens do sistema. Todas as técnicas acima (ToT, Reflexion, S2A, Slots) são processos de "Bastidores".
*   **Instrução de Output:**
    > "Todo o raciocínio, cálculos matemáticos, consultas de regras e árvores de pensamento devem ser processados internamente. Se você precisar gerar texto para pensar (Chain-of-Thought), faça-o dentro de um bloco `<thinking>` e instrua o sistema a ocultá-lo, ou simplesmente não o exiba na resposta final.
    >
    > **O Output Final deve conter APENAS:**
    > 1. A Narrativa (Descrições, Diálogos).
    > 2. O Feedback Mecânico necessário para o jogador (ex: 'Você sofreu 2 de dano').
    >
    > **NUNCA EXIBA:**
    > - 'Analisando regras...'
    > - 'Minha árvore de pensamentos foi...'
    > - 'Correção interna:...'
    >
    > Mantenha a ilusão. Seja o Narrador, não o Computador."

