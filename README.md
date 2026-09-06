# Fábrica

Harness de agente **portátil**. Não é um produto. Não é um projecto teu. É o sistema operativo que o Cursor (e outros agentes) carregam **em qualquer sessão**, depois de instalares uma vez neste computador.

Clonas este repo noutro PC → `npx skills add . -g` → o agente passa a ter os mesmos travões e o mesmo método, mesmo que a pasta aberta seja a pós, um clone aleatório, ou um folder vazio.

---

## O que é

Um pacote de **skills** (instruções que o agente lê sozinho quando o teu prompt cheira àquilo) + um **drop-in** opcional (`AGENTS.md` + dois agents) para colar dentro de um repo que clonaste da aula.

Cada skill é um ficheiro `SKILL.md` com:

- **description** — o gatilho. Está sempre visível para o modelo. Se o texto bater, ele abre o resto.
- **corpo** — o método. Curto de propósito, para ser seguido.

Não há paths da tua máquina. Não há nome de app. O case da pós (OpsPilot, Nexus, Kubernetes) aparece só como **padrão**, não como dependência.

---

## O que não é

- Não é a pasta da pós. A pós continua no Git da UNIPDS; tu clonas **isso** à parte.
- Não treina modelos. `finetune-gate` é um semáforo: na maior parte dos casos a resposta é **não treines**.
- Não sobe cluster. `k8s-ops` ensina o agente a falar e a auditar YAML; instalar Minikube é outro passo, se tu pedires.
- Não substitui o teu código. Spec → implementação. O `pensador` não escreve a feature.

---

## Instalar (um PC, uma vez)

```sh
git clone https://github.com/DaviBragaBA/fabrica.git
cd fabrica
npx -y skills add . -g -y
```

`-g` = global no **utilizador**. Qualquer janela do Cursor neste login vê as skills.

Actualizar depois de um `git pull`:

```sh
npx -y skills add . -g -y
```

### Drop-in (opcional)

Acabaste de clonar um repo da aula e queres o `AGENTS.md` **dentro desse clone**:

```sh
# na raiz do fabrica
cp drop-in/AGENTS.md /caminho/do-clone/
cp -r drop-in/.cursor /caminho/do-clone/
```

PowerShell:

```powershell
Copy-Item -Force .\drop-in\AGENTS.md C:\caminho\do-clone\
Copy-Item -Recurse -Force .\drop-in\.cursor C:\caminho\do-clone\
```

---

## Loop (qualquer prompt)

```
ideia  →  grilling
         ↓ sobreviveu
spec   →  spec-driven   (pensador)
         ↓ spec com done
código →  implementador + anti-slop
         ↓ se for irreversível
gate   →  approval-gate
```

Atalhos:

- “mete IA” → `ai-architecture` (agente vs regra; fine-tune quase nunca)
- Kubernetes / CrashLoop / self-healing → `k8s-ops`
- prompt JSON / TOON → `prompt-contract`
- thread longa / tokens → `context-budget`
- “vamos treinar” → `finetune-gate`
- criar / rever agente autónomo → `autonomous-agent`

---

## Skills

| Pasta | Gatilho típico | O que o agente faz |
|---|---|---|
| `grilling` | “faz sentido?”, plano, decisão | Entrevista em rondas. Não implementa enquanto houver pergunta aberta. Se for software/IA, pergunta **IA ou regra?** e **fine-tune ou RAG?** |
| `anti-slop` | texto, UI, README, código gerado | Corta prosa de chatbot, UI genérica, comentário que repete código, agente sem critério de paragem |
| `spec-driven` | “implementa X”, feature, spec | Exige `specs/NNN-slug.md` com contrato + **done** observável **antes** de código |
| `ai-architecture` | RAG, LLM, gateway, “mete IA” | Canvas: job → regra vs agente → conhecimento → runtime → gate → falha |
| `approval-gate` | apply, deploy, delete, pagar, e-mail | Dry-run + “sim/não”. Sem sim, não escreve no mundo |
| `k8s-ops` | Kubernetes, pod, GitOps, self-healing | Desired state. Gerar YAML → auditar → apply (com gate) → curar o **manifesto**, não “reiniciar mais forte” |
| `prompt-contract` | system prompt, JSON, TOON | Prompt como contrato: input, schema, recusa, temperatura |
| `context-budget` | conversa longa, tokens | Paga contexto só pelo que muda a próxima acção. Spec ganha à arqueologia do chat |
| `finetune-gate` | fine-tune, LoRA, “vamos treinar” | 4 perguntas. Um não = não treina. Dataset e eval **antes** de GPU |
| `autonomous-agent` | ReAct, harness, memória, LangGraph, multiagente | Ordem: harness → spec → loop → uma store → eval → gate. Time só no fim |

Agents (em `drop-in/.cursor/agents/`):

| Agent | Papel |
|---|---|
| `pensador` | Impacto, spec, lista de ficheiros. **Não** implementa |
| `implementador` | Executa a spec. Diff mínimo + testes. Sem spec, para |

---

## “Vamos treinar” (finetune-gate)

Não é um treino. É um **não**, até prova em contrário.

As quatro têm de pender a sim:

1. Tarefa estreita e repetida (mesmo schema, muitos casos iguais).
2. Prompt + RAG já falharam num eval real.
3. Dataset limpo (JSONL, sem PII/segredos).
4. Mais barato no ano do que um modelo grande.

Senão: melhor `prompt-contract` ou RAG. Treinar é o último passo, com ficha do modelo.

---

## Mapa com a pós (origem dos padrões)

A pós UNIPDS ensina os sistemas. Este repo **extrai o método** para qualquer pasta:

| Padrão no curso | Skill aqui |
|---|---|
| Disciplina 4 — agentes autónomos (OpsPilot) | `autonomous-agent` |
| Spec + Copilot com guardrails | `spec-driven`, `pensador` |
| Canvas agente vs regra, gateway, gate | `ai-architecture`, `approval-gate` |
| Geração / auditoria / self-healing K8s | `k8s-ops` |
| JSON prompt, TOON | `prompt-contract` |
| Vale a pena fine-tune? (Amplitude) | `finetune-gate` |

O código da aula continua no [repo da pós](https://github.com/unipds-engenharia-de-ia-aplicada/engenharia-de-software-com-ia-aplicada). Clona **esse** para fazer os labs. Este repo só viaja o cérebro.

---

## Layout

```
fabrica/
  README.md
  skills/           ← npx skills add . -g
    grilling/
    anti-slop/
    spec-driven/
    ai-architecture/
    approval-gate/
    k8s-ops/
    prompt-contract/
    context-budget/
    finetune-gate/
    autonomous-agent/
  drop-in/          ← opcional, copiar para um clone da aula
    AGENTS.md
    .cursor/agents/
```
