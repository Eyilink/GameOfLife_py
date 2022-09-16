LES AUTOMATES CELLULAIRES



SOMMAIRE
Introduction	3
1 - Définition	3
2 - L’histoire des automates cellulaires	3
I-Système dynamique	4
1 - Temporalité au sens algorithmique	4
2 - Les règles au sens algorithmique	4
3 - Caractérisation mathématique d’un automate cellulaire	4
II-Avantages et intérêts des automates cellulaires	5
1 - Machine de Turing (turing-complet)	5
1.1 Définition	5
1.2 Machine de Turing Universelle	6
2 - Classes remarquables d’automates cellulaires	7
2.1 Automates cellulaires réversibles	7
2.2 - Automates cellulaires linéaire	7
2.3 La classification de Wolfram	8
III-Application et structures : Le jeu de la Vie	9
1 - Histoire	9
2 - Les structures	9
2.1 - Structures classiques	9
2.2 - Structures associées	10
3 - Analyse du fonctionnement de l’automate	11
3.1 - Les règles du Jeu de la Vie	11
3.2 - Simulation d’un vaisseau : LWSS	12
4 - Exemples d’application	12
4.1 Chiffrement de données et sécurité informatique	12
4.2 Musique	13
IV-Etat de la recherche	14
1-Les automates cellulaires quantiques	14
1.1 - Le but de la recherche dans ce domaine	14
1.2 - Fonctionnement	14
1.3 - Les problèmes restants à résoudre	15
CONCLUSION	17
BIBLIOGRAPHIE	18
LISTE DES FIGURES	19
ANNEXES	20




Introduction
1 - Définition

Un automate cellulaire est un ensemble de cellules sous forme de matrice, ces cellules doivent pouvoir prendre au moins deux états, chaque cellule possède un ou plusieurs voisins que l’on appelle son voisinage. Cet ensemble doit être régi par un ensemble de règles relativement simples. Ces règles doivent mener à une évolution de l’ensemble des cellules étape par étape. Ces règles sont appliquées à l’ensemble des cellules en même temps. 

2 - L’histoire des automates cellulaires

Le premier automate cellulaire fut créé dans les années 1940 par le mathématicien et informaticien John Von Neumann. Cet automate cellulaire, appelé “copieur et constructeur universel”, fut le résultat des recherches de John Von Neumann sur les systèmes auto-réplicatifs. Le copieur et constructeur universel est une matrice de cellules en deux dimensions dans lesquelles les cellules peuvent prendre 29 états. Dans cet automate cellulaire John Von Neumann put créer un motif pouvant se répliquer à l’infini.

À la fin des années 1950 les automates cellulaires ont commencé à être assimilés à des ordinateurs parallèles, des structures permettant de traiter des informations de manières simultanées.

Puis dans les années 1960 le parallèle entre les automates cellulaires et les machines de Turing commença à émerger.

Dans les années 1970 fut créé le plus célèbre des automates cellulaires, le jeu de la vie. Inventé par le mathématicien John H. Conway le jeu de la vie, composé de quatre règles simples, est encore étudié de nos jours. 

Au cours de l’année 1981 l'informaticien Stephen Wolfram commence à travailler sur les automates cellulaires publiant plusieurs papiers. Notamment un en 2002 appelé “A new kind of science” appuyant que les découvertes sur les automates cellulaires ne sont pas des découvertes isolées mais sont importantes pour toutes les sciences.











I-Système dynamique

1 - Temporalité au sens algorithmique

Un automate cellulaire à un temps t sera composé de plusieurs cellules (matrice de cellules , qu’on appellera C)  dont leur état sera retenu dans une matrice d’état (E) . A t=t+1 , la nouvelle matrice temporaire (T) d’état retiendra le nouvelle état des cellules en fonction des règles appliquées et de l’état de l’ancienne matrice d’état (E) .La nouvelle matrice(T) d’état sera affecté dans la matrice d’état(E) qui aura alors les nouveaux états des cellules. Il ne reste plus qu’à dessiner la matrice C dans un canvas.

2 - Les règles au sens algorithmique

Les règles sont l’ensemble des lois régissant le passage d’une cellule de  l'état (T)  à l’état (t=t+1) en fonction de son voisinage.
À chaque nouvelle unité de temps, les mêmes règles sont appliquées simultanément à toutes les cellules de la grille, produisant une nouvelle « génération » de cellules dépendant entièrement de la génération précédente.
On peut modéliser une règle par une application F:E(t)E(t+1) .

