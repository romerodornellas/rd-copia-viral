# copira-rd-viral

Skill de Claude Code que **assiste um vídeo viral de verdade** (frames + áudio) e devolve um **roteiro pronto pra gravar** no método Ressuscita Zumbi (Romero Dornellas): gancho ≤3s, esqueleto em 4 beats, narração palavra por palavra e CTA que fecha em venda.

Serve pra pegar um Reel/TikTok que bombou e transformar em roteiro replicável pro seu negócio (restaurante / delivery / qualquer nicho).

## ⚠️ Pré-requisito (não pule)

Esta skill **não funciona sozinha**. Ela chama por baixo a skill [`watch`](https://github.com/bradautomates/claude-video), que é quem "assiste" o vídeo. Instale primeiro:

1. **Skill `watch`** — do repo `bradautomates/claude-video`. Clone as skills dele pra dentro de `~/.claude/skills/`.
2. **Programas de sistema** que o `watch` usa:
   - [`yt-dlp`](https://github.com/yt-dlp/yt-dlp) — baixar o vídeo
   - [`ffmpeg`](https://ffmpeg.org/) — extrair frames e áudio
   - [`whisper.cpp`](https://github.com/ggerganov/whisper.cpp) — transcrição local (offline, sem custo)

No macOS, o básico:

```bash
brew install yt-dlp ffmpeg whisper-cpp
```

Sem a `watch` instalada, a `copira-rd-viral` avisa e para.

## Instalação

```bash
git clone https://github.com/romerodornellas/copira-rd-viral ~/.claude/skills/copira-rd-viral
```

Reinicie a sessão do Claude Code. A skill fica disponível como `/copira-rd-viral`.

## Uso

```
/copira-rd-viral <url-ou-arquivo-do-viral> [seu nicho/negócio]
```

Exemplos de gatilho:
- `/copira-rd-viral https://www.instagram.com/reel/XXXX/ hamburgueria`
- "copia esse viral"
- "monta o escopo replicador desse vídeo"

Ela assiste o vídeo, pergunta o seu nicho (se você não disse), e entrega o roteiro pronto.

## Como funciona

1. **Assiste** o viral com a `watch` (baixa, extrai frames, transcreve o áudio localmente).
2. **Aplica o método** por cima e devolve: o que roubar, gancho ≤3s, esqueleto em 4 beats, roteiro palavra por palavra (~30s), CTA que vende e a armadilha a evitar.

---

Feito por [Romero Dornellas](https://github.com/romerodornellas) — método Ressuscita Zumbi™.
