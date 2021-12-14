# Django admin

Pour récupérer la liste des prospects qui s'inscrivent sur notre formulaire, nous allons utiliser l'interface Django admin.

Ouvrons le fichier `blog/admin.py` dans l'éditeur de code et remplaçons son contenu par ceci :

{% filename %}blog/admin.py{% endfilename %}

```python
from django.contrib import admin
from .models import Prospect

admin.site.register(Prospect)
```

Comme vous pouvez le voir, nous importons le modèle « Prospect » que nous avons écrit dans le chapitre précédent. Afin que notre modèle soit visible dans l'interface d'administration, nous avons besoin d'enregistrer notre modèle à l'aide de `admin.site.register(Prospect)`.

Voilà, il est temps de jeter un œil à notre modèle Prospect. N'oubliez pas d'exécuter `python manage.py runserver` dans votre console afin de lancer le serveur web. Retourner sur votre navigateur et taper l'adresse http://127.0.0.1:8000/admin/. Vous verrez une page de login qui ressemble à celle-ci :

![Page de login](images/login_page2.png)

Afin de vous connecter, vous allez devoir créer un *superuser*, c'est à dire un utilisateur qui contrôlera l'intégralité du site. Retournez à votre ligne de commande : tapez `python manage.py createsuperuser` puis appuyez sur entrée.

> Conseil : pour pouvoir taper de nouvelles commandes pendant que le serveur tourne, ouvrez une nouvelle console et activez à nouveau votre virtualenv. La section **Démarrer le serveur web** du chapitre **Votre premier projet Django !** explique comment écrire de nouvelles commandes.

{% filename %}Mac OS X or Linux:{% endfilename %}

    (myvenv) ~/landingpage$ python manage.py createsuperuser
    

{% filename %}Windows:{% endfilename %}

    (myvenv) C:\Users\Name\landingpage> python manage.py createsuperuser
    

Tapez votre nom d'utilisateur (en minuscules, sans espace), votre email et votre mot de passe. **Ne soyez pas surpris de ne pas voir le mot de passe quand vous le saisissez, c'est normal.** Saisissez le à l'aveugle et appuyez sur `Entrée` pour continuer. Vous devrez obtenir quelque chose comme ceci (où le nom d'utilisateur et le mail correspond à ce que vous avez saisi) :

    Username: ola
    Email address: ola@example.com
    Password:
    Password (again):
    Superuser created successfully.
    

Pour choisir un mot de passe vraiment robuste (et ne pas avoir à vous en rappeler !), vous pouvez utiliser un gestionnaire de mots de passe comme Dashlane (pour lequel beta.gouv peut vous fournir une licence) — plus d'infos dans la doc de la communauté et sur `~incubateur-dashlane`.

Retournez dans votre navigateur et connectez-vous en tant que superutilisateur grâce à l'utilisateur que vous venez de créer. Vous devriez accéder à l'interface d'administration de Django.

![Django admin](images/django_admin3.png)

Vous devriez retrouver ici les Prospects qui se sont inscrits sur votre landing page !

![Django admin](images/edit_post3.png)

Si vous voulez en savoir plus sur l'interface d'administration de Django, n'hésitez pas à consulter la documentation du framework : https://docs.djangoproject.com/en/2.2/ref/contrib/admin/