3 - Caractérisation mathématique d’un automate cellulaire
Un automate cellulaire est défini par : 
d sa dimension , son réseau est alors Zd. 
Q qui est son alphabet 
V Zd qui est son voisinage 
:a qui est sa règle de transition locale et a = V qui est l’arité de l’automate ( l’arité d’une fonction est le nombre d’opérandes ou d’arguments qu’elle requiert)
Par exemple un automate cellulaire binaire ayant 2 dimensions représenté par une matrice dont chaque cellule peut prendre deux valeurs (0 ou 1) étant son alphabet Q et qui a une régle . Alors cela peut-être représenté sur un plan dont l’ensemble des cellules est son réseau Zd. Chaque cellule a huit voisins donc son arité a =V = 8  et son voisinage V =v1, ... , v8.
La configuration d’un automate cellulaire est l’attribution d’un état à chaque cellule du réseau. Une configuration est un élément de QZd, c’est à dire une fonction qui associe à chaque élément du réseau Zdun état de l’ensemble Q.
On associe une fonction globale à un automate : F:QZdQZd

Définie par : F(c) = z(c(z+v1), .... ,c(z+va))  pour toute configuration cQZdet voisinage V =v1, ... , va.
II-Avantages et intérêts des automates cellulaires
1 - Machine de Turing (turing-complet)
1.1 Définition 

Une machine de Turing est un concept abstrait qui modélise le fonctionnement d’objets, c’est un objet mathématique qui comporte les éléments suivants :

-Un ruban infini divisé en cases consécutives. Chaque case contient un alphabet fini donné. Le ruban à une largeur infini, c'est-à-dire que l’on peut se déplacer dans chaque cases à droite ou gauche sans interruption. La machine doit avoir assez de longueur de ruban à droite et à gauche pour son exécution.

-Une tête de lecture / écriture qui peut lire ou écrire (et se déplacer vers la droite ou gauche) n’importe où sur le ruban.

-Un registre d’état qui mémorise l’état de la machine. A noter qu’il existe un état initial de la machine avant son exécution. 

-Une machine d’action qui indique quel sera le nouvel état sur chaque case en fonction de l’ état courant, des règles appliquées. Si aucune action n’existe pour une combinaison lu et état courant alors la machine s’arrête.







1.2 Machine de Turing Universelle 

Une machine de Turing universelle est capable de simuler le comportement de n’importe quelle autre machine de Turing.
C’est à dire que si on lui donne le codage d’une machine de Turing T et en entrée des données D, elle produit le même résultat que la machine T à laquelle on aurait donné les données D en entrée.
On dit alors qu’elle est Turing-complet.

Par exemple un automate universel est intuitivement capable de simuler pas à pas n’importe quel autre automate de même dimension :




Figure 1 : Automate universel

L’automate cellulaire de gauche (A)  est un Jeu de la Vie avec pour configurations de départ des planeurs.


Figure 2 : Motif d’un planeur
 
Chaque cellule de l’automate de droite (B)  est représentée par 16 cellules (4x4) dans A. B à l’état noir correspond à un groupe de 16 celulles mortes dans A. L’état rouge de B correspond à un planeur entouré de cellules mortes dans (A) à condition qu’il soit dans une case.


2 - Classes remarquables d’automates cellulaires
	2.1 Automates cellulaires réversibles
		Par définition, un automate cellulaire A est réversible s’il existe un automate cellulaire B tel que les fonctions globales de FAet FBsont l’inverse l’une de l’autre : FAFB= I avec I l’identité.

Autrement dit B “remonte le temps” de l’évolution de A et inversement.
Un automate réversible est associé à une fonction globale qui est bijective. 
Ce type d’automate cellulaire à été très étudié notamment en physique car dans la recherche les systèmes de calcul réversibles sont supposés consommer moins d’énergie (d’après le principe de Landauer ).Certains automates cellulaires réversibles sont Turing-Universelle ( travaux de Kenichi Morita ).

Par exemple, il est possible de créer un automate cellulaire réversible avec la technique dite du second ordre qui consiste à mélanger bit à bit les informations du nouvel état grâce à un ou exclusif en fonction de son état passé. Cependant pour que cela fonctionne il faut un nombre considérable d’états.

L'intérêt de tels automates se trouve dans la recherche et particulièrement en informatique

	2.2 - Automates cellulaires linéaire
		Un automate cellulaire d’alphabet Q est dit linéaire si on peut munir Q d’une loi de groupe , c’est à dire :

