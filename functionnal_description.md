# Spécification Fonctionnelle
## Système d'Organisation Intelligente de Fichiers pour Windows

### 1. VISION PRODUIT

#### 1.1 Objectif Principal
Développer une application Windows autonome qui automatise l'organisation des fichiers en combinant intelligence artificielle, règles métier prédéfinies et personnalisation utilisateur pour réduire de 90% le temps de classement manuel.

#### 1.2 Proposition de Valeur
- **Automatisation intelligente** : Classification IA basée sur le contenu et le contexte
- **Flexibilité maximale** : 8 templates d'organisation adaptés à tous les besoins
- **Personnalisation avancée** : Création de topics et projets personnalisés
- **Apprentissage continu** : Le système s'améliore avec chaque utilisation
- **Organisation hybride** : Association flexible entre topics, projets et templates

### 2. FONCTIONNALITÉS PRINCIPALES

#### 2.1 Module de Scan Intelligent

##### Modes de Parcours
| Mode | Description | Cas d'usage |
|------|-------------|-------------|
| **Superficiel** | Analyse uniquement le dossier racine | Tri rapide de téléchargements |
| **Récursif** | Parcours complet de l'arborescence | Organisation complète d'archives |
| **Projets** | Détection et groupement de fichiers liés | Gestion de projets complexes |

##### Filtres et Exclusions
- **Exclusions automatiques** : node_modules, .git (intégrité préservée), __pycache__
- **Filtres personnalisables** : 
  - Taille maximale (défaut: 1GB)
  - Extensions à ignorer (.tmp, .cache, .log)
  - Dossiers système

##### Capacités de Détection
- Métadonnées et formats de fichiers
- Signatures de projets (package.json, .git, requirements.txt)
- Mots-clés contextuels (client, version, rapport, final)
- Relations temporelles entre fichiers

#### 2.2 Moteur d'Intelligence Artificielle

##### Architecture IA Multi-Couches
1. **Analyse Sémantique (NLP)**
   - Modèle : Sentence Transformers (all-MiniLM-L6-v2)
   - Fonction : Classification par analyse des noms de fichiers
   - Précision : 85-95% selon le type de fichier

2. **Reconnaissance de Contenu**
   - OCR pour documents scannés (Tesseract)
   - Analyse d'images pour classification visuelle
   - Extraction de métadonnées avancées

3. **Apprentissage Adaptatif**
   - Enregistrement des corrections utilisateur
   - Amélioration continue des prédictions
   - Personnalisation par profil d'usage

##### Fonctions de Classification
- **Détection de domaine** : Finance, RH, Marketing, IT, etc.
- **Statut de projet** : En cours, Terminé, Archivé, Récurrent
- **Phase de projet** : Préparation, Documentation, Faisabilité, Code
- **Score de confiance** : Indicateur de fiabilité (0-100%)

#### 2.3 Templates d'Organisation (8 Modèles)

| # | Template | Structure | Usage Recommandé |
|---|----------|-----------|------------------|
| 1 | **Année/Mois** | `/{année}/{mois}/` | Archives mensuelles simples |
| 2 | **Année/Semaine** | `/{année}/Semaine_{n}/` | Suivi hebdomadaire |
| 3 | **Année/Mois/Type** | `/{année}/{mois}/{type}/` | Archives détaillées par type |
| 4 | **Année/Semaine/Type** | `/{année}/Semaine_{n}/{type}/` | Organisation hebdo par type |
| 5 | **Projets** | `/Projets/{nom_projet}/` | Gestion de projets simple |
| 6 | **Domaine/Projets** | `/{domaine}/{nom_projet}/` | Classification par domaine métier |
| 7 | **Statut/Domaine/Projet** | `/{statut}/{domaine}/{projet}/` | Gestion avancée avec statut |
| 8 | **Statut/Domaine/Projet/Phase** | `/{statut}/{domaine}/{projet}/{phase}/` | Workflow complet de projet |

#### 2.4 Gestion des Topics et Projets

##### Système de Topics Personnalisés
- **Définition de topics** : L'utilisateur peut créer une hiérarchie de sujets
  - Exemple : Comptabilité > Point Cash
  - Exemple : Marketing > Campagnes > 2024
  - Exemple : RH > Recrutement > Candidatures
  
- **Association topic-template** : Chaque topic peut avoir son propre mode d'organisation
  - Topic "Comptabilité/Point Cash" → Template "Année/Mois"
  - Topic "Marketing/Campagnes" → Template "Domaine/Projets"
  - Topic "RH/Contrats" → Template "Année/Type"

