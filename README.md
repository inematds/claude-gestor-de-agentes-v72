# Claude como gestor de agentes — curso INEMA v7.2

Saia do chat: coordene uma equipe de agentes no Claude. Oito aulas curtas, abertas e gratuitas:
sessões em segundo plano e agent view, a sessão gestora, Projects na nuvem, artifacts, custo e controle
(`/skill-doctor`, `/usage`, `/advisor`, status line, mods) e o seu sistema de gestão.

**Curso:** https://inematds.github.io/claude-gestor-de-agentes-v72/

| # | Aula | Página |
|---|---|---|
| 1 | A virada: do chat à gestão | `aulas/virada/` |
| 2 | A sessão por dentro (`/btw`, `/recap`, `/color`, tela dividida) | `aulas/sessao/` |
| 3 | Sessões em segundo plano (`claude --bg`, `claude agents`) | `aulas/segundo-plano/` |
| 4 | A sessão gestora: ela coordena, você decide | `aulas/sessao-gestora/` |
| 5 | Local, segundo plano ou nuvem (Projects) | `aulas/nuvem/` |
| 6 | Artifacts: do resultado ao link | `aulas/artifacts/` |
| 7 | Custo e controle | `aulas/custo/` |
| 8 | Seu sistema de gestão de agentes | `aulas/sistema/` |

Cada aula tem um explicavideo com o avatar do Nei (canal INEMA, lives7).

## O processo, do início ao fim

Legenda: 🧠 sessão com o Nei · ⚙️ script/timer · 🤖 `claude -p` / subagente

1. 🧠 Pedido do Nei + conteúdo de origem → fatos conferidos na documentação oficial (`longrun/2026-10-28-claude-gestor-agentes/FATOS.md` no repo wifi).
2. ⚙️ Criar o curso: `~/.claude/skills/formato-curso-v72/scripts/novo-curso.sh ~/projetos/claude-gestor-de-agentes-v72 "Claude como gestor de agentes"`.
3. 🤖 Escrever as aulas em `conteudo/pt/aulas/*.json` (um redator por par de aulas, só com fatos do FATOS.md).
4. 🤖 Imagens: capa e fotos de abertura pelo Codex (`codex exec`, image_gen na assinatura) → `assets/img/`.
5. ⚙️ Portão: `python3 gerar.py && python3 validar.py --links && node ~/.claude/skills/formato-curso-v72/scripts/conferir-tela.cjs .`
6. 🤖 Revisor independente (agente novo, persona do público) → corrigir → revisar de novo; notas em `~/projetos/wifi/scripts/revisor-nota.py`.
7. ⚙️ Publicar: commit + `gh repo create inematds/claude-gestor-de-agentes-v72 --public --source . --push` + GitHub Pages da raiz.
8. 🤖 Explicavideos: roteiro, visual e capa por aula (`~/projetos/output/claude-gestor-agentes-videos/cga-aN/`).
9. ⚙️ Avatar no estúdio HeyGen + render: `tools/lote.sh cga-aN …` (longrun) → `entrega/cga-aN.mp4`.
10. ⚙️ YouTube lives7 + bot v3 + inemaytbot: `tools/plano16.sh` (dry-run) → `tools/publica16.sh` (ou `tools/auto.sh`).
11. ⚙️ Vídeos no curso: release `video-v1.0.0` + `tools/embute.py` → `gerar.py` → push.
12. ⚙️ Portal: skill `atualiza-portal` (curso em `courses.ts` + trilha Agentes Jarvis + enrichment) e vídeos em `videoUpdatesData`.
13. 🧠 r7ex 9:16 da novidade: `~/projetos/r7ex/edicoes/2026-10-28-claude-gestor-agentes/` → `producao/producao.py --add` → fila do lives7.
14. 🧠 Telegram INEMA.CCODE (skill `postar-telegram`) + MENU.

## Mais no INEMA.CLUB
- [Ficha completa deste curso](https://www.inema.club/cursos/388-claude-como-gestor-de-agentes-saia-do-chat-e-coordene-uma-equipe-de-agentes/)
- [Guia: como aprender inteligência artificial](https://www.inema.club/aprender-inteligencia-artificial/)
- [Todos os cursos](https://www.inema.club/cursos/)

Conteúdo aberto e gratuito · formato INEMA Learning v7.2 · INEMA.CLUB
