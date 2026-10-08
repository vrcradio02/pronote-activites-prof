# Pronote Activités Prof

Application web de gestion des activités pédagogiques pour un enseignant. Le projet est une interface HTML/JavaScript statique qui permet de :

- se connecter à l'espace professeur,
- créer des activités avec un nom et un lien,
- partager le lien avec les élèves,
- consulter les participations et les statistiques,
- modifier le mot de passe du compte enseignant,
- utiliser Supabase comme backend d’authentification et de stockage des données.

## Aperçu

Le dépôt contient une application mono-page (`index.html`) avec le style et la logique intégrées dans le même fichier. La configuration de connexion à Supabase est stockée dans `config.js`.

## Stack technique

- HTML5
- CSS3
- JavaScript vanilla
- Supabase JavaScript SDK

## Structure du projet

```text
.
├── config.js
├── index.html
└── README.md
```

- `index.html` : interface utilisateur, formulaires, logique d’authentification et gestion des activités.
- `config.js` : variables de connexion Supabase (`SUPABASE_URL` et `SUPABASE_KEY`).
- `README.md` : documentation du projet.

## Fonctionnalités principales

### 1. Authentification enseignant
- page de connexion dédiée,
- validation du nom d’utilisateur et du mot de passe,
- contrôle de session via Supabase,
- vérification que l’utilisateur connecté correspond bien au compte enseignant autorisé.

### 2. Création d’activités
- saisie du nom d’une activité,
- saisie d’un lien vers l’activité,
- enregistrement dans Supabase et affichage dans la liste du tableau de bord.

### 3. Gestion des liens
- affichage du lien généré,
- copie du lien dans le presse-papiers,
- partage possible avec les élèves ou les participants.

### 4. Statistiques de participation
- comptage des participations
- vue du nombre d’élèves anonymes et identifiés
- graphiques simples (barres de proportion)

### 5. Changement de mot de passe
- modal dédiée pour modifier le mot de passe de l’enseignant,
- validation de confirmation du mot de passe.

## Prérequis

- un navigateur moderne,
- un projet Supabase actif,
- les clés d’authentification de votre instance Supabase.

## Installation et lancement

1. Clonez le dépôt :

```bash
git clone https://github.com/vrcradio02/pronote-activites-prof.git
cd pronote-activites-prof
```

2. Configurez votre fichier `config.js` :

```javascript
const SUPABASE_URL = "https://votre-instance.supabase.co";
const SUPABASE_KEY = "votre-cle-publique-ou-anonyme";
```

3. Ouvrez le projet dans un navigateur, ou servez-le via un petit serveur statique si nécessaire :

```bash
python -m http.server 8000
```

Puis ouvrez :

```text
http://localhost:8000
```

## Remarques importantes

- Le projet est une application front-end statique ; il dépend fortement de Supabase pour les données et l’authentification.
- Les identifiants et l’email du compte enseignant sont codés dans `index.html` (par exemple `herr.lamari` et `herr.lamari@prof.pronote-activites.local`).
- Pour un usage réel en production, il est conseillé de :
  - ne pas stocker de secrets sensibles côté client,
  - sécuriser les accès Supabase,
  - remplacer les identifiants codés en dur par un système d’authentification plus robuste,
  - utiliser des règles de sécurité côté base de données.

## Contribution

Vous pouvez modifier la structure HTML/CSS/JS directement dans `index.html`, ou découper le code en fichiers séparés pour faciliter la maintenance.

## Licence

Aucune licence n’a été explicitement renseignée dans le dépôt. Vérifiez le repository pour confirmer le statut légal avant toute réutilisation commerciale ou publique.