- **Attribution manuelle** : L'utilisateur peut à tout moment :
  - Assigner un fichier à un topic spécifique
  - Modifier l'association fichier-topic suggérée par l'IA
  - Créer de nouveaux topics à la volée

##### Gestion des Projets
- **Liste de projets personnalisée** : Création et gestion comme les topics
- **Hiérarchie flexible** : Projets principaux et sous-projets
- **Statuts personnalisables** : Au-delà des 4 statuts par défaut

##### Configuration des Répertoires Racine
- **Par topic** : Chaque topic peut avoir son répertoire de base
  - Comptabilité → D:\Documents\Finance\
  - Marketing → E:\Projets\Marketing\
  - RH → D:\Confidentiel\RH\

- **Par projet** : Répertoires dédiés par projet
  - Projet ClientA → F:\Clients\ClientA\
  - Projet Interne → D:\Projets\Internes\

- **Héritage intelligent** : Les sous-topics/sous-projets héritent du répertoire parent sauf configuration contraire

#### 2.5 Interface Utilisateur

##### Interface Graphique
- **Tableau de bord principal**
  - Vue d'ensemble des fichiers à organiser
  - Statistiques en temps réel
  - Barre de progression détaillée

- **Onglets fonctionnels**
  1. **Fichiers détectés** : Liste avec classification IA et attribution manuelle
  2. **Topics** : Création, édition et gestion des sujets
  3. **Projets** : Gestion et association de fichiers
  4. **Organisation** : Configuration et aperçu
  5. **Historique** : Journal des actions avec annulation

- **Panneau d'attribution rapide**
  - Menu contextuel sur chaque fichier
  - Attribution à un topic ou projet en 2 clics
  - Suggestion de topics basée sur l'historique

##### Workflow d'Attribution
```
1. Scan des fichiers → 2. Suggestions IA (topics/projets)
         ↓                          ↓
3. Validation/Modification → 4. Attribution manuelle possible
         ↓
5. Application du template associé → 6. Organisation
```

### 3. CARACTÉRISTIQUES FONCTIONNELLES

#### 3.1 Gestion Avancée des Topics

##### Création et Organisation
- **Interface de gestion dédiée** : Arborescence visuelle des topics
- **Hiérarchie illimitée** : Topics principaux et sous-topics
- **Icônes et couleurs** : Personnalisation visuelle pour identification rapide
- **Import/Export** : Partage de configurations entre utilisateurs

##### Exemples de Hiérarchies Topics
```
Finance/
├── Comptabilité/
│   ├── Point Cash
│   ├── Bilans Mensuels
│   └── Factures Fournisseurs
├── Budget/
│   ├── Prévisionnel
│   └── Réalisé
└── Investissements/

Clients/
├── Grands Comptes/
│   ├── ClientA
│   └── ClientB
└── PME/
    ├── Secteur Tech
    └── Secteur Service
```

##### Association Topic-Template-Répertoire
| Topic | Template Associé | Répertoire Racine |
|-------|-----------------|-------------------|
| Comptabilité/Point Cash | Année/Mois | D:\Finance\Comptabilité\ |
| Marketing/Campagnes | Domaine/Projets | E:\Marketing\Campagnes\ |
| RH/Contrats | Année/Type | D:\RH\Documentation\ |
| Clients/Grands Comptes | Statut/Domaine/Projet | F:\Clients\Premium\ |

#### 3.2 Système d'Attribution Intelligent

##### Attribution Manuelle
- **Glisser-déposer** : Vers un topic ou projet dans l'interface
- **Menu contextuel** : Clic droit → "Attribuer à..."
- **Raccourcis clavier** : Attribution rapide aux topics favoris
- **Multi-sélection** : Attribution en masse de fichiers similaires

##### Attribution Assistée par IA
- **Suggestions contextuelles** : Basées sur le nom et le contenu
- **Apprentissage** : Mémorisation des attributions manuelles
- **Règles personnalisées** : Création de règles d'attribution automatique
- **Score de confiance** : Indication de la pertinence de la suggestion

#### 3.3 Configuration des Répertoires

##### Paramètres par Topic
- **Répertoire principal** : Base d'organisation pour le topic
- **Sous-répertoires automatiques** : Création selon le template
- **Permissions** : Gestion des accès si nécessaire
- **Règles de nommage** : Personnalisation des conventions

