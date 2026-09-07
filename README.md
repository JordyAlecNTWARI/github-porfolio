# Jordy Alec — Portfolio Développeur

Développeur full-stack junior spécialisé TypeScript, PHP/Symfony et React. Après un BTS SIO (SLAM) et un stage en fintech, je suis en Bachelor Développement Full-Stack à l'EPSI Nantes et je recherche une alternance.

Portfolio en ligne : [jordyalecntwari.github.io/github-portfolio](https://jordyalecntwari.github.io/github-portfolio/)

---

## A propos

Développeur passionné par le développement logiciel, l'architecture applicative et les expériences web immersives. Ce portfolio regroupe mes projets réalisés en stage, en formation et en personnel.

---

## Projets

### Reservation-app — Réservation de créneaux temps réel (Stage Gauss&Co 2026)

Application de réservation de créneaux pensée pour la cohérence des données et la résilience. La réponse à l'utilisateur est instantanée : la génération du PDF de confirmation et l'envoi de l'email se font en arrière-plan via une file de messages.

**Stack technique :**
- Node.js + Express (TypeScript) — API REST
- PostgreSQL + Prisma 7 — persistance et intégrité des données
- Redis — cache de recherche (30 s) et rate limiting par IP
- RabbitMQ — traitement asynchrone (PDF + email), avec retry et dead letter
- Nodemailer — email de confirmation avec PDF en pièce jointe
- React + Vite — interface
- Vitest — tests d'intégration

**Réalisations :**
- Unicité des réservations garantie même en requêtes simultanées (contrainte PostgreSQL, prouvée par un test de concurrence)
- Réponse `201` immédiate, découplée du worker (le PDF et l'email ne bloquent pas l'utilisateur)
- Cache Redis avec invalidation automatique après réservation
- Rate limiting fail-open (l'API reste disponible si Redis tombe)
- File de nouvelle tentative + dead letter pour les échecs d'envoi
- 6 fichiers de tests d'intégration sur la vraie stack (API + base + Redis)

Repo privé (code confidentiel entreprise)

---

### Taskflow — Gestion de tâches kanban temps réel (Stage Gauss&Co 2026)

Application de gestion de tâches en kanban (Todo / Doing / Done) avec mise à jour en temps réel : une action d'un utilisateur (créer, déplacer, supprimer) est répercutée en direct chez les autres, sans recharger la page. Monorepo : une API Node/Express et un client React qui la consomme.

**Stack technique :**
- Node.js + Express (TypeScript) — API REST en couches (routes → controllers → services → repositories)
- React + Vite (TypeScript) — interface et routing (React Router)
- Socket.IO (WebSocket) — mises à jour temps réel
- JWT + bcrypt — authentification et hachage des mots de passe
- Postman — tests d'API (cas nominaux et cas d'erreur)

**Réalisations :**
- Authentification de bout en bout : inscription (bcrypt), connexion (JWT), middleware de protection des routes
- CRUD des tâches protégé par token (lister, créer, déplacer, supprimer)
- Temps réel via Socket.IO : le serveur émet `tasksUpdated`, le client recharge à la volée
- Gestion de session côté front : token en `localStorage`, gardes `ProtectedRoute` / `GuestRoute`
- Endpoints testés sous Postman avec les cas d'échec (titre vide → 400, sans token → 401, id inexistant → 404)

Repo privé (code confidentiel entreprise)

---

### KYC Module — cbkl-labs (Stage 2026)

Module KYC (Know Your Customer) développé lors de mon stage chez CUBIKL S.A.S à Paris.

**Stack technique :**
- TypeScript, Bun, Hono
- NX Monorepo (`@cbkl/kyc`, `@cbkl/common`)
- Clean Architecture (Domain / Application / Infrastructure / Adapters)

**Réalisations :**
- Structuration d'un monorepo NX en packages indépendants
- API REST avec pipeline OCR pour vérification de documents d'identité
- Entités métier : `KycRequest`, `OcrData`, `ScoringResult`
- Moteur de scoring automatique sur les demandes KYC
- Workflow Git professionnel : branches `feature/`, commits conventionnels, PRs avec review

Repo privé (code confidentiel entreprise)

---

### MediaTek86 (Projet scolaire BTS SIO)

Application web de gestion de médiathèque développée dans le cadre de la formation BTS SIO.

**Stack technique :**
- PHP / Symfony (API REST backend)
- HTML, CSS, JavaScript (frontend)
- MySQL

**Fonctionnalités :**
- Catalogue de livres avec statut de disponibilité
- Ajout, emprunt et retour de livres
- Interface de démonstration avec données simulées

Voir la démo : [jordyalecntwari.github.io/github-portfolio/mediatek](https://jordyalecntwari.github.io/github-portfolio/mediatek/)

Voir le repo : [github.com/JordyAlecNTWARI/Mediatek86](https://github.com/JordyAlecNTWARI/Mediatek86)

---

## Compétences

| Domaine | Technologies |
|---|---|
| Langages | TypeScript, JavaScript, PHP, Python, C# |
| Frontend | React 18, HTML / CSS, Vite |
| Backend | Node.js / Express, Symfony 7, Bun, Hono, API REST, JWT |
| Temps réel | Socket.IO, WebSocket |
| Files / Cache | Redis, RabbitMQ |
| Architecture | Clean Architecture, SOLID, POO, MVC |
| Base de données | PostgreSQL, Prisma, MySQL, Doctrine ORM |
| Tests | Vitest, PHPUnit, Postman |
| Outils | NX Monorepo, Git, GitHub, WebStorm, SonarLint |
| CI/CD | GitHub Actions |

---

## Contact

- [jordyalecntwari@gmail.com](mailto:jordyalecntwari@gmail.com)
- [jordyalec00@gmail.com](mailto:jordyalec00@gmail.com)
- [github.com/JordyAlecNTWARI](https://github.com/JordyAlecNTWARI)
