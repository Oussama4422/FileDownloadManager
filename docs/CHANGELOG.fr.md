# File Download Manager — historique des versions

Présentation du projet : [README](../README.md) · site officiel : https://filedownloadmanager.com

## Nouveautés de la version 1.9.0 — torrents à la carte, hébreu, moteurs à jour

- **Torrents** : le bouton « Fichier .torrent » (Ctrl+O) ouvre la fenêtre « Ajouter des torrents » : on y colle un
  ou plusieurs liens magnet et on y importe un ou plusieurs fichiers .torrent (aussi par glisser-déposer).
  Chaque torrent s'ouvre ensuite dans sa propre fenêtre « Contenu du torrent » : arborescence des dossiers et
  fichiers à cocher (dossiers repliables, cases à trois états, filtre, tout / rien), dossier d'enregistrement (par défaut « Torrents »), taille, espace libre, empreinte,
  morceaux, puis Télécharger, Mettre en file d'attente ou Annuler. Pour un lien magnet, la liste arrive dès que
  les pairs ont envoyé les informations du torrent. Même fenêtre pour les liens magnet du navigateur, les
  fichiers .torrent ouverts depuis Windows et ceux déposés sur l'application.
- **Gros torrents** : un téléchargement de plusieurs dizaines de Go ne s'arrête plus au début avec l'erreur
  « HttpClient.Timeout of 20 seconds » : Windows prépare désormais le fichier instantanément (fichier « creux »).
- **Fenêtre d'informations avant chaque téléchargement** (bouton « Ajouter », clic sur un lien ou une vidéo dans
  le navigateur) : nom, taille, type, reprise possible et adresse du fichier, lus avant de télécharger ; dossier
  de sa catégorie par défaut (Vidéos, Musique, Programmes…) ; Télécharger, Mettre en file d'attente ou Annuler.
  Réglage « Afficher la fenêtre d'informations avant chaque téléchargement » (Paramètres → Navigateur). La
  fenêtre « Ajouter » ne gère plus les torrents : un lien magnet collé part dans la fenêtre des torrents.
- **Moteurs de téléchargement et de conversion** (Paramètres) : version installée de yt-dlp, ffmpeg, deno et
  aria2, recherche des mises à jour sur leurs pages GitHub officielles, mise à jour en un clic, et mise à jour
  automatique une fois par jour (activée par défaut).
- **Bouton vidéo du navigateur** redessiné : bouton « Choisir la qualité » sur la vidéo, menu sombre en deux colonnes
  « Options vidéo » (8K, 4K, 2K, 1080p… avec images/s et taille) et « Options audio » (MP3 320 à 96 kb/s).
- **Qualité 8K** : les vidéos en 4320p sont proposées comme « 4320p [8K] » (application et navigateur).
- **Hébreu** dans l'application, l'installateur et l'extension (13 langues, de droite à gauche comme l'arabe) ;
  le site reprend désormais ses textes hébreux de l'application.
- **My Video downloader** : petite icône Android dans la barre de commandes, après « Lancer la file », qui ouvre
  videodownloader.my dans le navigateur.
- **Dons** : PayPal = adresse e-mail seule avec bouton copier (plus de lien vers une page de paiement), comme sur le site.
- **Icône des notifications** : l'application a maintenant sa propre identité Windows (`FileDownloadManager.App`), déclarée
  avec son nom et son logo actuel. Windows gardait l'ancienne icône en cache sous un nom généré automatiquement
  (« NotifyIconGeneratedAumid_… ») ; les raccourcis du menu Démarrer, du Bureau et de la barre des tâches reçoivent
  la même identité pour rester regroupés avec la fenêtre.

## Nouveautés de la version 1.8.1 — arabe : noms de fichiers et adresses

- **Arabe** : les noms de fichiers, adresses et chemins s'affichent dans le bon ordre
  (`blender-4.2.3-windows-x64.msi` et non plus `msi.windows-x64-4.2.3-blender`) dans la liste, la fenêtre de
  progression et le capteur de site, tout en restant alignés à droite ; les champs d'adresse, de nom et de dossier
  se saisissent de gauche à droite.
- Colonne « Dernier essai » un peu plus large : la date et l'heure tiennent en entier.
- Présentation GitHub en 12 langues avec captures (`tools/make_readme.py`, `tools/screenshots/capture.bat`).

## Nouveautés de la version 1.8.0 — allemand et portugais (12 langues)

- **Deux langues de plus** : allemand (Deutsch) et portugais du Brésil (Português), soit 12 langues pour
  l'application (429 textes), l'installateur, l'extension du navigateur (`_locales/de`, `pt_BR`, `pt_PT`) et le site
  (`/de/`, `/pt/`, avec `hreflang`, Open Graph `de_DE` / `pt_BR` et mots-clés propres à chaque pays dans
  `site/docs/SEO.md`). « Automatique » choisit l'allemand ou le portugais si Windows est dans l'une de ces langues ;
  dates et nombres suivent la culture `de-DE` / `pt-BR` (virgule décimale).