(x1y1,x2y2, ... ,xnyn) =(x1 , x2 , ... , xn) (y1 ,y2 ,... , yn) 

Fest linéaire, si on étend l’opération agissant de cellule en cellule sur l’espace de configurations, car elle est une composition de .
Parmi ces automates linéaires il existe une sous-famille qui s’appelle les automates cellulaires additifs. C'est-à-dire quand on ajoute chaque motif cela revient à les ajouter cellules par cellules. Par exemple l’automate cellulaire élémentaire 90 est additif et contient deux états : 0 ou 1. Sa règle consiste à faire modulo 2 la somme de ses deux cellules voisines de sa ligne, c’est donc un automates de dimension 1 :

Figure 3 : Automate additif

Chaque ligne modélise l’état  t+1, l’état t=0 est défini par la dernière ligne qui comporte qu’une cellule à 1.
On peut voir qu’avec le principe de superposition quand on additionne deux automates élémentaire 90 par rapport au même point (rouge) cela donne bien la somme des deux.

Cet automate est appelé automate cellulaire élémentaire 90 car Stephen Wolfram a répertorié les 256 règles existantes pour les automates contenant deux états (binaire).
Ici on utilise la règle 90.

	
2.3 La classification de Wolfram
		La première tentative de classification est apparu en 1983 dans l’article de Stephen Wolfram “Universality and complexity in cellular automata” dans laquelle il classe les automates selon leur évolution à partir de configurations initiales aléatoires :

Stable ( I ) : Au bout d’un certain nombre de générations le motif devient stable, c’est à dire que sa configuration n’évolue plus
Cyclique ( II ) : c’est un automate évoluant vers un état qui se stabilise où les motifs se répètent périodiquement
Chaotique ( III ) : Le système génère des motifs chaotiques et apériodiques
Complexe ( IV ) : émergence de motifs complexes comme des oscillateurs voire des systèmes leurs stabilités malgré des perturbations injectées dans l’automate. Exemple : Le jeu de la Vie

Cependant il existe d’autres classifications qui sont apparues plus tard prenant en compte d’autres paramètres. Par exemple : la classification d’Eppstein.




III-Application et structures : Le jeu de la Vie
1 - Histoire

Le Jeu de la Vie fut inventé par John Conway qui était professeur de mathématiques à l’université de Cambridge.
Conway était intéressé par un problème présenté par un mathématicien renommé : John von Neumann.
Il essayait de trouver une hypothétique machine qui pourrait s’auto-reproduire. Conway essaya de simplifier les idées de von Neumann et finit par réussir. Couplant les réseaux de Leech avec ses travaux sur les machines autoréplicantes, il donne naissance au jeu de la vie.
Il est apparu la première fois en octobre 1970 dans le magazine Scientific American sous la rubrique jeux mathématiques.
D’un point de vue théorique il est intéressant car il a les caractéristiques d’une Machine de Turing Universelle
Le jeu a beaucoup de modèles qui émergent des conditions initiales particulières.
 
2 - Les structures
	2.1 - Structures classiques	
En fonction de l’état initial des cellules, l'automate cellulaire peut faire apparaître plusieurs types de structures.
Tout d’abord, les structures stables sont des ensemble de cellules n’ayant plus d'évolution. C’est à dire qu’aucun élément perturbateur ne peut changer le motif créé par l’automate.
Nous avons aussi les structures périodiques ou oscillateurs ,ils se transforment de manière cyclique en adoptant plusieurs formes avant de retrouver leur état de départ.
La dernière structure classique et particulièrement identitaire aux automates cellulaires est appelée les vaisseaux. Un vaisseau est une structure capable de retrouver son état initial mais décalé dans l’univers du jeu après un certain nombre de générations. 
Un vaisseau qui retrouve son état après N itérations de l’algorithme , s’étant déplacé de A cases horizontalement et de B cases verticalement est notée A-B .
Sa vitesse est définie par max(A,B) * c / N avec c représente “ la vitesse de la lumière “ , qui est la vitesse maximale d’une cellule par itération.
On peut distinguer plusieurs types de vaisseaux :
les vaisseaux transversaux qui se déplacent soit horizontalement soit verticalement  autrement dit (A,B) = 0 , donc A=0 ou B=0
les vaisseaux de type diagonal à savoir A = ∓B
des vaisseaux ayant un déplacement oblique ,c’est à dire A ≠ ∓B
 
 
 
 
Le planeur est le plus petit vaisseau du jeu de la Vie , il a donc la plus grande vitesse .

