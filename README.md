# Arrondi CTLS

Un atterrissage de CTLS rejoué : une silhouette à l'assiette exacte de la trace, au-dessus
de la piste à l'échelle, et les bandes de mesure synchronisées sous elle.

**La page : https://ffdumont.github.io/arrondi-ctls/**

## Ce que la page montre

L'essai `20260908-163103`, volé sur le banc X-Plane du projet flare-sim à LFXU 28R :
volets 15, 60 kt, plan à 5 %, jusqu'à l'arrêt complet. La silhouette porte l'assiette
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

Aucune valeur n'est saisie à la main. La page est **générée** à partir de la trace
archivée de l'essai, des marques peintes sur la piste et du scénario du vol ; le
générateur vit dans le dépôt du projet, qui est privé.

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
