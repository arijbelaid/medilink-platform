# Architecture Microservices — MediLink

## 1. Découpage des Microservices
| Microservice | Responsabilités principales | Base de données |
|---|---|---|
| User Service | Authentification (JWT), gestion des rôles, profils. | PostgreSQL |
| Doctor Service | Profils professionnels, spécialités, horaires, prescriptions. | PostgreSQL |
| Appointment Service | Création, statuts, anti-double réservation, historique. | PostgreSQL |
| API Gateway | Point d'entrée unique, routage, vérification JWT. | N/A |
| Frontend | Interface utilisateur (Patient, Médecin, Admin). | N/A |

## 2. Communication
- Synchrone : REST / HTTP via l'API Gateway.
- Règle : Aucun service ne partage sa base de données.