Figure 4 : Planeur
 
	2.2 - Structures associées
		Les structures associées sont la composition de plusieurs vaisseaux ou automates cellulaires qui donneront en sortie un ou plusieurs vaisseaux.
Par exemple , un réflecteur est un motif stable jusqu'à ce qu’un vaisseau l’atteigne produisant alors une copie de ce vaisseau se déplaçant dans une direction différente.
Les tagalong (suiveur ) et pushalong (tracteur) sont deux autres types de structures associées, basiquement un tagalong est un motif stable qui n’est pas un vaisseau mais qui peut-être attaché derrière un vaisseau pour un former un plus grand.Au contraire un pushalong est un motif que l’on vient attacher devant un vaisseau. Par exemple la position initiale du canon à planeur (Jeu de la Vie) en est un exemple :

Figure 5 : Canon à planeur position initiale
Les vaisseaux peuvent aussi être utilisés pour transmettre des informations.
Par exemple, le planeur du Jeu de la Vie peut servir à cette fonction. Il existe des portes logiques pour planeurs.
Exemple d’une structure associée “Le feu de forêt" :
=
 
Figure XX : Feu de forêt 
 
 
3 - Analyse du fonctionnement de l’automate
	3.1 - Les règles du Jeu de la Vie
		Le jeu de la Vie (voir en annexe code python) est un automate cellulaire, c’est à dire que c’est un jeu sans joueurs, son évolution dépend des états initiales des cellules et des règles appliquées.
Chaque cellule peut prendre deux états : mort (0) ou vivant (1).
A chaque étape, l’état futur d’une cellule est déterminée par ses huit voisins :
une cellule morte possédant exactement trois voisins devient vivante
une cellule vivante ayant deux ou trois voisines vivantes le reste, autrement elle meurt
 
Ainsi cette configuration initiale :
 (1)
Figure 6 : Exemple Jeu de la Vie (a)
Donnera après avoir appliquées les règles :
(2)
Figure 7 : Exemple Jeu de la Vie (b)
Avec ce modèle initial, on obtient un oscillateur qui oscille entre la figure (1) et (2).
 
 
En reformulant :

Figure 8 : Exemple Jeu de la Vie (c)
Si une cellule a trois voisines vivantes, elle sera vivante à l’état suivant.

Figure 9 : Exemple Jeu de la Vie (d)
Si une cellule a exactement deux cellules voisines vivantes elle reste dans son état actuel.

Figure 10 : Exemple Jeu de la Vie (e)
Si une cellule a moins de deux ou strictement plus de trois cellules voisines vivantes, à l'étape suivante elle sera morte. Dans le cas ci-dessus la cellule a plus de trois voisins vivants elle sera donc à l’état 0.
	
	3.2 - Simulation d’un vaisseau : LWSS 
Le LWSS (Light Weight SpaceShip) est un vaisseau qui est créé avec le Jeu de la Vie en ayant des paramètres initiaux particuliers (code python en annexes).

Figure 11 : Motif initial LWSS

D’après ce motif initial le jeu de la Vie va générer les figures 2,3 et 4 ci-dessous :

Figure 12 : Cycle LWSS

Ces motifs se répètent indéfiniment se déplaçant de 2 cases (A) de gauche à droite à chaque cycle comprenant 4 itérations d'algorithme (N). 
Donc la vitesse V=c*max(A,B)/N = c*A/4 = c/2 ce qui signifie que le vaisseau se déplace d’une cellule toute les deux générations d'algorithmes.

4 - Exemples d’application
4.1 Chiffrement de données et sécurité informatique 
		Il est possible avec les automates et certaines règles de générer un motif presque aléatoire par exemple règle Wolfram 90 qui à partir d’une suite binaire initiale en génère une nouvelle. Il suffirait de choisir la suite initiale en fonction de paramètres connus comme l’heure, une adresse IP, les initiales d’un prénom et nom… On pourrait utiliser cet algorithme pour créer une clé de cryptage.


Figure 13 : Automate cellulaire généré avec la 90ème règle de Wolfram

Bien souvent le chiffrement de donnée est unilatérale, cependant il peut y avoir de collisions qui peuvent obfusquer la version cryptée et donc on est incapable de remonter à un mot de passe à partir de sa version cryptée ( automate réversible ). En revanche, il peut s’agir d’une méthode efficace pour ne pas remonter à un mot de passe depuis sa version cryptée.
Toutefois, on pourrait tout aussi bien utiliser un automate de classe III ( chaotique ) de Wolfram pour générer une clé ou une version cryptée presque aléatoire.

