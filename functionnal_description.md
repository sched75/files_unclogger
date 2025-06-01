# Spécification Fonctionnelle
## Système de Nettoyage Intelligent de Fichiers pour Windows

### 1. VISION PRODUIT

#### 1.1 Objectif Principal
Développer une application Windows de nettoyage et d'organisation de fichiers qui permet de ranger efficacement des arborescences complètes en combinant intelligence artificielle et contrôle utilisateur via une interface visuelle intuitive de type glisser-déposer.

#### 1.2 Proposition de Valeur
- **Interface visuelle unifiée** : Vue complète de l'arborescence avec attribution par glisser-déposer
- **Réévaluation intelligente** : L'IA réajuste automatiquement les attributions lors des modifications
- **Processus en 3 étapes** : Sélection → Attribution → Organisation
- **Contrôle total** : Visualisation et modification de chaque attribution avant exécution

### 2. PROCESSUS DE NETTOYAGE

#### 2.1 Étape 1 : Sélection de la Source
- **Sélection du répertoire racine** : Point de départ du nettoyage
- **Analyse préliminaire** : Comptage et catégorisation rapide
- **Options de filtrage** : Exclusion de certains types ou dossiers
- **Estimation** : Nombre de fichiers et volume à traiter

#### 2.2 Étape 2 : Interface d'Attribution
L'écran principal est divisé en deux zones :

**Zone Gauche - Arborescence des Fichiers**
```
Colonnes affichées :
│ Nom du fichier/dossier │ Topic │ Projet │ Template │ Destination │
├─ Documents/
│  ├─ Rapport_2024.docx   │ Compta │ -      │ An/Mois │ D:\Compta\2024\01\ │
│  └─ Brief_Nike.pptx     │ Client │ Nike   │ Projets │ E:\Clients\Nike\   │
└─ Images/
   └─ Logo_v2.png         │ Design │ Nike   │ Projets │ E:\Clients\Nike\   │
```

**Zone Droite - Panneaux d'Attribution**
- **Panneau Topics** : Liste hiérarchique des sujets disponibles
- **Panneau Projets** : Liste des projets actifs
- **Panneau Templates** : 8 templates de classement prédéfinis

#### 2.3 Étape 3 : Mécanisme d'Attribution par Glisser-Déposer

##### Fonctionnement
1. **Glisser** un topic/projet/template depuis le panneau droit
2. **Déposer** sur un fichier ou dossier dans l'arborescence
3. **Mise à jour immédiate** des colonnes d'attribution
4. **Réévaluation IA** : Tous les fichiers du répertoire modifié sont réanalysés

##### Comportement Intelligent
- **Attribution sur dossier** : Applique à tous les fichiers contenus
- **Héritage intelligent** : Les sous-dossiers héritent des attributions parentes
- **Suggestions contextuelles** : L'IA propose des attributions similaires
- **Apprentissage** : Chaque attribution manuelle améliore les futures suggestions

### 3. INTERFACE UTILISATEUR DÉTAILLÉE

#### 3.1 Écran Principal de Nettoyage
```
┌─────────────────────────────────────────────────────────────────────┐
│ [Sélectionner Source] [Analyser] [Prévisualiser] [Nettoyer]        │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  ARBORESCENCE (60%)                    ATTRIBUTION (40%)           │
│ ┌─────────────────────────────────┐  ┌───────────────────────────┐│
│ │ ☑ □ Nom        Topic  Projet... │  │ ▼ TOPICS                  ││
│ │ ▼ □ Documents                   │  │   ▼ Finance               ││
│ │   ☑ Facture... Compta  -       │  │     • Comptabilité        ││
│ │   ☑ Devis...   Client  Nike    │  │     • Budget              ││
│ │ ▶ □ Archives                    │  │   ▶ Clients               ││
│ │                                 │  │                           ││
│ │                                 │  │ ▼ PROJETS                 ││
│ │                                 │  │   • Nike 2024             ││
│ │                                 │  │   • Adidas Q1             ││
│ │                                 │  │                           ││
│ │                                 │  │ ▼ TEMPLATES               ││
│ │                                 │  │   • Année/Mois            ││
│ │                                 │  │   • Statut/Domaine/Projet ││
│ └─────────────────────────────────┘  └───────────────────────────┘│
│                                                                     │
│ Statut: 234 fichiers analysés | 12 à traiter | Prêt               │
└─────────────────────────────────────────────────────────────────────┘
```

