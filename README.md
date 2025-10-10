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

### 🎯 Les limites de l’architecture API Gateway

❌ Point unique de défaillance : une panne de la Gateway bloque tout le système.

❌ Latence supplémentaire : chaque requête passe par une couche intermédiaire.

❌ Complexité de gestion : configuration et maintenance plus lourdes.

❌ Coût en ressources : consommation accrue de mémoire et CPU.

❌ Risque de goulot d’étranglement : si la Gateway n’est pas bien dimensionnée.

### ⚠️ Note importante
Cette architecture représente une modélisation conceptuelle basée sur les meilleures pratiques du domaine et les patterns architecturaux observés dans les systèmes d'IA à grande échelle. 
Mais apres notre discussion avec Chatgpt et Claude on a trouvé qu'elle n'a pas été officiellement confirmée par DeepSeek, mais illustre une approche plausible et optimisée pour ce type de plateforme.

## 🔷Architecture Parallele
<img width="528" height="413" alt="image" src="https://github.com/user-attachments/assets/8e51db4b-6cb8-4aa0-8cb1-b72ec8daeddb" />

## 🔷Mecanisme de Fallback Intelligent
Le syst`eme de fallback Alibaba Cloud surveille en temps r ́eel :
— Charge CPU : Seuil de 80% de saturation
— Utilisation m ́emoire : Limite `a 85% de la capacit ́e
— Temps de r ́eponse : Alerte si ¿ 2 secondes
— Taux d’erreur : Basculement si ¿ 5% d’erreurs
## 🔷Mecanisme de Basculement Automatique
<img width="542" height="319" alt="image" src="https://github.com/user-attachments/assets/28599b83-b11b-4aec-8b46-380e03966433" />
## Avantages de l’Architecture Parall`ele
— Haute Disponibilit ́e : Redondance compl`ete des services
— Performance Optimis ́ee : Processeurs d ́edi ́es par service
— Scalabilit ́e Horizontale : Ajout facile de nouveaux serveurs
— R ́esilience : Basculement automatique en cas de d ́efaillance
— Maintenance Sans Interruption : Mise `a jour altern ́ee des serveurs

## Contributeurs

| Nom & Prénom |
|--------------|
| Lina Boussaada |
| Mariem Trabelsi | 

---

*Document technique sur l'architecture DeepSeek, maintenu par l'équipe système.*
