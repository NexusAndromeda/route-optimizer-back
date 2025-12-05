# Backend - Route Optimizer

Backend en Rust pour gérer les sessions de livraison, la synchronisation offline et l'optimisation de routes.

## Ce que ça fait

- API REST pour le frontend
- Authentification avec Colis Privé
- Synchronisation des données offline/online
- Optimisation de routes avec Mapbox
- Base de données PostgreSQL avec PostGIS

## Stack

- **Rust** avec Axum (framework web)
- **PostgreSQL** + PostGIS (pour les coordonnées)
- **Redis** (cache des sessions)

## Commandes

```bash
# Développement
cargo run

# Build pour production
cargo build --release

# Tests
cargo test

# Linting
cargo clippy
```

## Structure

```
backend/
├── src/
│   ├── main.rs              # Point d'entrée
│   ├── controllers/        # Endpoints HTTP
│   ├── services/           # Logique métier
│   ├── repositories/       # Accès à la BD
│   ├── models/             # Structs et DTOs
│   └── routes/             # Définition des routes
└── scheme.sql              # Schéma de BD
```

## Endpoints principaux

- `POST /api/v1/sessions` - Créer une session
- `GET /api/v1/sessions/{id}` - Obtenir une session
- `POST /api/v1/sessions/{id}/sync` - Synchroniser les changements
- `POST /api/v1/sessions/{id}/optimize` - Optimiser la route
- `GET /health` - Health check

## Notes

- Architecture MVC stricte : Controllers → Services → Repositories
- Les controllers valident juste et appellent les services
- Les services contiennent la logique métier
- Les repositories font juste des queries à la BD

## État du projet

⚠️ En développement - tout n'est pas encore implémenté
