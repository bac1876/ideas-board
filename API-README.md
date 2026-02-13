# Kanban Board API

## Service
- **URL:** `http://143.110.233.145:3200`
- **Location:** `/root/ideas-board-api/`
- **PM2 name:** `ideas-api`
- **Database:** `/root/ideas-board-api/kanban.db` (SQLite)

## API Key
```
60e2db09f605271f40acbe5ad44e13bf0efec6048988783202c348ea0e9fa2b8
```

## Board IDs
- `brian` — Brian's Ideas Board (index.html)
- `lisa` — Lisa's Board (lisa-kanban.html)

## Endpoints

### Public (no auth needed)
- `GET /api/boards/:boardId/cards` — all cards
- `GET /api/boards/:boardId/columns` — column config
- `GET /health` — health check

### Writes (need API key via `X-API-Key` header, or CORS from GitHub Pages)
- `POST /api/boards/:boardId/cards` — create card
- `PUT /api/boards/:boardId/cards/:cardId` — update card
- `DELETE /api/boards/:boardId/cards/:cardId` — delete card
- `PUT /api/boards/:boardId/columns` — replace columns
- `PUT /api/boards/:boardId/bulk` — replace all columns + cards

## Kosmo Usage Examples

### Add a card
```bash
curl -X POST http://143.110.233.145:3200/api/boards/brian/cards \
  -H "Content-Type: application/json" \
  -H "X-API-Key: 60e2db09f605271f40acbe5ad44e13bf0efec6048988783202c348ea0e9fa2b8" \
  -d '{"columnId":"ideas","title":"New Idea","description":"Details here","emoji":"💡","tags":["ai"]}'
```

### Move a card to a different column
```bash
curl -X PUT http://143.110.233.145:3200/api/boards/brian/cards/CARD_ID \
  -H "Content-Type: application/json" \
  -H "X-API-Key: 60e2db09f605271f40acbe5ad44e13bf0efec6048988783202c348ea0e9fa2b8" \
  -d '{"columnId":"building"}'
```

### Delete a card
```bash
curl -X DELETE http://143.110.233.145:3200/api/boards/brian/cards/CARD_ID \
  -H "X-API-Key: 60e2db09f605271f40acbe5ad44e13bf0efec6048988783202c348ea0e9fa2b8"
```

### Get all cards
```bash
curl http://143.110.233.145:3200/api/boards/brian/cards
```

## Card Schema
Cards from API have: `id, boardId, columnId, title, description, emoji, tags[], revenue, sections{}, position, createdAt, updatedAt`

The frontend maps `columnId` ↔ `column` and `description` ↔ `desc` for compatibility.

## How It Works
- Browser loads from API on page load, falls back to localStorage if offline
- Every save syncs to both API and localStorage (debounced 500ms)
- Green dot = connected, yellow = syncing, red = offline/localStorage mode
- Kosmo can CRUD cards via API key without touching git
