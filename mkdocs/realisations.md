# Mes réalisations

J'aime beaucoup programmer. C'est pourquoi souvent je fais de petits projets qui me permettent d'apprendre des choses.  
Que ce soit pour me familiariser à un langage, mettre en pratique un algorithme, ou tomber sur des problèmes que je ne soupçonnais pas, je
suis toujours ravis de découvrir de nouvelles choses.

## SenseHat connected clock

Le [SenseHat connected clock](https://github.com/Keftcha/SenseHat-connected-clock/) est un de mes premiers projets.  
J'ai eu l'idée d'initier ce projet car je voulais une petite horloge connectée et tant qu'à faire, autant la faire sois même !

Ce projet est en python et est aussi l'un des premiers avec lequel j'ai utilisé git. Il est relativement vieux et je m'efforce de faire
un code le plus propre possible car je ne développe pas fréquemment dessus. Je continue le développement de ce projet de manière très
irrégulière.

Je suis très content de ce projet car j'ai un retour direct de ce que j'ai fait. Ceci est dû au fait qu'il utilise le
[Sense HAT](https://www.raspberrypi.org/products/sense-hat/) du Rapsberry Pi. Ce projet est beaucoup moins abstrait que la plupart des
autre que j'ai pu faire.

Pour le développement de ce projet j'ai commencé par utiliser le simulateur inclus avec le système d'exploitation officiel du Rapsberry Pi.
Lorsque je suis arrivé aux limites de ce dernier, j'ai inverti dans l'équipement afin de continuer mon développement.

Aujourd'hui (le 19 mars 2021), je n'ai pas encore fini ce projet. Je suis très content et attaché à ce projet et je compte m'en servir un
jour bien qu'il soit très sommaire.

Je pense qu'avec le recul et mon expérience, je pourrai recommencer le projet pour qu'il intègre de nouvelles fonctionnalités et que le
développement soit plus facile.

## Letter counter

[Letter counter](https://github.com/albandewilde/letter_counter "Dépôt github") est un bot discord qui compte les caractères et messages que les
utilisateurs envoient.

Des [bots](https://fr.wikipedia.org/wiki/Bot_informatique "Bot Informatique - Wikipedia")
Discord qui font cela il en existe des quantités astronomiques car
fonctionnellement il est simple à implémenter.
Cependant j’ai développé ce bot car pour moi le but était de continuer de me
familiariser avec le Go et Docker.

Pendant le développement de cette application, j’ai rencontré un problème très
connu en informatique.  
Un jour je me suis rendu compte que certains caractères (tels que ¨ ou encode
§) étaient compté comme 2 par le programme. En me renseignant, je me suis rendu
compte que pour un ordinateur tous les caractères ne font pas la même taille
dans sa mémoire (cf. [cet article](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/ "site web de Joel Spolsky")).
C’est pourquoi certains caractères comptaient double, triple voir quadruple.
Au final, j’ai corrigé mon problème en utilisant le type de donnée appropriée
(rune en Go).

Je suis content de ce projet bien qu’il ne soit pas très ambitieux ou même
utile. Je retiens beaucoup sur les chaines de caractères en informatique qui
est en fait un problème très complexe. Ce que j’ai appris à ce sujet pendant ce
projet m’a permis de comprendre beaucoup de choses plus tard, notamment
certaines implémentations et mécaniques du Rust.

## Web Radio Share

Ce projet ([WRS](https://github.com/Keftcha/web_radio_share "Dépôt github")) a été
initié dans le but de partager la musique que l'on écoute.  
Cependant, pour moi, le but principal était de me familiariser avec la mise en pratique d'un serveur http
en Go avec la librairie standard. J'ai aussi profité de ce projet pour me familiariser avec le *templating*
que permet le même langage.  
Ce projet m'a permis aussi de perfectionner ma pratique de docker.

On peut comparer ce que fait le package de la librairie standard de Go
([net/http](https://golang.org/pkg/net/http/ "Package http")) à ce que font des librairies comme
[Flask](https://flask.palletsprojects.com/en/1.1.x/) ou encore [Bottle](https://bottlepy.org/docs/dev/) en Python.  
Ayant déjà utilisé *Bottle* plusieurs fois, la ressemblance me semblait forte. J'ai pu apprendre beaucoup,
notamment sur les idiomes de Go.

C'est aussi pendant ce projet que je me suis mis à préférer Go à Python. À la fois pour sa simplicité de développement,
que pour tout l'environnement et les outils qu'il nous met à disposition.

## Diodon

[Diodon](https://github.com/Keftcha/diodon "Dépôt github") est, lui aussi, un
bot discord. Son but est d'apprendre des messages des utilisateurs pour
qu'ensuite il fasse ses propres phrases.

Pour l'apprentissage et la génération des phrases construites par le bot j'ai
utilisé une [chaîne de Markov](https://fr.wikipedia.org/wiki/Chaîne_de_Markov "Chaîne de Markov - Wikipedia").  
J'ai fait le choix d'utiliser ce processus car il est simple à implémenter et
correspond à mon besoin.

En voulant manipuler les données (sauvegarder et réutiliser les mots des
phrases) je suis tombé sur un problème courant de l'informatique, la mutation
concurrente des données (*Data race*).  
Mes données sont sauvegardées dans un json ou un *map* (structure de données en
Go). Cependant, la partie écrivant et lisant les données est asynchrone.
L'asynchronisme a beaucoup d'avantage, cependant pour un accès à des données
il faut l'éviter.  
Pour pallier ce problème j'ai utilisé une [exclusion mutuelle](https://fr.wikipedia.org/wiki/Exclusion_mutuelle "Mutex - Wikipedia").
Le principal danger des mutex est **l'interblocage**. C'est-à-dire qu'un
processus attend l'accès à une ressource verrouillé tandis qu'un autre processus attend
que le premier ait fini pour libérer ladite ressource.

Je suis content de ce projet car après plusieurs mois d'apprentissage le bot
fait maintenant des phrases très marrantes. De plus, j'ai appris sur les chaînes
de Markov ainsi que certains effets collatéraux de l'asynchrone et comment s'en
prévenir.
