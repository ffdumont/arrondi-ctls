# Arrondi CTLS

Un atterrissage de CTLS rejoué : une silhouette à l'assiette exacte de la trace, au-dessus
de la piste à l'échelle, et les bandes de mesure synchronisées sous elle.

**La page : https://ffdumont.github.io/arrondi-ctls/**

## Ce que la page montre

**Douze essais, au choix dans le sélecteur en haut à droite**, tous volés sur le banc X-Plane
du projet flare-sim à LFXU 28R. La page s'ouvre sur `20260908-163103` — volets 15, 60 kt,
plan à 5 % — et l'adresse porte l'essai regardé (`?essai=<identifiant>`), donc un lien
envoyé rouvre bien le même vol.

Huit se lisent comme une campagne, et trois leviers les séparent :

- la **vitesse d'approche**, 60 ou 54 kt — celle du club, ou celle du manuel de vol ;
- les **gaz coupés au passage des 50 ft**, qui est la condition dans laquelle le manuel
  établit ses distances d'atterrissage ;
- le **point d'aboutissement**, où le plan de descente coupe la piste : à +183 ou +136 m du
  seuil selon la pente, ou **sur le seuil même** — la pratique de terrain court, qui rend la
  LDA entière disponible.

**Les quatre derniers ont été filmés**, et la section « ce que ça donne en vidéo » porte leurs
liens. Ils n'ajoutent pas un levier, ils ajoutent les images : deux reprennent la
configuration de `20260908-195249` — 60 kt, 3,84°, gaz portés, aboutissement à +136 m — et les
deux autres celle de `20260909-191805`, où l'aboutissement est **sur le seuil**. Chacune des
deux paires reproduit son essai d'origine à trois mètres près sur le toucher.

Une fenêtre de X-Plane ne rend qu'un point de vue à la fois et son enregistreur filme ce qui
est rendu, si bien que la place pilote et la caméra par le travers gauche viennent de **deux
passages successifs**, archivés comme deux essais. L'avion a touché à deux mètres près au même
endroit sur les deux passages d'une même prise ; ce ne sont pas pour autant deux caméras d'un
même vol, et la page ne propose à chaque essai filmé que les points de vue de sa propre prise.

Le panneau « ce qui a été volé » donne, pour l'essai affiché, la masse, la vitesse
d'approche, la pente commandée, la hauteur au seuil, l'aboutissement, les réglages d'arrondi
et de freinage. Trois valeurs y sont en couleur parce qu'elles seules décident si deux essais
se comparent : la coupure des gaz, l'aboutissement au seuil, et la vitesse à laquelle le
roulement est arrêté.

La silhouette porte l'assiette
mesurée à chaque instant et pivote autour du point de contact de ses roues principales.
Sous elle : la hauteur des roues, le variomètre en pieds par minute, la vitesse indiquée
avec la ligne de l'avertisseur de décrochage, l'assiette et l'incidence, la commande de
profondeur — toutes au même curseur.

Trois repères verticaux reviennent partout : le seuil, le **point d'aboutissement**
(où le plan de descente coupe la piste — de la géométrie) et la **marque de toucher**
peinte à +281 m (la médiane des touchers de la flotte — un résultat). L'écart entre les
deux est le flottement.

Commandes : lecture/pause (barre d'espace), vitesse ×½ ×1 ×2, curseur de temps, flèches
gauche/droite image par image, et un clic-glissé sur n'importe quelle bande pour se placer
à une distance au seuil donnée. En ×1, la lecture dure ce que le vol a duré.

## D'où viennent les chiffres

Aucune valeur n'est saisie à la main. La page est **générée** à partir des traces
archivées des essais, des marques peintes sur la piste et du scénario de chaque vol ; le
générateur vit dans le dépôt du projet, qui est privé.

## Comment les essais sont stockés

Tout est statique — aucun serveur, aucune construction côté navigateur :

```
index.html            la page, sans aucune donnée
data/index.json       le catalogue : un descripteur par essai, de quoi remplir le
                      sélecteur sans rien charger d'autre
data/silhouette.json  la silhouette du CTLS, mesurée sur son modèle visuel et
                      identique d'un essai à l'autre — chargée une seule fois
data/runs/<uid>.json  un essai : ses quatorze séries par image, ses repères de piste,
                      ses caractéristiques de vol et sa comparaison au manuel
```

Le découpage suit ce qui varie. La silhouette pèse 17 ko et ne change jamais : l'embarquer
dans chaque essai reviendrait à la republier six fois. Un essai pèse une trentaine de
kilo-octets, et seul celui qu'on regarde est téléchargé.

La silhouette n'est pas un dessin : c'est la projection du modèle visuel de X-Plane sur
son plan de symétrie, rastérisée au pas de 4 mm — 6,69 m de long, 9,04 m d'envergure,
la verrière apparaissant en creux.

## Crédits et réserves

L'avion simulé est le **VSKYLABS Flight Design CTLS** pour X-Plane 12, un produit
commercial. Cette page en publie un **contour de profil en deux dimensions**, mesuré au
pas de 4 mm — ni le maillage, ni les textures, ni aucune donnée du modèle de vol.
Le modèle X-Plane est par ailleurs ~5 % plus grand que le CTLS publié sur les dimensions
de voilure ; c'est l'avion du simulateur qui est dessiné, pas une reconstitution du réel.

Le vol, lui, est piloté par la loi de pilotage du projet flare-sim, partagée avec son
modèle JSBSim.