##### Paramètres par Projet
- **Répertoire dédié** : Isolation complète du projet
- **Structure type** : Modèle de sous-dossiers à créer
- **Archivage** : Règles de déplacement pour projets terminés
- **Synchronisation** : Options de backup automatique

### 4. CAS D'USAGE DÉTAILLÉS

#### 4.1 Organisation Comptable avec Topics
**Contexte** : Service comptabilité avec multiples types de documents
```
Scénario :
1. Détection du fichier "Rapport_Tresorerie_Janvier_2024.xlsx"
2. L'utilisateur l'attribue au topic "Comptabilité/Point Cash"
3. Template associé automatiquement : "Année/Mois"
4. Répertoire racine du topic : "D:\Finance\Comptabilité\Point_Cash\"
5. Organisation finale : "D:\Finance\Comptabilité\Point_Cash\2024\01\Rapport_Tresorerie_Janvier_2024.xlsx"

Fichiers similaires traités automatiquement :
- Balance_Janvier_2024.xlsx → Même organisation
- Rapprochement_Bancaire_Jan24.pdf → Même organisation
```

#### 4.2 Gestion Multi-Projets avec Topics
**Contexte** : Agence créative avec clients variés
```
Configuration initiale :
- Topic "Clients/Grands Comptes/Nike" → Template "Statut/Domaine/Projet"
- Topic "Clients/PME/StartupX" → Template "Projets"
- Répertoires distincts pour chaque niveau

Attribution en pratique :
1. Brief_Nike_2024.docx → Topic "Clients/Grands Comptes/Nike"
   Résultat : F:\Clients\Premium\En_cours\Marketing\Nike\Brief_Nike_2024.docx

2. Devis_StartupX.xlsx → Topic "Clients/PME/StartupX"
   Résultat : F:\Clients\PME\Projets\StartupX\Devis_StartupX.xlsx
```

#### 4.3 Workflow Hybride Topics et Projets
**Contexte** : Département RH avec recrutement en cours
```
Configuration :
- Topic "RH/Recrutement" avec template "Année/Type"
- Projet "Recrutement_2024_Dev" rattaché au topic

Traitement :
1. CV candidats → Attribution au projet spécifique
2. Procédures RH → Attribution au topic général
3. Organisation cohérente mais séparée des deux flux

Résultats :
- D:\RH\Projets\Recrutement_2024_Dev\CV\[fichiers CV]
- D:\RH\Documentation\2024\Procédures\[fichiers procédures]
```

#### 4.4 Migration de Structure Existante
**Contexte** : Entreprise souhaitant réorganiser 5 ans d'archives
```
Approche :
1. Création de la hiérarchie de topics correspondant à l'organisation souhaitée
2. Scan des archives existantes
3. Attribution semi-automatique avec validation utilisateur
4. Réorganisation progressive par lots

Exemple de mapping :
- Ancien : "Divers\Compta\2023\fichier.xlsx"
- Détection IA : Fichier comptable
- Suggestion : Topic "Finance/Comptabilité/Archives"
- Nouveau : "D:\Finance\Comptabilité\Archives\2023\01\fichier.xlsx"
```

### 5. FONCTIONNALITÉS AVANCÉES

#### 5.1 Gestion des Topics Favoris
- **Topics épinglés** : Accès rapide aux plus utilisés
- **Historique d'utilisation** : Suggestions basées sur la fréquence
- **Topics récents** : Liste des 10 derniers utilisés
- **Recherche rapide** : Filtrage instantané dans la liste

#### 5.2 Règles d'Attribution Automatique
- **Par mots-clés** : "facture" → Topic "Comptabilité/Factures"
- **Par expéditeur** : Emails de fournisseurX → Topic correspondant
- **Par date** : Documents anciens → Topics d'archives
- **Par taille** : Gros fichiers → Topics médias/archives

#### 5.3 Modèles de Configuration
- **Templates de topics** : Structures prédéfinies par secteur
  - Pack Entreprise : Finance, RH, Commercial, Production
  - Pack Créatif : Projets, Clients, Ressources, Archives
  - Pack Personnel : Photos, Documents, Finances, Loisirs
- **Personnalisation** : Adaptation des modèles aux besoins
- **Partage** : Export/import entre utilisateurs ou postes

