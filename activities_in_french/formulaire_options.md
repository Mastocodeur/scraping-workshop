# Formulaire chrome_options
Voici une fiche pour répertorier toutes les options possibles de notre driver Chrome.

## Guide de codage
La structure du code est toujours la même : 
- Création d'une instance des options Chrome : 

    `chrome_options = Options()`
- Définition des options Chrome : 

    `chrome_options.add_argument(...)`
- Création d'une nouvelle instance du navigateur Chrome avec les options spécifiées : 

    `driver = webdriver.Chrome(options=chrome_options)`
- Définition de l'URL que l'on veut scraper et injection dans le driver :

    `url = "https://professeur-layton.fandom.com/fr/wiki/La_travers%C3%A9e_(1)"`

    `driver.get(url)`

Précision  : 
- `webdriver.Chrome` initialise le navigateur Chrome via le WebDriver de Selenium.
- `options=chrome_options` permet de passer les options définies précédemment à cette instance de Chrome.

Voici donc les différentes options possibles : 

## --- OPTIONS GÉNÉRALES ---

#### Désactiver l'invite de sélection du moteur de recherche au premier lancement
    chrome_options.add_argument('--disable-search-engine-choice-screen') 

#### Lancer Chrome en mode headless (sans interface graphique)
    chrome_options.add_argument('--headless')

#### Désactiver l'accélération matérielle GPU (souvent nécessaire en mode headless)
    chrome_options.add_argument('--disable-gpu')

#### Démarrer Chrome avec une fenêtre de taille spécifique
    chrome_options.add_argument('--window-size=1920,1080')

#### Démarrer Chrome maximisé
    chrome_options.add_argument('--start-maximized')

#### Ouvrir Chrome en mode incognito (navigation privée)
    chrome_options.add_argument('--incognito')

#### Désactiver la sandbox de Chrome pour des environnements spécifiques (moins sécurisé)
    chrome_options.add_argument('--no-sandbox')

#### Utiliser un profil utilisateur personnalisé (permet de conserver les cookies, l'historique, etc. associés au profil)
    chrome_options.add_argument('--user-data-dir=/path/to/your/custom/profile')



## --- SÉCURITÉ ET VIE PRIVÉE ---

#### Désactiver la sécurité du web, par exemple, pour accéder à des pages avec des erreurs SSL
    chrome_options.add_argument('--disable-web-security')

#### Désactiver l'isolation des sites (peut améliorer les performances mais réduit la sécurité)
    chrome_options.add_argument('--disable-site-isolation-trials')

#### Désactiver les infobars telles que "Chrome est contrôlé par un logiciel de test automatisé"
    chrome_options.add_argument('--disable-infobars')

#### Désactiver les extensions installées dans Chrome
    chrome_options.add_argument('--disable-extensions')

#### Bloquer les popups indésirables, tels que les fenêtres publicitaires et autres fenêtres intempestives
    chrome_options.add_argument("--disable-popup-blocking")

#### Désactiver les notifications du navigateur
    chrome_options.add_argument('--disable-notifications')

#### Activer la navigation en toute sécurité, pour bloquer les contenus malveillants
    chrome_options.add_argument('--safebrowsing-disable-download-protection')

## --- PERFORMANCE ET RENDEMENT ---

#### Désactiver les fonctionnalités spécifiques de Chrome pour améliorer les performances
    chrome_options.add_argument('--disable-features=NetworkService,Notifications')

#### Désactiver le préchargement DNS pour accélérer le chargement des pages
    chrome_options.add_argument('--disable-dns-prefetch')

#### Désactiver le service réseau (réduit l'utilisation des ressources réseau)
    chrome_options.add_argument('--disable-network-service')

#### Activer ou désactiver la compression Brotli (peut affecter la performance du réseau)
    chrome_options.add_argument('--disable-brotli')

## --- AFFICHAGE ET RENDU ---

#### Désactiver WebGL pour éviter certaines animations ou graphiques lourds
    chrome_options.add_argument('--disable-webgl')

#### Désactiver le rendu logiciel, ce qui peut améliorer les performances graphiques
    chrome_options.add_argument('--disable-software-rasterizer')

#### Désactiver le chargement des images pour accélérer le chargement des pages
    chrome_options.add_argument('--blink-settings=imagesEnabled=false')

#### Ouvrir un port pour le débogage à distance
    chrome_options.add_argument('--remote-debugging-port=9222')

## --- DÉTECTION D'AUTOMATISATION ---

#### Désactiver les fonctionnalités qui révèlent que le navigateur est contrôlé par un outil d'automatisation
    chrome_options.add_argument('--disable-blink-features=AutomationControlled')

#### Empêcher l'utilisation de l'extension d'automatisation par défaut de Chrome
    chrome_options.add_experimental_option("useAutomationExtension", False)

#### Exclure certains commutateurs (comme 'enable-automation') qui révèlent que le navigateur est automatisé
    chrome_options.add_experimental_option("excludeSwitches", ["enable-automation"])

#### Désactiver les infobars qui apparaissent en haut du navigateur
    chrome_options.add_argument('disable-infobars')

#### Activer certains paramètres d'automatisation (peut être redondant avec d'autres options)
    chrome_options.add_argument('enable-automation') 

## --- AUTRES OPTIONS UTILES ---

#### Spécifier un User-Agent personnalisé
    chrome_options.add_argument('--user-agent="Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.212 Safari/537.36"')

#### Désactiver les rapports de plantage de Chrome
    chrome_options.add_argument('--disable-crash-reporter')

#### Désactiver la gestion automatique des signets (favoris)
    chrome_options.add_argument('--disable-bookmark-autocomplete')

#### Désactiver les popups de confirmation d'impression
    chrome_options.add_argument('--kiosk-printing')

#### Désactiver le chargement des scripts pour accélérer les temps de chargement des pages
    chrome_options.add_argument('--disable-javascript')

#### Désactiver l'audio pour éviter les sons lors de l'automatisation
    chrome_options.add_argument('--mute-audio')