#### 3.2 Fonctionnalités de l'Interface

##### Zone Arborescence
- **Cases à cocher** : Sélection/désélection pour le traitement
- **Colonnes informatives** : Attribution actuelle visible en permanence
- **Codes couleur** : 
  - Vert : Attribution validée
  - Orange : Suggestion IA à confirmer
  - Rouge : Attribution manquante
- **Icônes de statut** : Indication visuelle du type de fichier

##### Zone Attribution
- **Glisser-déposer multiple** : Sélection de plusieurs éléments
- **Recherche rapide** : Filtrage des topics/projets
- **Favoris** : Accès rapide aux éléments fréquents
- **Création à la volée** : Nouveau topic/projet sans quitter l'écran

#### 3.3 Interactions Avancées

##### Multi-sélection et Attribution en Masse
1. Sélectionner plusieurs fichiers (Ctrl+clic ou Shift+clic)
2. Glisser-déposer un topic/projet/template
3. Application à tous les fichiers sélectionnés
4. Réévaluation IA sur l'ensemble

##### Menu Contextuel (Clic Droit)
- Attribuer à → Sous-menu topics/projets
- Créer nouveau topic ici
- Exclure du nettoyage
- Propriétés détaillées

### 4. SYSTÈME DE RÉÉVALUATION INTELLIGENTE

#### 4.1 Déclencheurs de Réévaluation
- **Attribution manuelle** : Modification d'un fichier/dossier
- **Création de topic** : Nouveau sujet disponible
- **Modification de template** : Changement de règle d'organisation
- **Import de configuration** : Nouvelles règles appliquées

#### 4.2 Comportement de la Réévaluation
- **Périmètre intelligent** : Seuls les fichiers liés sont réévalués
- **Préservation des choix** : Les attributions manuelles sont prioritaires
- **Suggestions améliorées** : Basées sur les nouvelles attributions
- **Notification des changements** : Indication visuelle des modifications

### 5. TEMPLATES DE CLASSEMENT

#### 5.1 Les 8 Templates Prédéfinis

| Template | Structure | Usage Optimal |
|----------|-----------|---------------|
| **Année/Mois** | `/{année}/{mois}/` | Archives mensuelles simples |
| **Année/Semaine** | `/{année}/Semaine_{n}/` | Suivi hebdomadaire |
| **Année/Mois/Type** | `/{année}/{mois}/{type}/` | Archives avec catégorisation |
| **Année/Semaine/Type** | `/{année}/Semaine_{n}/{type}/` | Organisation hebdo détaillée |
| **Projets** | `/Projets/{nom_projet}/` | Gestion simple par projet |
| **Domaine/Projets** | `/{domaine}/{nom_projet}/` | Organisation par secteur |
| **Statut/Domaine/Projet** | `/{statut}/{domaine}/{projet}/` | Workflow avec états |
| **Statut/Domaine/Projet/Phase** | `/{statut}/{domaine}/{projet}/{phase}/` | Gestion complète |

#### 5.2 Application des Templates
- **Prévisualisation en temps réel** : La colonne "Destination" se met à jour
- **Combinaison flexible** : Topic + Template = Organisation personnalisée
- **Variables dynamiques** : Adaptation automatique aux métadonnées

### 6. CAS D'USAGE CONCRETS

#### 6.1 Nettoyage d'un Disque de Travail
**Situation** : Freelance avec 2 ans de fichiers en vrac

```
Processus :
1. Sélection de C:\Travail comme racine
2. L'IA identifie 3 clients principaux et suggère des topics
3. Glisser "Client/Nike" sur le dossier contenant "Nike"
4. L'IA réévalue et trouve tous les fichiers Nike éparpillés
5. Attribution du template "Domaine/Projets"
6. Résultat : Tous les fichiers Nike rangés dans D:\Clients\Nike\
```

#### 6.2 Réorganisation Département Comptabilité
**Situation** : Service comptable avec nouvelle politique de classement