- Site : les cartes du téléchargement et du tutoriel ne débordent plus sur les petits écrans (320 px), les boutons
  longs passent à la ligne.
- Arabe : le titre de la fenêtre principale ne passe plus sous les boutons Réduire / Agrandir / Fermer.
- Captures d'écran des 12 langues (`tools/screenshots/capture.bat`) et présentation GitHub en 12 langues
  (`tools/make_readme.py`).

## Nouveautés de la version 1.7.0 — site web et mises à jour automatiques

- **Site officiel filedownloadmanager.com** (dossier `site/`, PHP + SQLite, 10 langues) : présentation, téléchargement,
  tutoriel illustré de l'extension, dons, alternative à IDM, confidentialité, référencement complet (hreflang,
  sitemap, données structurées, Open Graph) et administration avec statistiques (téléchargements, pays, langues,
  navigateurs, sites d'origine, installations actives). Voir `site/README.md`.
- **Mises à jour automatiques** : une fois par jour, l'application demande au site la dernière version (seuls le
  numéro de version et la langue sont envoyés). Un bandeau propose « Mettre à jour » : l'installateur est
  téléchargé, son empreinte SHA-256 vérifiée, puis installé en silence et l'application redémarre. Réglable dans
  Paramètres → À propos (« Rechercher maintenant »).
- **Liens vers le site** : élément « Site web » dans la barre latérale, section À propos des paramètres, fiche
  « Applications installées » de Windows (informations, aide, mises à jour) et page d'accueil de l'extension.
- build.bat écrit l'empreinte SHA-256 de l'installateur dans `out\FileDownloadManager-Setup.sha256`.
- Les pourcentages suivent toujours la langue choisie (virgule ou point), même après un changement de thème.

## Nouveautés de la version 1.6.0 — 10 langues

- **Cinq langues de plus** : russe, chinois simplifié, hindi, japonais et coréen, en plus de l'anglais, du français,
  de l'espagnol, de l'italien et de l'arabe — pour l'application (405 textes), l'extension du navigateur et
  l'installateur. « Automatique » choisit la langue de Windows si elle est proposée.
- **Police propre à chaque écriture** : Microsoft YaHei UI (chinois), Yu Gothic UI (japonais), Malgun Gothic (coréen)
  et Nirmala UI (hindi), avec Segoe UI Variable derrière ; la langue de chaque fenêtre est déclarée pour que les
  idéogrammes prennent la forme chinoise ou japonaise. Dates et nombres suivent la culture de la langue.

## Nouveautés de la version 1.5.0 — BitTorrent

