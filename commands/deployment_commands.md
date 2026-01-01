
# Commandes utilisées dans le projet Zabbix AWS

## 🔹 Mise à jour système
sudo apt update && sudo apt upgrade -y

## 🔹 Installation Docker
sudo apt install docker.io docker-compose -y
sudo systemctl enable docker
sudo systemctl start docker

## 🔹 Lancement du serveur Zabbix
docker-compose up -d

## 🔹 Vérification des conteneurs
docker ps

## 🔹 Installation Zabbix Agent 2 (Linux)
sudo apt install zabbix-agent2 -y
sudo systemctl enable zabbix-agent2
sudo systemctl start zabbix-agent2

## 🔹 Vérification agent
sudo systemctl status zabbix-agent2

## 🔹 Test de connectivité
telnet 10.0.1.211 10050
