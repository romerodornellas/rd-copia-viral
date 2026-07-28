---
name: copira-rd-viral
description: Assiste um vídeo viral de verdade (via a skill /watch) e devolve o ROTEIRO PRONTO pra replicar no método Ressuscita Zumbi do Romero Dornellas. Use quando alguém colar um link/arquivo de um Reel/TikTok/vídeo viral e quiser copiar pro próprio negócio (restaurante/delivery). Gatilhos "copia esse viral", "/copira-rd-viral <link>", "monta o escopo replicador desse vídeo", "roteiro pra copiar esse reel".
argument-hint: "<url-ou-arquivo-do-viral> [meu nicho/negócio]"
user-invocable: true
allowed-tools: Bash, Read, AskUserQuestion
---

# /copira-rd-viral — assiste o viral + método Romero = roteiro pra copiar

Transforma QUALQUER vídeo viral num roteiro pronto pra gravar, no método Ressuscita Zumbi (Romero Dornellas). Dois passos: **(1) ASSISTIR** o viral de verdade (frames + áudio) com a skill `/watch`, **(2) aplicar o MÉTODO** por cima. O diferencial é o passo 1: você não adivinha o vídeo, você VÊ.

## Passo 1 — Assistir o viral (grátis, local, nada pago)

Rode a skill `watch` pra ler o vídeo. Resolva o caminho do `watch.py` (primeiro que existir):

```bash
for W in "$HOME/.claude/skills/watch/scripts/watch.py" "$HOME/.codex/skills/watch/scripts/watch.py"; do
  [ -f "$W" ] && WATCH="$W" && break
done
[ -z "$WATCH" ] && echo "⚠️ Skill /watch não instalada. Instale: github.com/bradautomates/claude-video" && exit 1
python3 "$WATCH" "<url-ou-arquivo-do-viral>" --whisper local --detail balanced
```

- **Sempre `--whisper local`** — nada pago, transcrição offline.
- Se o `/watch` não estiver instalado, avise que é ele que dá "o olho de assistir vídeo" (repo do bradautomates) e pare.
- **Leia CADA frame** que o watch listar (ferramenta Read) + a transcrição. Só depois de VER, siga.

## Passo 2 — Montar o escopo replicador (método RZ) — ENXUTO

Com o que você viu e ouviu, entregue **curto e direto** (SEM 8 seções, sem enrolação), no tom nordestino do Romero, **ZERO travessão em-dash, zero clichê de IA**:

1. **O QUE ROUBAR** — o princípio do viral em 1 frase (o mecanismo, não a produção cara).
2. **GANCHO ≤3s** — 3 opções de primeira frase que param o dedo, SEM citar o produto.
3. **ESQUELETO (4 beats)** — Gancho → Bastidor/Prova → Payoff → CTA (o que cada beat FAZ).
4. **ROTEIRO PRONTO** — a narração palavra por palavra pra gravar no celular (~30s), adaptada ao nicho/negócio.
5. **CTA QUE VENDE** — verbo + oferta + prazo + palavra-código no WhatsApp (nunca "curta a experiência").
6. **ARMADILHA ZUMBI** — o 1 erro que faria o vídeo ficar bonito e NÃO vender.

## Regras

- Se o usuário NÃO passou o nicho/negócio, use `AskUserQuestion` e pergunte **1 coisa só** (que negócio é: nicho, cidade, ticket) antes de escrever o roteiro. Não invente o negócio.
- Feche mandando **validar 1 clipe-teste antes do lote** (Combo do Zumbi: não posta 1 e some).
- Não redescreva o vídeo. Entregue o transferível e acionável.
- É o método do Romero: gancho ≤3s, VPM RTT (Processo de Fabricação = mostrar o bastidor), ABC da Jornada, CTA que fecha em venda.
