# pas trouvé de solution pour lancer la commande

```sh
# dans le pipeline Jenkins
# problème de droit
pip install Flask
```

# tentative , utiliser le concept d'environnement virtuel de Python

pip freeze > requirements.txt

python -m venv venv
.\venv\Scripts\activate
./venv/bin/activate

dans le pipeline => rien

# tentative , mettre l'utilisateur jenkins avec les droits roots

docker exec -it -u root my-jenkins bash

# SOLUTION

créer une image sur dockerhub maison qui contient les dépendances dont j'ai besoin !!
et la remplacer dans l'image dans l'agent du step

