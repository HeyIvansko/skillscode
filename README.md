# skillscode

Dépôt de skills pour agents (Claude Code, Codex, Cursor, etc.), gérés avec la CLI `skills`.

## Ajouter un skill

```bash
npx skills add <owner>/<repo>
```

Exemple : `npx skills add Leonxlnx/taste-skill`

La commande :
- copie les skills dans `.agents/skills/<nom>/`
- crée un symlink `.claude/skills/<nom>` pour Claude Code
- enregistre source et hash dans `skills-lock.json`

Ensuite : `git add -A && git commit && git push`.

## Autres commandes

```bash
npx skills list            # skills installés
npx skills update          # mettre à jour depuis la source
npx skills remove <nom>    # supprimer un skill
```

## Sécurité

Un skill est du texte d'instructions que l'agent exécute avec ses permissions complètes.
Lis le `SKILL.md` de chaque skill avant de le merger. `skills-lock.json` fixe le hash
de chaque skill pour détecter toute modification en amont.
