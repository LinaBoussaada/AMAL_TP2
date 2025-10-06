# AMAL_TP2
# Architecture API Gateway et Microservices Parallèles DeepSeek

## 📋 Vue d'ensemble

Ce document présente une analyse technique approfondie de l'architecture DeepSeek, en se concentrant sur deux aspects critiques :
1. **L'API Gateway** comme point d'entrée centralisé du système
2. **L'architecture microservices parallèle** pour le traitement distribué des requêtes IA

---

## 🔷Architecture Gateway API Standard

Avant d’aborder l’architecture API Gateway de DeepSeek, nous allons d’abord présenter l’architecture API Gateway standard.
<img width="818" height="500" alt="image" src="https://github.com/user-attachments/assets/94f3d8c9-16bd-43e7-8fdc-024625534003" />
Cette architecture illustre un schéma classique d’API Gateway, qui centralise les échanges entre clients (web, mobile, applications) et microservices (authentification, limitation du trafic, facturation, inférence, etc.). Les clusters de traitement (ex. GPU pour l’IA) et les composants comme le cache de réponse ou la base de connaissances optimisent performance et rapidité.
## 🔷Architecture Gateway API - Deepssek
<img width="1268" height="757" alt="DEEPSEEK ARCHI" src="https://github.com/user-attachments/assets/2d01c627-3b99-403e-ad81-a4ecaac49e15" />

### Composants principaux de la Gateway

#### 1. Couche d'entrée (Client Layer)
- **Clients multiples** : Web, Mobile, Applications tierces
- **Point d'accès unique** : Toutes les requêtes transitent par l'API Gateway
- **Protocoles supportés** : REST, WebSocket, gRPC

#### 2. API Gateway (Orchestrateur central)

L'API Gateway assure plusieurs fonctions critiques :

| Fonction | Description | Bénéfice |
|----------|-------------|----------|
| **Routage intelligent** | Redirection des requêtes vers les microservices appropriés | Séparation des responsabilités |
| **Authentification & Autorisation** | Vérification des tokens, gestion des permissions | Sécurité centralisée |
| **Rate Limiting** | Limitation du nombre de requêtes par utilisateur/API key | Protection contre les abus |
| **Load Balancing** | Distribution équitable de la charge | Optimisation des ressources |
| **Transformation de protocoles** | Adaptation des formats de requêtes/réponses | Compatibilité multi-clients |
| **Monitoring & Logging** | Collecte des métriques et traces | Observabilité du système |

🎯 Hiérarchie des titres en Markdown
markdown# Titre niveau 1 (le plus grand)
## Titre niveau 2
### Titre niveau 3
#### Titre niveau 4
##### Titre niveau 5
###### Titre niveau 6 (le plus petit)
Règle importante : TOUJOURS mettre un espace après les #

✅ # Titre → Fonctionne
❌ #Titre → Ne fonctionne pas (GitHub l'affiche comme texte normal)


🔧 Vérification rapide
Pour tester si vos titres fonctionnent dans votre fichier README.md actuel :

Ouvrez votre fichier
Cherchez tous les # en début de ligne
Vérifiez qu'il y a un espace après chaque série de #
Si non, ajoutez l'espace

Exemple de correction :
diff- #Architecture Gateway API Standard
+ # Architecture Gateway API Standard

- ##Les limites de l'architecture API Gateway
+ ## Les limites de l'architecture API Gateway

- ###Composants clés
+ ### Composants clés
Une fois corrigé, vos titres s'afficheront avec les bonnes tailles sur GitHub ! 🎉RéessayerClaude n'a pas encore la capacité d'exécuter le code qu'il génère.Claude peut faire des erreurs. Assurez-vous de vérifier ses réponses.

#Les limites de l’architecture API Gateway

Point unique de défaillance : une panne de la Gateway bloque tout le système.

Latence supplémentaire : chaque requête passe par une couche intermédiaire.

Complexité de gestion : configuration et maintenance plus lourdes.

Coût en ressources : consommation accrue de mémoire et CPU.

Risque de goulot d’étranglement : si la Gateway n’est pas bien dimensionnée.

#Remarque :
L’architecture présentée ci-dessus est une représentation conceptuelle inspirée des principes généralement utilisés par DeepSeek. Elle n’est pas officiellement confirmée par l’entreprise, mais illustre de manière plausible l’organisation d’un système basé sur une API Gateway.
De plus, plusieurs éléments du schéma (tels que Response Cache, Knowledge Base / RAG System ou Inference Router) sont cohérents avec ce type d’architecture, mais ne sont pas explicitement mentionnés dans la documentation publique disponible.

#Architecture Parallele
<img width="528" height="413" alt="image" src="https://github.com/user-attachments/assets/8e51db4b-6cb8-4aa0-8cb1-b72ec8daeddb" />


## Contributeurs

| Nom & Prénom |
|--------------|
| Lina Boussaada |
| Mariem Trabelsi | 

---

*Document technique sur l'architecture DeepSeek, maintenu par l'équipe système.*
