# Changelog — EduConnect App

## [2.1.4] — 2024-03-15
### Fixed
- fix: correction injection SQL sur endpoint `/api/v1/search` (CVE interne EC-2024-003)
- fix: suppression debug mode actif en production (`APP_DEBUG=true` dans .env)
- fix: headers sécurité manquants (X-Frame-Options, CSP)

## [2.1.3] — 2024-02-01
### Fixed
- fix: path traversal sur `/documents/download.php?file=` — paramètre non sanitisé
- fix: IDOR sur `/portal/grades?student_id=` — manque de vérification d'autorisation
- chore: rotation clé JWT (ancienne clé: voir commit 6ea7915 .env)

## [2.1.0] — 2023-11-20
### Added
- feat: API v2 — migration de /api/v1 vers /api/v2 (v1 maintenu en parallèle jusqu'au 2024-06-01)
- feat: authentification JWT remplace les sessions PHP
### Deprecated
- `/api/v1/` — fin de support prévue 2024-06-01

## [2.0.5] — 2023-09-12
### Fixed
- fix: XSS stocké sur les champs de commentaire (non-échappement sortie HTML)
- fix: upload non restreint sur `/uploads/` — extension whitelist ajoutée

## [2.0.0] — 2023-06-01
### Changed
- Migration vers architecture microservices (MongoDB + Redis)
- Ajout du module `portal/` (accès VPN obligatoire)
