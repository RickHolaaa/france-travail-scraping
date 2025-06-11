# HrFlow - Test Technique : Job Crawler

Ce projet a été réalisé dans le cadre d'un **test technique pour l'entreprise HrFlow**.

L'objectif est de concevoir un crawler capable de scraper des offres d'emploi depuis la plateforme **France Travail (anciennement Pôle Emploi)** et de les injecter automatiquement dans une board HrFlow via leur API.

## 📄 Description

Le projet est structuré sous forme de notebook Jupyter :  
- `crawler.ipynb`

Le script réalise les étapes suivantes :

1. **Connexion API HrFlow**
   - Utilisation du SDK HrFlow pour interagir avec l'API de stockage des offres.
   - Chargement des clés API via un fichier `.env` local.

2. **Scraping dynamique avec Selenium**
   - Ouverture automatique du site France Travail.
   - Parcours des différentes catégories d'offres.
   - Extraction des informations complètes des annonces :
     - Titre, description, responsabilités, exigences, compétences, entreprise, type de contrat, horaires, salaire, etc.

3. **Géocodage avec Geopy**
   - Récupération des coordonnées géographiques des adresses extraites.

4. **Injection dans HrFlow**
   - Transformation des données en JSON formaté selon les spécifications HrFlow.
   - Upload des offres dans un board HrFlow via `job.storing.add_json()`.

## 🔧 Technologies utilisées

- Python 3.x
- Jupyter Notebook
- HrFlow Python SDK (`hrflow`)
- Selenium
- Geopy
- Dotenv
