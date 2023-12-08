0x10. HTTPS-SSL

0. Internet mondial
obligatoire
Configurez votre zone de domaine pour que le sous-domaine www pointe vers l'adresse IP de votre équilibreur de charge (lb-01). Ajoutons également d'autres sous-domaines pour nous faciliter la vie et écrivons un script Bash qui affichera des informations sur les sous-domaines.

Exigences:

Ajoutez le sous-domaine www à votre domaine, pointez-le vers votre IP lb-01 (votre nom de domaine est peut-être configuré avec des sous-domaines par défaut, n'hésitez pas à les supprimer)
Ajoutez le sous-domaine lb-01 à votre domaine, pointez-le vers votre IP lb-01
Ajoutez le sous-domaine web-01 à votre domaine, pointez-le vers votre IP web-01
Ajoutez le sous-domaine web-02 à votre domaine, pointez-le vers votre IP web-02
Votre script Bash doit accepter 2 arguments :
domaine:
tapez : chaîne
quoi : nom de domaine à auditer
obligatoire : oui
sous-domaine :
tapez : chaîne
quoi : sous-domaine spécifique à auditer
obligatoire : non
Résultat : Le sous-domaine [SUB_DOMAIN] est un enregistrement [RECORD_TYPE] et pointe vers [DESTINATION]
Lorsque seul le paramètre domain est fourni, affichez les informations de ses sous-domaines www, lb-01, web-01 et web-02 - dans cet ordre spécifique
Lors de la transmission des paramètres de domaine et de sous-domaine, afficher les informations sur le sous-domaine spécifié
Ignorer le cas shellcheck SC2086
Doit utiliser:
embarrassant
au moins une fonction Bash
Vous n'avez pas besoin de gérer des cas extrêmes tels que :
Paramètres vides
Noms de domaine inexistants
Sous-domaines inexistants

1. Résiliation SSL HAproxy
obligatoire
« Terminer SSL sur HAproxy » signifie que HAproxy est configuré pour gérer le trafic chiffré, le déchiffrer et le transmettre à sa destination.

Créez un certificat à l'aide de certbot et configurez HAproxy pour accepter le trafic crypté pour votre sous-domaine www.

Exigences:

HAproxy doit écouter sur le port TCP 443
HAproxy doit accepter le trafic SSL
HAproxy doit servir un trafic chiffré qui renverra le / de votre serveur web
Lors de l'interrogation de la racine de votre nom de domaine, la page renvoyée doit contenir Holberton School
Partagez votre configuration HAproxy en tant que fichier de réponses (/etc/haproxy/haproxy.cfg)
Le fichier 1-haproxy_ssl_termination doit être votre fichier de configuration HAproxy

Assurez-vous d'installer HAproxy 1.5 ou supérieur, la terminaison SSL n'est pas disponible avant la v1.5.


