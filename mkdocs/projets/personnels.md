projets personnels

# SenseHat-connected-clock

# Letter counter

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

# web_radio_share

# Diodon

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
