# Commerciale — Metodo Dale Carnegie

Strumenti per preparare le call con i prospect.

## Skill `prepara-prospect`

Dossier di pre-call (ricerca, domanda di apertura, domande As Is/Should Be/Change/Payout, obiezioni, follow-up) e cheat-sheet di una pagina.

- **In questo repository:** è già attiva (`.claude/skills/prepara-prospect`). Uso: `/prepara-prospect azienda, sito, referente…`.
- **Ovunque, come plugin:** in Claude Code esegui
  ```
  /plugin marketplace add PropagandaAdv/commerciale-dalecarnege
  /plugin install prepara-prospect@propaganda-commerciale
  ```
  Fuori da questo repository la skill cerca `agenzia.md` nella cartella di lavoro e poi in `~/.claude/agenzia.md`: copia lì il file.

## File

- `agenzia.md` — servizi, USP, casi studio e ICP dell'agenzia (letto dalla skill e dal morning brief).
- `plugins/prepara-prospect/` — il plugin con la skill e i riferimenti.
- `routine/morning-brief.md` — copia versionata del prompt del brief mattutino.
