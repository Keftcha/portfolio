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
