################################################################################
# 2. Architecture Réseau
################################################################################

# Architecture du VPC et configuration des Security Groups
#
# 📸 Capture d’écran – Architecture réseau AWS
# <img width="873" height="491" alt="image" src="https://github.com/user-attachments/assets/ec7634ac-3b76-4a01-9a69-5d60a8537b7d" />
#<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/a17acda8-d715-4cda-9759-66023799bf83" />
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/d693e734-48a5-406f-b06b-3720d7ce76f1" />
# Figure 1 : Schéma du réseau du VPC, subnet publique et configuration des Security Groups


################################################################################
# 3. Architecture des Instances EC2
################################################################################

# Instances utilisées dans le projet
#
# 📸 Capture d’écran – Instances EC2
# 
#  - Serveur Zabbix (Ubuntu – t3.medium)
<img width="865" height="486" alt="image" src="https://github.com/user-attachments/assets/ce7b34d3-08d2-4c0d-b539-53e2bc04dcee" />
#  - Client Linux (Ubuntu – t3.medium)
<img width="865" height="473" alt="image" src="https://github.com/user-attachments/assets/880fe6a7-b4fc-44ff-86b6-d74bb85f5cb4" />
#  - Client Windows (Windows Server – medium))
#<img width="866" height="487" alt="image" src="https://github.com/user-attachments/assets/778014f1-7950-4efa-a699-e1662dd6dde8" />
# Figure 2 : Instances EC2 utilisées pour le projet de supervision


################################################################################
# 4. Déploiement du Serveur Zabbix
################################################################################

# Conteneurs Docker Zabbix
#
# 📸 Capture d’écran – Conteneurs Docker
# <img width="865" height="350" alt="image" src="https://github.com/user-attachments/assets/3b05d9d5-104a-4fe4-9360-1589b1825bc2" />
# montrant :
#  - zabbix-server
#  - zabbix-web
#  - zabbix-db)
#
# Figure 3 : Conteneurs Docker du serveur Zabbix en cours d’exécution


# Interface Web Zabbix
#
# 📸 Capture d’écran – Interface Web Zabbix
# <img width="920" height="519" alt="image" src="https://github.com/user-attachments/assets/d3471b87-9c6e-4fdf-aaa1-a2affa6f2449" />
#
# Figure 4 : Interface Web Zabbix – Connexion réussie


################################################################################
# 5. Configuration des Clients (Agents)
################################################################################

# Client Linux
#
# 📸 Capture d’écran – Configuration agent Linux
# (Insérer ici la capture du fichier :
#  <img width="922" height="444" alt="image" src="https://github.com/user-attachments/assets/41253a04-583c-49b2-b0c2-c7f9c0c2416d" />
<img width="1920" height="1080" alt="Screenshot (128)" src="https://github.com/user-attachments/assets/63bbf550-3476-4020-ac26-f9b0fb5149aa" />
# montrant :
#  - ServerActive=<IP_PRIVEE_ZABBIX>
#  - Hostname=ubuntu-client)
#
# Figure 5 : Configuration du fichier zabbix_agentd.conf sur le client Linux


# Client Windows
#
# 📸 Capture d’écran – Configuration agent Windows
# <img width="1152" height="550" alt="Screenshot (131)" src="https://github.com/user-attachments/assets/62df1294-c135-4a88-bd68-43cc76ed8f98" />
# ou de l’installateur MSI montrant :
#  - Server=<IP_PRIVEE_ZABBIX>
#  - ServerActive=<IP_PRIVEE_ZABBIX>
#  - Hostname=windows-client)
#
# Figure 6 : Configuration du fichier zabbix_agentd.conf sur le client Windows


################################################################################
# 6. Monitoring et Tableaux de Bord
################################################################################

# Ajout des hôtes dans Zabbix
#
# 📸 Capture d’écran – Hôtes ajoutés
# <img width="429" height="57" alt="Screenshot (115)" src="https://github.com/user-attachments/assets/9f9f331d-aad0-484d-977d-78811d188f9b" />
<img width="1048" height="119" alt="image" src="https://github.com/user-attachments/assets/e803908e-8c54-41ba-a397-3865a3e2f9bd" />
#  Data collection → Hosts
# montrant :
#  - ubuntu-client
#  - windows-client)
#
# Figure 7 : Hôtes supervisés dans l’interface Zabbix


# Statut des hôtes
#
# 📸 Capture d’écran – Statut ZBX
# <img width="1080" height="280" alt="image" src="https://github.com/user-attachments/assets/1f9baf01-221d-4c57-b87f-55e1fa9c598d" />

# avec l’indicateur ZBX en vert)
#
# Figure 8 : Statut de supervision des clients (ZBX vert)


# Graphiques de performance
#
# 📸 Capture d’écran – Graphique CPU ou RAM
# <img width="909" height="511" alt="image" src="https://github.com/user-attachments/assets/6b1a61ed-cc0b-49cd-866c-213d91d31824" />
<img width="909" height="511" alt="image" src="https://github.com/user-attachments/assets/4cbf7d8e-976b-413b-a452-9c7a0cbfe6b9" />

# CPU load ou Memory usage d’un client)
#
# Figure 9 : Graphique de charge CPU ou utilisation mémoire d’un client
################################################################################

