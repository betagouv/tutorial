# Le Système de Design de l'État (DSFR)

Soyons honnêtes : notre landing page est plutôt moche, non ? Un peu de CSS devrait nous permettre d'arranger ça !
## Qu'est-ce que le CSS ?

Les feuilles de style (CSS : Cascading Style Sheets) sont un langage utilisé pour décrire l'apparence et la disposition d'un site écrit en langage de balisage (comme HTML). Considérez-le comme le maquillage de notre page web. ;)

Mais on ne souhaite pas repartir de zéro. Une fois de plus, nous utiliserons quelque chose que les programmeurs ont publié gratuitement sur Internet. Réinventer la roue n'est pas amusant, n'est-ce pas ?

## Le DSFR

Afin de permettre aux citoyens d'avoir une cohérence graphique et une meilleure expérience à travers l'ensemble des sites de l'État. Le Système de Design de l'État regroupe un ensemble de composants réutilisables, répondant à des standards et à une gouvernance, pouvant être assemblés pour créer des sites Internet accessibles et ergonomiques

Nous alons utiliser les feuilles de style du DSFR afin de rendre notre landing page plus jolie et ergonomique.

Les composantes du DSFR peuvent être téléchargées au lien suivant : https://gouvfr.atlassian.net/wiki/spaces/DB/pages/223019574

Téléchargez les fichiers statiques du DSFR dans le .zip que vous trouverez sur cette page. Puis, dans ce zip, récupèrez le dossier `dist` qui contient tous les éléments dont nous avons besoin pour utiliser le Système de Design de l'État sur notre site.

Ensuite, créez un nouveau dossier `static/css/` dans le dossier `landingpage` qui contient votre application et placez-y le dossier `dist`. Vous devriez maintenant avoir une structure de dossier qui ressemble à celle-ci:

    landingpage
    ├── manage.py
    ├── mysite
    │   └── ...    
    ├── myvenv
    │   └── ...
    ├── landingpage
    │   └── static
    │       └── css
    │           └── dist
    │   └── ...
    └── requirements.txt

Pour vérifier que cela a fonctionné, changez le fichier `home.html` et collez-y ceci :

{% filename %}landingpage/templates/landingpage/home.html{% endfilename %}

```html
<!DOCTYPE html>
<html>

<head>
    <title>Ma Startup d'Etat</title>
    {% load static %}
    <link rel="stylesheet" href="{% static 'css/dist/dsfr/dsfr.min.css' %}">
</head>

<body>
    <header role="banner" class="fr-header">
        <div class="fr-container">
            <div class="fr-header__body-row">
                <div class="fr-header__service">
                    <a href="/" title="Ma super startup">
                        <p class="fr-header__service-title">Ma super startup</p>
                    </a>
                    <p class="fr-header__service-tagline">Apprenez à coller des post-its avec nous</p>
                </div>
            </div>
        </div>
    </header>
    <main role="main" id="contenu">
        <div class="fr-container fr-py-6w fr-px-2w">
            {% block content %}
            {% endblock %}
        </div>
    </main>
</body>
<footer>
    <div class="fr-container">
        <div class="fr-footer__bottom">
            <ul class="fr-footer__bottom-list">
                <li class="fr-footer__bottom-item">
                    <a class="fr-footer__bottom-link" href="">Accessibilité : non conforme</a>
                </li>
                <li class="fr-footer__bottom-item">
                    <a class="fr-footer__bottom-link" href="">Mentions légales</a>
                </li>
                <li class="fr-footer__bottom-item">
                    <a class="fr-footer__bottom-link" href="">Contactez-nous</a>
                </li>
            </ul>
        </div>
    </div>
</footer>

</html>
```

La ligne `<link rel="stylesheet" href="{% static 'css/dist/dsfr/dsfr.min.css' %}">` indique à Django d'aller chercher la feuille de style du DSFR et de l'utiliser pour notre landing page.

Recharchez ensuite votre landing page. Le design de votre page vous-est familier ? C'est normal — votre landing page fait maintenant partie de centaines de sites qui utilisent le DSFR !