```
Avant : Tout dans C:\Comptabilité sans structure
Après application :
- Topic "Comptabilité/Factures" + Template "Année/Mois"
  → D:\Finance\Factures\2024\01\
- Topic "Comptabilité/Rapports" + Template "Année/Semaine"
  → D:\Finance\Rapports\2024\Semaine_03\
- Topic "Comptabilité/Clients" + Template "Projets"
  → D:\Finance\Clients\[NomClient]\
```

#### 6.3 Migration Projet Terminé
**Situation** : Projet client terminé à archiver

```
1. Sélection du dossier projet E:\EnCours\ProjetX\
2. Glisser "Projet Archivé" sur le dossier racine
3. L'IA change automatiquement :
   - Statut : "En cours" → "Archivé"
   - Destination : E:\Archives\2024\ProjetX\
4. Validation et déplacement en un clic
```

### 7. FONCTIONNALITÉS AVANCÉES

#### 7.1 Modes de Vue
- **Vue Arborescence** : Navigation classique Windows
- **Vue Liste** : Tous les fichiers à plat avec filtres
- **Vue Kanban** : Colonnes par topic/projet
- **Vue Statistiques** : Graphiques de répartition

#### 7.2 Filtres et Recherche
- **Par état** : Non attribués, Suggérés, Validés
- **Par type** : Documents, Images, Code, Archives
- **Par date** : Récents, Anciens, Période spécifique
- **Par taille** : Volumineux, Standards, Petits

#### 7.3 Automatisation
- **Règles personnalisées** : "Si contient 'facture' alors Topic Comptabilité"
- **Surveillance de dossiers** : Nettoyage automatique des nouveaux fichiers
- **Planification** : Nettoyage hebdomadaire/mensuel
- **Profils** : Configurations sauvegardées par contexte

### 8. CONFIGURATION ET PERSONNALISATION

#### 8.1 Paramètres des Topics
- **Icône et couleur** : Identification visuelle rapide
- **Répertoire de base** : Destination par défaut
- **Template associé** : Organisation automatique
- **Règles d'attribution** : Critères automatiques

#### 8.2 Paramètres des Projets
- **Informations** : Client, dates, statut
- **Structure type** : Sous-dossiers à créer
- **Équipe** : Personnes associées
- **Archives** : Comportement fin de projet

#### 8.3 Préférences Utilisateur
- **Comportement glisser-déposer** : Copier/Déplacer
- **Confirmation** : Niveau de validation requis
- **Notifications** : Alertes et rapports
- **Raccourcis** : Personnalisation des touches

### 9. RAPPORTS ET SUIVI

#### 9.1 Tableau de Bord
- **Statistiques globales** : Fichiers traités, gain d'espace
- **Répartition** : Graphiques par topic/projet
- **Tendances** : Évolution du volume par catégorie
- **Performance** : Temps économisé

#### 9.2 Historique Détaillé
- **Journal des actions** : Qui, quoi, quand
- **Avant/Après** : Comparaison des structures
- **Annulation possible** : Retour arrière sécurisé
- **Export** : Rapports PDF/Excel

### 10. BÉNÉFICES MÉTIER

#### 10.1 Gains Mesurables
- **Temps** : 90% de réduction du temps de rangement
- **Espace** : 20% d'espace récupéré (doublons détectés)
- **Productivité** : Retrouvabilité immédiate des fichiers
- **Conformité** : Respect automatique des politiques

#### 10.2 Avantages Qualitatifs
- **Stress réduit** : Plus de fichiers perdus
- **Collaboration améliorée** : Structure partagée claire
- **Évolutivité** : S'adapte à la croissance
- **Professionnalisme** : Organisation irréprochable

### 11. CONCLUSION

Ce système de nettoyage intelligent transforme la corvée du rangement de fichiers en processus visuel et intuitif. L'interface unifiée avec glisser-déposer, combinée à l'intelligence artificielle qui réévalue continuellement les attributions, offre le parfait équilibre entre automatisation et contrôle utilisateur.

La visualisation complète de l'arborescence avec les attributions en colonnes permet de comprendre instantanément l'organisation future, tandis que la réévaluation intelligente garantit une cohérence parfaite même lors de modifications manuelles.

---

*Document version 3.0 - Spécification Fonctionnelle - Juin 2025*