- **Liens magnet et fichiers .torrent** : coller un lien magnet (Ctrl+V, « Ajouter », « Plusieurs liens »), bouton
  « Fichier .torrent » (Ctrl+O), glisser-déposer de fichiers .torrent ou de liens sur la fenêtre, ou clic sur un lien
  magnet dans le navigateur (l'extension l'envoie à l'application). Les .torrent téléchargés depuis le navigateur
  démarrent directement le torrent.
- **Moteur aria2** (libre, fourni avec l'installateur) piloté en arrière-plan : DHT, échange de pairs, découverte locale
  et trackers publics, reprise après pause ou redémarrage (copie du .torrent gardée par l'application, métadonnées
  des liens magnet conservées), limite de vitesse générale et par téléchargement.
- **Affichage** : catégorie « Torrents », pairs et sources dans la liste et la fenêtre de progression, recherche des
  métadonnées des liens magnet, suppression du dossier d'un torrent à plusieurs fichiers si on le demande.
- **Paramètres → BitTorrent** : continuer à partager après le téléchargement (ratio 1,0 ou 1 heure), et ouvrir les
  liens magnet et fichiers .torrent de Windows avec l'application (désactivé par défaut).

## Nouveautés de la version 1.4.0 — nouveau design

- **Système de design « instrument calme »**, inspiré des Paramètres et de l'Explorateur de Windows 11, de Linear
  et des gestionnaires de téléchargement modernes : matière Mica, surfaces superposées, angles de 6 à 8 px,
  icônes monochromes Segoe Fluent, police Segoe UI Variable (Display pour les titres), chiffres alignés.
- **Une seule couleur, réservée à ce qui bouge** : le dégradé bleu → violet n'apparaît que pour la progression,
  le débit, l'action principale et l'élément choisi ; tout le reste est neutre (rouge seulement pour les erreurs).
- **Fenêtre principale** : barre de titre intégrée (dispositions d'ancrage de Windows 11), barre latérale avec
  compteurs alignés, **courbe du débit en direct** (dernière minute, pic), barre de commandes qui passe en icônes
  seules quand la place manque, liste avec pastille d'état (anneau de progression, coche, erreur), cases visibles
  au survol, état vide avec bouton « Ajouter ».
- **Paramètres** façon Windows 11 (une ligne par réglage, interrupteurs) et nouveau choix **Apparence** :
  comme Windows, clair ou sombre.
- **Boîtes de message** aux couleurs de l'application (fin des boîtes grises de Windows), onglets « pivot »,
  pieds de fenêtre pour les boutons, fenêtre de progression avec le pourcentage en grand.
- **Nouveau logo** : trois fragments réunis en une flèche, sur une tuile bleu → violet ; extension du navigateur
  et installateur aux mêmes couleurs.

## Nouveautés de la version 1.3.2

- **Sélection à la souris** dans la liste : une case à cocher par téléchargement (s'ajoute à la sélection sans
  effacer les autres), case « tout sélectionner » dans l'en-tête, bouton « Tout sélectionner », glisser la souris
  sur plusieurs lignes, Ctrl/Maj + clic et Ctrl+A.
- **Aspirateur de site web** (bouton « Aspirer un site », menu de la zone de notification) : tout le site
  (pages, images, styles, scripts, fichiers) avec liens convertis pour la consultation hors ligne, ou seulement
  les fichiers des extensions choisies (préréglages Images, Documents, Musique, Vidéos, Compressés, Programmes) ;
  profondeur des liens, nombre maximal de pages, fichiers d'autres domaines, arborescence du site, choix du dossier.
  L'analyse liste les fichiers trouvés (à cocher), puis les téléchargements passent par la file d'attente.

## Nouveautés de la version 1.3.1

- **Téléchargement multi-fragments** (option dans Paramètres → Connexions, et case dans « Nouveau téléchargement »
  et « Plusieurs liens ») : le fichier est découpé en fragments téléchargés en même temps, puis réunis à la fin.
- **Deuxième barre de progression** dans la fenêtre de téléchargement : la réunion des fragments
  (« Réunion du fragment 3 sur 8… »), ainsi que la fusion image + son des vidéos ; ligne « Fragments » dans l'état.
- **Couleurs sobres** : un seul dégradé bleu → indigo (logo, icônes, boutons, barres), gris ardoise pour les
  commandes secondaires, rouge réservé aux erreurs ; la couleur d'accentuation de Windows est remplacée par celle de l'application.

## Nouveautés de la version 1.3

- **10 langues** : anglais, français, espagnol, italien, arabe (de droite à gauche), russe, chinois simplifié,
  hindi, japonais et coréen. Choix dans Paramètres → Général ; « Automatique » suit la langue de Windows
  (anglais à défaut). L'extension et l'installateur suivent aussi la langue. Textes dans `tools/i18n.py`
  (en, fr, es, it, ar) et `tools/i18n_more/*.json` (ru, zh, hi, ja, ko, de, pt) → `src/Fdm.Core/Localization/*.json`.
- **Fenêtre de progression** à chaque démarrage (comme IDM) : état, taille, débit, temps restant,
  reprise possible, carte des connexions et tableau N° / téléchargé / infos ; onglets
  « Limiteur de vitesse » et « Options de fin » (ouvrir le fichier ou le dossier, veille, arrêt).
- **Catégories et classeur** : Compressés, Documents, Musique, Programmes, Vidéos, Images,
  Non terminés, Terminés, File d'attente ; tableau Nom / F / Taille / Statut / Temps restant /
  Débit / Dernier essai / Description ; rangement automatique des fichiers par catégorie.
- **Choix de la qualité** (YouTube, Facebook, Vimeo…) : 4K, 1080p, 720p… ou MP3 320/256/192/128/96 kb/s,
  dans la page (panneau sur la vidéo) comme dans la fenêtre « Nouveau téléchargement ».
- **Conversion en MP3** d'un fichier téléchargé (clic droit → Convertir en MP3).
- **Liens sélectionnés en un clic** : sélectionnez des liens vers des fichiers dans une page,
  un bouton « Télécharger N liens » apparaît (ou clic droit → Télécharger les liens sélectionnés).
- **Composants vidéo inclus** dans l'installateur (yt-dlp, ffmpeg, ffprobe, deno).
- **Démarrer avec Windows** : case dans l'installateur et dans les Paramètres.
- **Design 3D** : logo 3D animé (Viewport3D), boutons en relief, barres de progression brillantes.
- **Tutoriel illustré** d'installation de l'extension pour Chrome, Edge, Brave, Opera, Vivaldi et Firefox.
- **Onglet « Faire un don »** : PayPal et Bitcoin (QR code).
