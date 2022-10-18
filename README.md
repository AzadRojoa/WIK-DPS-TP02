Azad Rojoa

- Consignes:

  Créer une image Docker avec un seul stage qui permet d’exécuter votre API développée précédemment (WIK-DPS-TP01)

  L'image doit être la plus optimisée possible concernant l'ordre des layers afin de limiter le temps de build lors des modifications sur le code

  Scanner votre image avec docker scan, trivy ou clair pour obtenir la liste des vulnérabilités détectées

  L'image doit utiliser un utilisateur spécifique pour l'exécution de votre serveur web

  Créer une seconde image Docker pour votre API avec les mêmes contraintes en termes d'optimisations mais avec plusieurs stages : un pour l'étape de build et une autre pour l’exécution (qui ne contient pas les sources)

- Build l'image:

  docker build -t tp02 .

- Run l'image :

  docker run -e PING_LISTEN_PORT=8080 -p 8080:8080 tp02

- Tester le programme :

  Terminal : curl http://127.0.0.1:8080/ping

  Navigateur: http://127.0.0.1:8080/ping

- Fonctionnement:

  Une route "Ping" qui montre tous les headers en format JSON.

  Toutes les autres routes renvoit une erreur 404.

- Technos:

  Rust
  Actix
  Serde
