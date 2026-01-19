# récit.sh MCP

Serveur MCP pour [récit.sh](https://récit.sh) — l'outil de user stories que tu n'as jamais besoin d'ouvrir.

## C'est quoi ?

récit.sh est un gestionnaire de user stories pensé pour les devs. Ce repo contient les prompts et la documentation pour utiliser récit.sh depuis ton IDE ou ton terminal via [MCP](https://modelcontextprotocol.io/).

## Connexion

### Claude Desktop

Ajoute dans `~/.config/claude/claude_desktop_config.json` :

```json
{
  "mcpServers": {
    "recit": {
      "url": "https://mcp.récit.sh/sse"
    }
  }
}
```

### Cursor

Settings → MCP → Add Server :

```json
{
  "mcpServers": {
    "recit": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.récit.sh/sse"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add recit https://mcp.récit.sh/sse
```

## Authentification

Au premier appel, tu seras redirigé vers récit.sh pour autoriser la connexion OAuth. Tes tokens sont stockés localement.

## Tools disponibles

| Tool | Description |
|------|-------------|
| `list_projects` | Liste tes projets |
| `list_stories` | Liste les stories d'un projet |
| `get_story` | Détails d'une story |
| `create_story` | Crée une nouvelle story |
| `update_story` | Met à jour une story |
| `update_story_status` | Change le statut |
| `list_tags` | Liste les tags d'un projet |
| `add_comment` | Ajoute un commentaire |

## Prompts

Le dossier [`/prompts`](./prompts) contient des instructions pour aider ton IA à mieux utiliser récit.sh :

- [`story-creation.md`](./prompts/story-creation.md) — Guide pour créer des stories complètes
- [`workflow.md`](./prompts/workflow.md) — Bonnes pratiques de workflow
- [`coding-integration.md`](./prompts/coding-integration.md) — Lier code et stories

Tu peux copier ces prompts dans tes instructions custom ou t'en inspirer.

## Exemples

```
> Liste mes stories en cours
> Crée une story "Ajouter le dark mode" dans le projet frontend
> Passe l'US-42 en review
> Commente l'US-15 "En attente du retour design"
```

## Liens

- [récit.sh](https://récit.sh) — App web
- [Documentation](https://récit.sh/docs) — Guide complet
- [Changelog](https://récit.sh/changelog) — Nouveautés

## Contribuer

Les prompts sont communautaires ! Si tu as des suggestions pour améliorer l'utilisation de récit.sh avec Claude, Cursor ou autre, ouvre une PR.

## Licence

MIT