#### 5.4 Tableau de Bord Topics
- **Vue d'ensemble** : Nombre de fichiers par topic
- **Activité récente** : Dernières attributions
- **Espace utilisé** : Répartition du stockage
- **Suggestions** : Topics peu utilisés à réviser

### 6. BÉNÉFICES UTILISATEUR

#### 6.1 Gains de Productivité
- **Organisation personnalisée** : Adaptation parfaite au métier
- **Flexibilité totale** : Topics et templates combinables
- **Cohérence garantie** : Même logique pour tous les fichiers
- **Retrouvabilité optimale** : Structure claire et logique

#### 6.2 Avantages Organisationnels
- **Standardisation** : Mêmes topics pour toute l'équipe
- **Scalabilité** : Ajout facile de nouveaux topics/projets
- **Traçabilité** : Historique complet des attributions
- **Conformité** : Respect des politiques de classement

### 7. INTERFACE ET EXPÉRIENCE UTILISATEUR

#### 7.1 Écran de Gestion des Topics
```
[Barre d'outils : Nouveau Topic | Nouveau Sous-topic | Supprimer | Paramètres]

Arborescence des Topics          |  Détails du Topic Sélectionné
--------------------------------|--------------------------------
▼ Finance                       |  Nom : Comptabilité/Point Cash
  ▼ Comptabilité               |  Template : Année/Mois
    • Point Cash ←             |  Répertoire : D:\Finance\Compta\
    • Bilans Mensuels          |  Créé le : 01/01/2024
    • Factures                 |  Fichiers : 234
  ▶ Budget                     |  Dernier accès : Aujourd'hui
▶ Clients                      |  
▶ RH                          |  [Modifier] [Statistiques]
```

#### 7.2 Interface d'Attribution
- **Vue liste enrichie** : Aperçu fichier + topic suggéré
- **Mode kanban** : Glisser-déposer vers colonnes topics
- **Attribution rapide** : Touches 1-9 pour topics favoris
- **Prévisualisation** : Voir où le fichier sera organisé

#### 7.3 Workflow Type
1. **Import** : Sélection du dossier source
2. **Analyse** : Scan et suggestions IA
3. **Révision** : Validation/modification des attributions
4. **Configuration** : Vérification des répertoires cibles
5. **Exécution** : Organisation avec rapport détaillé

### 8. CONFIGURATION ET PERSONNALISATION

#### 8.1 Paramètres Globaux
- **Comportement par défaut** : Topic pour fichiers non attribués
- **Création automatique** : Nouveaux topics depuis l'IA
- **Notifications** : Alertes pour actions importantes
- **Langue** : Interface multilingue

#### 8.2 Personnalisation par Utilisateur
- **Profils** : Configuration par type d'utilisateur
- **Raccourcis** : Personnalisation des touches rapides
- **Affichage** : Choix des colonnes et informations
- **Filtres** : Critères d'affichage personnalisés

### 9. SCÉNARIOS D'UTILISATION AVANCÉS

#### 9.1 Entreprise Multi-Services
```
Configuration :
- 50 topics organisés par département
- 200 projets actifs
- 10 utilisateurs avec profils différents

Utilisation :
- Chaque service a ses topics avec templates adaptés
- Répertoires racine sur différents serveurs
- Règles d'attribution par département
```

#### 9.2 Freelance Multi-Clients
```
Organisation :
- 1 topic principal par client
- Sous-topics par type de livrable
- Templates différents selon la mission
- Archives automatiques après facturation
```

#### 9.3 Usage Personnel Avancé
```
Structure :
- Topics pour vie privée/professionnelle
- Projets pour événements (vacances, déménagement)
- Templates adaptés (photos par date, documents par type)
- Synchronisation avec cloud personnel
```

### 10. CONCLUSION

Ce système d'organisation intelligente représente une solution complète et flexible pour la gestion des fichiers Windows. La combinaison unique de topics personnalisables, de templates d'organisation variés et d'intelligence artificielle offre une expérience utilisateur sans précédent. 

La possibilité d'attribuer manuellement chaque fichier à un topic spécifique, tout en bénéficiant de suggestions intelligentes, garantit une organisation parfaitement adaptée aux besoins de chaque utilisateur. L'association flexible entre topics, templates et répertoires racine permet de créer un système de classement véritablement sur mesure.

Que ce soit pour un usage personnel, professionnel ou en entreprise, cette solution transforme la corvée du classement de fichiers en un processus simple, rapide et intelligent.

---

*Document version 2.1 - Spécification Fonctionnelle - Juin 2025*