4.2 Musique 
		Dès la fin des années 1980, on voit apparaître des applications musicales. La plus célèbre est celle de Iannis Xenakis dans sa pièce pour orchestre Horos.


Figure 14 : Mesures musicales en fonction d’automates cellulaires

Par exemple les différents paramètres sont modélisés de la façon suivante :
La hauteur des notes est déterminée par sa disposition par rapport à la case la plus basse de l’automate.
L’état des cellules détermine le choix de l’instrumentation ( ex : piano, trompette, contrebasse, violon ..).
Les événements musicaux, c'est-à-dire le rythme , sont contrôlés par la présence ou non de cellules.

Un autre exemple est l’automate “Life Forms“ de Tim Thompson qui est basée sur le Jeu de la Vie, dans lequel on peut simuler ce type de morceau :

Sonate_Tim_Thompson

(Autre musique générée par un automate  : www.youtube.com/watch?v=ZZu5LQ56T18 )

IV-Etat de la recherche
1-Les automates cellulaires quantiques
1.1 - Le but de la recherche dans ce domaine
   La recherche dans ce domaine a pour but de développer des nouvelles méthodes de traitement d’information menant, à terme, à inventer des ordinateurs quantiques.
	En effet les chercheurs se sont lancé dans ce projet car le seul moyen connu, aujourd’hui, d’améliorer les performances des ordinateurs est de réduire la taille de leurs composants pour augmenter leur nombre.
	Les ordinateurs quantiques auraient de bien meilleures capacités de traitement que les ordinateurs classiques et seraient bien plus petits.

1.2 - Fonctionnement

	Les ordinateurs quantiques devront utiliser des cellules d’automates cellulaires quantiques commes des bits quantiques (qubits bits en superposition quantique d’état). Ces cellules sont constituées de 5 points et contiennent deux électrons. On notera les points de par un numéro de 0 à 4. Les répulsions coulombiennes mutuelles entraînent la bi-stabilité de la cellule entre les états P=+1 et P=-1. 

Figure 15 : Cellules quantiques

Ces ordinateurs quantiques seraient commandés par les bords (edge-driven) c’est à dire qu’aucune connection directe n’est faite entre les cellules internes de l’automate cellulaires et l'extérieur de cet automate. Ceci peut poser un problème :
 “Le fait qu’il n’y ai pas de connections directe aux cellules intérieures signifie qu’aucun mécanisme n’existe pour garder l’automate cellulaire à l’écart de son état de base.” traduit depuis le pdf de la recherche sur les automates cellulaires

Les chercheurs ont cependant trouvé un usage à cet état de base. Ils traitent les données en se servant de l’état de base (“computing with ground state”). Cette méthode a pour avantage que l’automate cellulaire traite les informations grâce à l’énergie dissipée par le système alors que celui-ci s’équilibre autour de l’état de base.

Grâce à cela le traitement des données n’est pas perturbé par les manifestation de la stabilisation de l’énergie et profite de la perte inévitable d’énergie

	Les chercheurs ont prouvé qu’il était possible de réaliser des portes logiques grâce à ces automates cellulaires quantiques. Une porte NOT peut être créée en appliquant un offset entre deux chaînes de cellules. Une porte or ou and sera créée en liant deux chaînes de cellules et en appliquant de légères modifications à l’état de la cellule servant d'intersection entre les deux chaînes. Pour une porte OR on augmente légèrement l’énergie aux points 2 et 4. Tandis que pour une porte AND on réoriente la cellule vers l’état 0.

1.3 - Les problèmes restants à résoudre
		Il est très important que les points d’une même cellule soient quasiment parfaitement de la même taille. Si la variation de taille entre plusieurs points de la cellules est supérieure aux forces de coulomb impliquées alors la cellule se bloquera dans un état et n’aura pas les propriétés quantiques souhaitées. 

	Une autre difficulté est l’uniformité de l’occupation des cellules. Il est impératif qu’il y ait exactement deux électrons dans la cellule. Il se trouve que ce problème est facilement réglé et qu’on peut maintenir cette uniformité sur en moyenne des matrices de 10^8 points.

	La température est aussi un problème pour l’instant. Nos technologies nous permettent de créer des points d'une certaine taille or pour atteindre les propriétés désirées il faut faire baisser la température à celle de l’hélium liquide, c'est-à-dire 4,2 K ou -269°C. Cependant ce problème sera réglé par les avancées scientifiques futures qui permettront de fabriquer des points plus petits, de l’ordre de quelques nanomètres. Le fait de réduire les points à une taille si infinitésimale permettra de faire remonter la température nécessaire afin qu’elle soit plus facilement atteignable.

