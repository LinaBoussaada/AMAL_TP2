# AMAL_TP2
# Architecture API Gateway et Microservices Parallèles DeepSeek

## 📋 Vue d'ensemble

Ce document présente une analyse technique approfondie de l'architecture DeepSeek, en se concentrant sur deux aspects critiques :
1. **L'API Gateway** comme point d'entrée centralisé du système
2. **L'architecture microservices parallèle** pour le traitement distribué des requêtes IA

---

## 🔷Architecture Gateway API Standard

Avant d’aborder l’architecture API Gateway de DeepSeek, nous allons d’abord présenter l’architecture API Gateway standard.
<img width="528" height="413" alt="image" src="https://github.com/user-attachments/assets/8e51db4b-6cb8-4aa0-8cb1-b72ec8daeddb" />
Cette architecture illustre un schéma classique d’API Gateway, qui centralise les échanges entre clients (web, mobile, applications) et microservices (authentification, limitation du trafic, facturation, inférence, etc.). Les clusters de traitement (ex. GPU pour l’IA) et les composants comme le cache de réponse ou la base de connaissances optimisent performance et rapidité.

## 🔷Architecture Gateway API - Deepssek
<img width="542" height="319" alt="image" src="https://github.com/user-attachments/assets/28599b83-b11b-4aec-8b46-380e03966433" />

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

### 🎯 Les limites de l’architecture API Gateway

❌ Point unique de défaillance : une panne de la Gateway bloque tout le système.

❌ Latence supplémentaire : chaque requête passe par une couche intermédiaire.

❌ Complexité de gestion : configuration et maintenance plus lourdes.

❌ Coût en ressources : consommation accrue de mémoire et CPU.

❌ Risque de goulot d’étranglement : si la Gateway n’est pas bien dimensionnée.

### ⚠️ Note importante
Cette architecture représente une modélisation conceptuelle basée sur les meilleures pratiques du domaine et les patterns architecturaux observés dans les systèmes d'IA à grande échelle. 
Mais apres notre discussion avec Chatgpt et Claude on a trouvé qu'elle n'a pas été officiellement confirmée par DeepSeek, mais illustre une approche plausible et optimisée pour ce type de plateforme.

🏗️ Architecture Parallèle
Notre système repose sur une architecture parallèle conçue pour assurer une haute disponibilité et une scalabilité optimale.

https://github.com/user-attachments/assets/8e51db4b-6cb8-4aa0-8cb1-b72ec8daeddb

🛡️ Mécanisme de Fallback Intelligent
Le système de fallback Alibaba Cloud assure une surveillance en temps réel avec les seuils suivants :

🔍 Métriques de Surveillance :

Charge CPU : Seuil d'alerte à 80%

Utilisation mémoire : Limite à 85% de la capacité totale

Temps de réponse : Alerte si > 2 secondes

Taux d'erreur : Basculement automatique si > 5%

⚡ Mécanisme de Basculement Automatique
https://github.com/user-attachments/assets/28599b83-b11b-4aec-8b46-380e03966433

✨ Avantages de l'Architecture Parallèle
🔄 Haute Disponibilité

Redondance complète de tous les services critiques

⚡ Performance Optimisée

Allocation dédiée de processeurs par service

Répartition intelligente de la charge

📈 Scalabilité Horizontale

Ajout transparent de nouveaux serveurs

Extension flexible selon la demande

🛡️ Résilience

Basculement automatique en cas de défaillance

Continuité de service assurée

🔧 Maintenance Sans Interruption

Mise à jour alternée des serveurs

Aucun impact sur la disponibilité

👥 Contributeurs
Nom & Prénom
Lina Boussaada
Mariem Trabelsi
Document technique sur l'architecture DeepSeek, maintenu par l'équipe système.

