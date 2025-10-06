# AMAL_TP2

Ce rapport propose une étude détaillée de l’architecture microservices de la plateforme DeepSeek, en mettant l’accent sur la modélisation UML de l’API Gateway, l’organisation du traitement parallèle et les pistes d’amélioration architecturale. 
L’analyse s’appuie sur des diagrammes UML standardisés pour représenter la structure statique (classes, composants, packages) ainsi que le comportement dynamique (séquences, activités, états) du système. L’objectif principal est d’identifier et de concevoir une architecture parallèle optimale, favorisant à la fois la scalabilité horizontale et l’efficacité du traitement des requêtes IA.

#Architecture Gateway API Standard

Avant d’aborder l’architecture API Gateway de DeepSeek, nous allons d’abord présenter l’architecture API Gateway standard.
<img width="818" height="500" alt="image" src="https://github.com/user-attachments/assets/94f3d8c9-16bd-43e7-8fdc-024625534003" />

#Architecture Gateway API - Deepssek
<img width="1268" height="757" alt="DEEPSEEK ARCHI" src="https://github.com/user-attachments/assets/2d01c627-3b99-403e-ad81-a4ecaac49e15" />

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
