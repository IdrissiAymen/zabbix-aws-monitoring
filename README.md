# zabbix-aws-monitoring
# Mise en œuvre d’une infrastructure cloud de supervision centralisée sous AWS

## Déploiement de Zabbix conteneurisé pour le monitoring d’un parc hybride (Linux & Windows)

---

## Introduction

Ce projet a pour objectif de déployer une solution de supervision centralisée basée sur **Zabbix**, conteneurisée avec **Docker**, et hébergée sur **AWS**. L’infrastructure permet de superviser un parc hybride composé d’un serveur **Linux** et d’un serveur **Windows**. Le déploiement respecte les contraintes du **Learner Lab AWS** et met l’accent sur la traçabilité via des **captures d’écran commentées**.

---

## Étape 1 — Sélection de la région AWS

**Action réalisée :** Sélection de la région **us-east-1 (N. Virginia)** dans la console AWS.

**Objectif :** Garantir la stabilité du Learner Lab et éviter les limitations de ressources.

**Capture à fournir :** Région visible en haut à droite de la console.

**Légende :** Figure 1 : Sélection de la région AWS us-east-1 (N. Virginia)

---

## Étape 2 — Création du VPC

**Action réalisée :** Création d’un VPC nommé `NomEtudiant-Zabbix-VPC` avec le CIDR `10.0.0.0/16`.

**Objectif :** Isoler l’infrastructure dans un réseau virtuel privé.

**Capture à fournir :** Page de création du VPC avec le nom et le CIDR visibles.

**Légende :** Figure 2 : Création du VPC dédié à l’infrastructure Zabbix

---

## Étape 3 — Création du Subnet public

**Action réalisée :** Création d’un subnet public `Public-Subnet-Zabbix` (CIDR `10.0.1.0/24`) avec attribution automatique d’IP publique.

**Objectif :** Permettre l’accès Internet aux instances pour l’administration et la supervision.

**Capture à fournir :** Détails du subnet (CIDR, option IP publique).

**Légende :** Figure 3 : Configuration du subnet public

---

## Étape 4 — Internet Gateway et routage

**Action réalisée :** Création et association d’un **Internet Gateway** au VPC, puis ajout de la route `0.0.0.0/0`.

**Objectif :** Autoriser la communication entre les instances et Internet.

**Capture à fournir :** Internet Gateway attachée + table de routage.

**Légende :** Figure 4 : Association de l’Internet Gateway et configuration du routage

---

## Étape 5 — Security Group

**Action réalisée :** Création du Security Group `SG-Zabbix-Monitoring` avec les ports nécessaires (22, 3389, 80, 443, 10050, 10051).

**Objectif :** Sécuriser l’accès réseau aux instances selon le principe du moindre privilège.

**Capture à fournir :** Règles entrantes du Security Group.

**Légende :** Figure 5 : Règles de sécurité du Security Group Zabbix

---

## Étape 6 — Création des instances EC2

### 6.1 Serveur Zabbix

**Action réalisée :** Déploiement d’une instance Ubuntu t3.large nommée `NomEtudiant-Zabbix-Server`.

**Objectif :** Héberger le serveur Zabbix et les conteneurs Docker.

**Capture à fournir :** Instance en état *Running* avec le nom visible.

**Légende :** Figure 6 : Instance EC2 du serveur Zabbix

### 6.2 Client Linux

**Action réalisée :** Déploiement d’une instance Ubuntu t3.medium.

**Objectif :** Machine Linux supervisée par Zabbix.

**Capture à fournir :** Instance Linux en état *Running*.

**Légende :** Figure 7 : Instance EC2 client Linux

### 6.3 Client Windows

**Action réalisée :** Déploiement d’une instance Windows Server t3.large.

**Objectif :** Machine Windows supervisée par Zabbix.

**Capture à fournir :** Instance Windows en état *Running*.

**Légende :** Figure 8 : Instance EC2 client Windows

---

## Étape 7 — Connexion SSH au serveur Zabbix

**Action réalisée :** Connexion SSH au serveur Zabbix depuis le terminal.

**Objectif :** Administrer le serveur pour installer Docker et Zabbix.

**Capture à fournir :** Terminal avec connexion réussie.

**Légende :** Figure 9 : Connexion SSH au serveur Zabbix

---

## Étape 8 — Installation de Docker et Docker Compose

**Action réalisée :** Installation de Docker et Docker Compose sur le serveur Ubuntu.

**Objectif :** Déployer Zabbix sous forme de conteneurs.

**Capture à fournir :** Installation réussie dans le terminal.

**Légende :** Figure 10 : Installation de Docker et Docker Compose

---

## Étape 9 — Déploiement de Zabbix via Docker

**Action réalisée :** Lancement des conteneurs Zabbix (server, base de données, interface Web).

**Objectif :** Mettre en service la plateforme de supervision.

**Capture à fournir :** Résultat de la commande `docker ps`.

**Légende :** Figure 11 : Conteneurs Zabbix en cours d’exécution

---

## Étape 10 — Accès à l’interface Web Zabbix

**Action réalisée :** Connexion à l’interface Web Zabbix via le navigateur.

**Objectif :** Administrer la supervision depuis une interface graphique centralisée.

**Capture à fournir :** Page de connexion Zabbix.

**Légende :** Figure 12 : Interface Web Zabbix accessible

---

## Étape 11 — Configuration de l’agent Linux

**Action réalisée :** Installation et configuration de l’agent Zabbix sur le client Linux.

**Objectif :** Collecter les métriques système Linux.

**Capture à fournir :** Fichier `zabbix_agentd.conf` configuré.

**Légende :** Figure 13 : Configuration de l’agent Zabbix sur Linux

---

## Étape 12 — Configuration de l’agent Windows

**Action réalisée :** Installation et configuration de l’agent Zabbix sur le serveur Windows.

**Objectif :** Collecter les métriques système Windows.

**Capture à fournir :** Service Zabbix Agent actif.

**Légende :** Figure 14 : Configuration de l’agent Zabbix sur Windows

---

## Étape 13 — Ajout des hôtes dans Zabbix

**Action réalisée :** Ajout des hôtes Linux et Windows dans l’interface Zabbix.

**Objectif :** Déclarer les machines à superviser.

**Capture à fournir :** Liste des hôtes ajoutés.

**Légende :** Figure 15 : Ajout des hôtes Linux et Windows dans Zabbix

---

## Étape 14 — Vérification de la supervision

**Action réalisée :** Vérification du statut des agents (ZBX vert).

**Objectif :** Confirmer le bon fonctionnement de la supervision.

**Capture à fournir :** Statut des hôtes.

**Légende :** Figure 16 : Agents Zabbix connectés avec succès

---

## Étape 15 — Visualisation des données

**Action réalisée :** Consultation des graphiques CPU/RAM dans *Monitoring > Latest Data*.

**Objectif :** Analyser les performances en temps réel.

**Capture à fournir :** Graphique CPU ou RAM.

**Légende :** Figure 17 : Graphique de performance d’un hôte supervisé

---

## Conclusion

Ce projet a permis de déployer une infrastructure de supervision complète sur AWS avec Zabbix et Docker. Les principales difficultés rencontrées concernaient l’ouverture des ports et la persistance des conteneurs après arrêt du lab, résolues par une configuration réseau correcte et le redémarrage des services Docker.
