# Rugby Data Centralization

## 1. Contexte et objectifs
Ce projet pédagogique vise à simuler la **migration et centralisation des données sportives d’un club de rugby** (serveur local → cloud Azure/AWS).  
Objectif : apprendre à gérer **pipelines, stockage cloud, traitement et visualisation** de données sportives.

> ⚠️ Aucune donnée réelle du club n’est utilisée. Toutes les données sont simulées ou anonymisées.

---

## 2. Sources et collecte des données
- **Types de données** : GPS, cardio, distance, vitesse, intensité, charge, données médicales, vidéos, ressenti joueur
- **Sources** :
  - Outils internes / applications développées par le club
  - Fournisseurs externes : Opta, Wyscout…
  - Applications cloud ou mobiles utilisées par les joueurs
- **Collecte et transfert** :
  - Import automatique via API ou synchronisation cloud
  - Export fichiers internes
  - Vidéos : transformation en clips analytiques, suppression des fichiers complets après traitement

> TODO : Ajouter fréquence réelle de collecte si reçue du club

---

## 3. Stockage et architecture
- **Stockage** :
  - Données brutes : `DataLake/Raw` ou serveur interne
  - Données transformées : `Blob Storage/Processed`, SQL pour analyse
- **Cheminement des données** : collecte → nettoyage → enrichissement → stockage final
- **Organisation pratique** :
  - Par joueur, session, type de match, poste, tags/métadonnées

> TODO : Ajouter capture schéma architecture Azure

---

## 4. Traitement et intégration
- **Outils/langages** : Python, SQL, DataBricks, Excel, Power BI
- **Centralisation vs cloisonnement** : certaines données restent cloisonnées, d’autres centralisées
- **Automatisation** :
  - Nettoyage et enrichissement automatisés pour GPS et stats
  - Intervention manuelle pour données médicales et métriques qualitatives
- **Indicateurs de performance** : calculés automatiquement quand possible, sinon complétés par le staff

> TODO : Ajouter exemples de scripts Python / DataBricks

---

## 5. Analyse et visualisation
- **Outil BI** : Power BI (ou Tableau)
- **Fréquence de mise à jour** : quotidienne ou après chaque match/séance
- **Principaux KPI** : distance, vitesse, intensité, charge, récupération, performance match, risque blessure

> TODO : Ajouter capture dashboard Power BI

---

## 6. Données vidéo
- **Stockage** : Cloud / Blob Storage
- **Granularité** : matchs complets pour traitement → clips analytiques
- **Organisation** : par joueur, session, type de match, adversaire
- **Annotations/Tags** : ajoutés manuellement ou automatiquement

> TODO : Ajouter exemple d’organisation de vidéos et tags

---

## 7. Structure du projet
- rugby-data-centralization/
- │
- ├── data/ # Données simulées (raw, processed)
- ├── notebooks/ # Notebooks Jupyter pour exploration et analyse
- ├── scripts/ # Scripts Python pour traitement et transformation
- ├── reports/ # Dashboards ou visualisations
- ├── README.md
- └── .gitignore

---

## 8. Suivi et roadmap
1. Simuler les données et pipelines cloud
2. Implémenter nettoyage et enrichissement (Python/DataBricks)
3. Créer tables SQL et dashboards Power BI
4. Ajouter documentation continue (captures, notebooks, scripts)
5. Ajouter pipelines automatisés pour GPS et stats, interventions manuelles pour données médicales

---

## 9. Git & .gitignore suggéré
Pour éviter de versionner des fichiers lourds ou temporaires, ajoute ce `.gitignore` :

Data files

*.csv
*.xlsx
*.xls
*.json

Notebooks checkpoints

.ipynb_checkpoints/

Videos

*.mp4
*.avi
*.mov

Python

pycache/
*.pyc

Environment

.env


---

## 10. TODO / Notes
- [ ] Ajouter réponses reçues du club
- [ ] Captures schémas architecture Azure
- [ ] Exemples de scripts de transformation
- [ ] Captures dashboard Power BI
- [ ] Organisation et tagging des vidéos