1.4 - Les opportunités
		Les chercheurs assurent que si les automates cellulaires quantiques sont un succès ils seront plus une révolution qu’une évolution. En effet, ils marqueraient un détachement de l’électronique traditionnelle.
L’un des plus grands obstacles au progrès dans l'électronique est le câblage, or ce problème est réglé par les automates cellulaires quantiques.”Les interconnections ne sont plus nécessaires afin de permettre la communication entre les cellules”,”Les interactions de coulomb suffisent à remplir cette tâche"
De plus, le fait que le système soit commandé par les bords implique que les cellules intérieures n’ont besoin ni d’énergie ni d’information.

On peut aussi noter le fait que cette technologie serait bien plus dense que les technologies actuelles. Les ordinateurs utilisant cette technologie seraient donc bien plus compacts et bien plus performants.



















CONCLUSION

CONCLUSION TECHNIQUE 

Les automates cellulaires représentent un secteur de recherche extrêmement vaste qui peut être utilisé dans énormément de secteurs. Ces systèmes complexes partant de règles simples pourraient permettre de modéliser beaucoup de différents systèmes que ce soit une foule ou une culture de bactéries, peut être même l’univers. Il reste cependant beaucoup de progrès à faire dans le domaine et les automates cellulaires quantiques pourraient s'avérer nous faire avancer prodigieusement dans ce secteur.











BIBLIOGRAPHIE

ARTICLES ENCYCLOPÉDIQUES :

Automates céllulaires : wikipedia.org Automate cellulaire
  wikipedia.org Cellular automaton
	  wikipedia.org Von Neumann universal constructor 

John H. Conway : wikipedia.org John Horton Conway 

John Von Neumann : wikipedia.org John von Neumann

Stephen Wolfram : wikipedia.org Stephen Wolfram

Jeu de la vie : wikipedia.org Jeu de la vie
           wikimonde.com Vaisseau automate cellulaire
           wikibooks.org Jeu de la vie Vaisseau
           dictionnaire.sensagent.leparisien.fr Vaisseau automate cellulaire

Fourmi de Langton : fr.wikipedia.org Fourmi_de_Langton

Machine de Turing : wikipedia.org Machine_de_Turing
         wikipedia.org Turing-complet

SITES INTERNET:
Automates cellulaires : Introduction aux automates cellulaires | Spiria

Jeu de la vie : science étonnante le jeu de la vie
		automatescellulairestpe.wordpress.com

Automates cellulaires en musique : Automates cellulaires – MusicAlgo
         
PDF DE RECHERCHE :
Automates cellulaires quantiques : iopscience les automates cellulaires quantiques
Comportements typiques des automates cellulaires : PDF_automate_techingé

PROGRAMMES ET MODULES PYTHON:
Module Tkinter python ( base du Jeu de la Vie ) : https://python.doctor tutoriel python

Tetris en jeu de la vie : stackexchange game of tetris in conways game of life



LISTE DES FIGURES

Figure 1 : Automate Universel

Figure 2 : Motif d’un planeur 

Figure 3 : Automate additif 

Figure 4 : Planeur

Figure 5 : Canon à planeur position initiale
 
Figure 5.5 : Feu de Forêt

Figure 6 : Exemple Jeu de la Vie (a)

Figure 7 : Exemple Jeu de la Vie (b)

Figure 8 : Exemple Jeu de la Vie ( c)

Figure 9 : Exemple Jeu de la Vie (d)

Figure 10 : Exemple Jeu de la Vie (e)

Figure 11 : Motif Initial LWSS

Figure 12 : Cycle LWSS

Figure 13 : Automate cellulaire généré avec la 90ème règle de Wolfram

Figure 14 : Mesures musicales en fonction d’automates cellulaires

Figure 15 : Cellules quantiques 






ANNEXES
Pour lire le code qui suit , on peut zoomer avec CTRL  SHIFT + 
Sinon le code est téléchargeable : code python
Code du Jeu de la Vie classique :



Code du jeu de la vie modifié /Vaisseau LWSS :







Code du Jeu de la Vie modifié / Canon à planeur  :


























Mots-clés :
Automates cellulaires, quantique, informatique, physique, musique, Turing complet , Jeu de la Vie , Règles de Wolfram

Keywords : 
Cellular automatons, quantum, computer science, physics, music, Turing complete , Game of life ,Wolfram rules



