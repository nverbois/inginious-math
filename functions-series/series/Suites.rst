| Cours de mahématiques de cinquième année
  4 périodes/semaine
  Année 2018-2019
| Lycée Martin V

1. Introduction
============

| 

  Combien fait :

  .. math:: 1+2+3+...+98+99+100~~?

  Selon la légende, Johann Carl Friedrich Gauss, un des plus grands
  mathématiciens de l’histoire, aurait donné la réponse à cette question
  après seulement 10 secondes alors qu’il avait 10 ans. À son époque,
  les calculatrices n’existaient même pas : comment est-il parvenu à
  réaliser cet exploit ? A-t-il véritablement calculé mentalement cette
  longue somme en moins de 10 secondes ?
| Contrairement à ce que de nombreuses personnes pensent, les
  mathématiques et le calcul sont deux choses bien différentes. En fait,
  un des buts des mathématiciens est souvent de réfléchir à la meilleur
  manière d’aborder un problème de telle sorte à avoir à réaliser le
  moins de calculs possibles. Si la légende est vraie, Gauss n’a
  certainement pas effectué mentalement cette somme en moins de 10
  secondes : il a très probablement utilisé ce que nous désignons
  aujourd’hui comme la méthode (et la formule) pour calculer la somme
  d’un nombre choisi de termes consécutifs d’une suite arithmétique,
  méthode que nous allons découvrir dans ce chapitre.
|  
| Ce chapitre est dédié aux suites, un outil simple qui permet de
  s’entraîner à la manipulation d’outils formels, de formaliser certains
  problèmes de façon efficace ou encore de comprendre la différence
  entre intérêts simples et intérêts composés. Dans ce cours, ce
  chapitre qui est de loin le plus facile de l’année sert également à
  donner le temps nécessaire à ceux qui en ont besoin pour se remettre à
  niveau.
|  
| Pour cette raison, les difficultés de ce chapitre ont été écartés [1]_
  et les prérequis ont été réduit au maximum. Il reste néanmoins
  souhaitable :

-  D’être à l’aise avec le formalisme de base des fonctions.

-  D’être capable de résoudre des problèmes (dont la difficulté
   correspond aux problèmes étudiés en quatrième année).

| Le chapitre de rappels et compléments est là pour vous aider à combler
  d’éventuels lacunes. N’hésitez pas à aller jeter (à nouveau) un œil
  sur la partie consécrée aux fonctions un peu plus tôt que prévu si
  vous percevez que cela est nécessaire.
|  
| Il est à noter que ce chapitre est volontairement incomplet dans le
  sens où une partie de la matière a été indiquée comme optionnelle. En
  effet, cette partie optionnelle correspond principalement à une
  manière spécifique d’introduire la complexe notion de limite. Nous
  avons choisi d’introduire celle-ci d’une autre façon, que nous
  découvrirons dans le chapitre suivant. Néanmoins, cette partie
  optionnelle est très intéressante en soi et peut (grandement) aider à
  comprendre la notion de limite par après. Pour cette raison, je vous
  invite vivement à la lire durant les vacances de Toussaint.

2 Suites
======

Dans cette section, nous allons introduire la notion de suite. Une suite
(de nombres) n’est rien d’autre qu’une succession infinie indexée (par
les nombres naturels) de nombres.

2.1 Définitions
-----------

.. |nbsp| unicode:: 0xA0 
   :trim:


**Définition 2.1.1.** |nbsp| Une *suite* est une fonction de :math:`\mathbb{N}` dans
:math:`\mathbb{R}` : :math:`f : \mathbb{N}\to \mathbb{R}`.

**Exemple 2.1.2.** Les fonctions suivantes :

.. math::

   \begin{aligned}
       f : \mathbb{N}&\to \mathbb{R}\\
       n &\mapsto 2
       \end{aligned}

et

.. math::

   \begin{aligned}
       g : \mathbb{N}&\to \mathbb{R}\\
       n &\mapsto 2+ \frac{1}{n+1}
       \end{aligned}

sont deux suites dont les termes sont :math:`2,2,2,2,2,2,...` et
:math:`2+ \frac{1}{1},2+ \frac{1}{2},2+ \frac{1}{3},2+ \frac{1}{4},2+ \frac{1}{5},...`.
On ne peut évidemment pas donner tous les termes de ces deux suites : il
y en a une infinité.

**Contre-exemple 2.1.3.** La fonction

.. math::

   \begin{aligned}
       f : \mathbb{R}&\to \mathbb{R}\\
       x &\mapsto x^2
       \end{aligned}

n’est pas une suite.

| 

**Notation.** Les lettres :math:`s,t,u,v` sont souvent utilisées pour les suites.
Plutôt que d’écrire :math:`s : \mathbb{N}\to \mathbb{R}` pour déclarer
une suite, on écrit souvent :math:`{(s_n)}_{n \in \mathbb{N}}`. Plutôt
que d’écrire :math:`s(n)`, ce qui est souvent nommé terme de rang
:math:`n` de la suite :math:`s`, on écrit souvent :math:`s_n`. Dans ce
document, nous reprendrons ces conventions communément admises.

**Remarque 2.1.4.** Comme pour les fonctions, il est possible de représenter les suites dans
un graphe orthonormé. Par exemple, la suite

.. math::

   \begin{aligned}
       g : \mathbb{N}&\to \mathbb{R}\\
       n &\mapsto 2+ \frac{1}{n+1}
       \end{aligned}

a le graphe suivant :

.. tikz:: 

		\draw[step=1cm,gray,very thin] (0,0) grid (5,5);

		\draw[very thick,->] (0,0) -- (5,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,0) -- (0,5) node[anchor=south west] {y};
		
		\foreach \x in {0,1,2,3,4,5}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};
		\draw[very thick,blue] (0,2+0.7) node[anchor=south] {\large{$\bullet$}};
		\draw[very thick,blue] (1,2+0.2) node[anchor=south] {\large{$\bullet$}};
		\draw[very thick,blue] (2,2+0.0333333) node[anchor=south] {\large{$\bullet$}};
		\draw[very thick,blue] (3,2-0.05) node[anchor=south] {\large{$\bullet$}};
		\draw[very thick,blue] (4,2-0.1) node[anchor=south] {\large{$\bullet$}};
		\draw[very thick,blue] (5,2-0.13) node[anchor=south] {\large{$\bullet$}};
		\foreach \y in {0,1,2,3,4,5}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};

Attention à ne pas relier les points du graphe ! Dans le cas des suites,
le domaine de définition est :math:`\mathbb{N}`, pas :math:`\mathbb{R}`
!

| Il y a deux manières de définir une suite particulière. On peut la
  définir comme une fonction : c’est ce qui a été fait à l’exemple 2.1.2. Dans ce cas, on dit qu’on donne la suite
  *en fonction du rang* puisqu’on possède alors une formule qui nous
  permet de calculer directement le terme de rang :math:`n` de la suite
  (:math:`n` étant un nombre naturel choisi).
| Mais il existe une autre manière de déclarer une suite, dite *par
  récurrence*. Celle-ci consiste à donner le ou les premiers termes de
  la suite, puis donner une règle générale permettant de calculer tous
  les termes suivants à partir de ce ou ces premiers termes. Plutôt que
  de donner la définition générale et abstraite de suite définie par
  récurrence (qui est assez technique), donnons un exemple très connu de
  suite définie par récurrence : la suite de Fibonacci.

| 

**Exemple 2.1.5.** 

  La suite de Fibonacci est l’unique suite :math:`{(F_n)}_{n \in \mathbb{N}}` telle que :
  
  .. math::

     \left\{
         \begin{array}{l}
         F_0 = 1 \\
         F_1 = 1 \\
         F_{n+2} = F_{n+1} + F_{n} ~~~~~~ n \in \mathbb{N}
         \end{array}
         \right.

  Autrement dit, on donne les deux premiers termes de la suite,
  :math:`F_0 =1` et :math:`F_1 = 1`, et la règle générale nous dit ici
  que pour obtenir un terme de la suite, il suffit d’additionner les
  deux précédents. Par exemple, que vaut le terme de rang :math:`2` de
  la suite, c’est-à-dire :math:`F_2` ? En prenant :math:`n=0` dans la
  formule générale, on sait qu’on doit avoir pour la suite
  :math:`{(F_n)}_{n \in \mathbb{N}}` :

  .. math:: F_{0+2} = F_{0+1} + F_{0}

  Autrement dit :

  .. math:: F_{2} = F_{1} + F_{0}

  Donc :

  .. math:: F_{2} = 1 + 1 = 2

  Puisqu’on connait :math:`F_2`, on peut alors particulariser la formule
  générale non plus en :math:`n=0` mais en :math:`n=1` pour découvrir
  comment calculer :math:`F_3` à partir de :math:`F_2` et :math:`F_1` :

  .. math:: F_{3} = F_{2} + F_{1} = 2+1=3

  Et ainsi de suite. On peut calculer que les premiers termes de la
  suite de Fibonacci sont :math:`1,1,2,3,5,8,13,21,34,...`.
|   
| La suite de Fibonacci est fascinante et très populaire car elle
  apparaît spontanément dans la nature, que ce soit dans les fleurs de
  tournesol ou dans les coquilles de certains mollusques. De plus, elle
  est reliée à un nombre qui a eu autrefois énormément d’importance en
  architecture et en art : le nombre d’or. Malheureusement, nous n’avons
  pas la possibilité dans ce cours de nous étendre sur le sujet.

L’exemple de la suite de Fibonacci comprend toute la généralité
nécessaire pour manipuler les suites définies par récurrence que nous
rencontrerons. La plupart du temps, seul le premier terme de la suite
est donné et la règle générale de récurrence ne dépent seulement que
d’un seul terme (contrairement au cas de la suite de Fibonacci, où elle
dépend de deux termes (:math:`F_{n+1}` et :math:`F_n`)).

**Remarque 2.1.6.** Une suite définie en fonction du rang est souvent plus facile à
manipuler qu’une suite donnée par récurrence, mais il est parfois plus
facile de définir une suite par récurrence.

Dans les deux sections suivantes, nous allons étudier deux types de
suites pour lesquels il est aisé de passer de la formulation en fonction
du rang à la formulation par récurrence et vice-versa.

| 

**Exemple 2.1.7.** Soit :math:`{(s_n)}_{n \in \mathbb{N}}` une suite telle que :

#. :math:`s_n = n^3 -n +1`        :math:`(n \in \mathbb{N})`

#. :math:`s_n = \frac{2}{\sqrt{n+1}}`        :math:`(n \in \mathbb{N})`

#. :math:`\left\{\begin{array}{l}s_0 = 1 \\s_1 = 2 \\s_{n+2} = F_{n+1} + 2s_{n} - 6 ~~~~~~ n \in \mathbb{N}\end{array}\right.`

#. :math:`\left\{\begin{array}{l}s_0 = -2 \\s_{n+1} = \frac{1}{4}(s_{n})^3 +4 ~~~~~~ n \in \mathbb{N}\end{array}\right.`

#. :math:`s_n = \frac{1}{5^{n-1}}`        :math:`(n \in \mathbb{N})`

Pour chacune de ces possibilités :

-  Calculer :math:`s_0`, :math:`s_1` et le terme de rang :math:`3`.

-  Représenter graphiquement les premiers termes de la suite.

.. inginious:: suite1_1
.. inginious:: suite1_2
.. inginious:: suite1_3
.. inginious:: suite1_4
.. inginious:: suite1_5

| 

2.2 Suites arithmétiques
--------------------

| Considérons les trois suites dont les premiers termes sont :

| :math:`0,1,2,3,4,5,...`
| :math:`-5,-5+\frac{1}{3},-5+\frac{2}{3},-4,-4+\frac{1}{3},-4+\frac{1}{3},...`
| :math:`11,9,7,5,3,1,-1,-3,...`

| Elles ont un point commun : pour passer d’un terme au suivant, on
  ajoute toujours un même nombre. Pour la première suite, ce nombre est
  :math:`1`, pour la deuxième, ce nombre est :math:`\frac{1}{3}`, pour
  la troisième, ce nombre est :math:`-2`. C’est le principe qui définit
  les suites arithmétiques.

| 

**Définition 2.2.1.** 

  Une *suite arithmétique* est une suite :math:`{(s_n)}_{n \in \mathbb{N}}` telle que :
  
  .. math::

     \left\{
         \begin{array}{l}
         s_0 = a \\
         s_{n+1} = s_{n} + r ~~~~~~ n \in \mathbb{N}
         \end{array}
         \right.

  où :math:`a \in \mathbb{R}` est le *terme initial* et
  :math:`r \in \mathbb{R}` est la *raison* (ce qu’on ajoute pour passer
  d’un terme au suivant).

| 

**Exemple 2.2.2.** La suite dont les premiers termes sont :math:`11,9,7,5,3,1,-1,-3,...`
est une suite arithmétique de terme initial :math:`a=11` et de raison
:math:`r=-2`.

**Remarque 2.2.3.** Puisque pour passer d’un terme au suivant dans une suite arithmétique,
il suffit d’ajouter la raison, les termes successifs d’une suite
arithmétique de terme initial :math:`a \in \mathbb{R}` et de raison
:math:`r \in \mathbb{R}` peuvent être notés :

.. math:: a,a+1.r,a+2.r,a+3.r,a+4.r,a+5.r,...

Il n’est dès lors pas surprenant qu’on puisse démontrer qu’une suite
arithmétique de terme initial :math:`a \in \mathbb{R}` et de raison
:math:`r \in \mathbb{R}` est égale à la suite :

.. math::

   \begin{aligned}
       f : \mathbb{N}&\to \mathbb{R}\\
       n &\mapsto a + r.n
       \end{aligned}

Ce qui correspond à la définition de cette suite en fonction du rang.

**Exemple 2.2.4.** La suite dont les premiers termes sont :math:`11,9,7,5,3,1,-1,-3,...`
est une suite arithmétique de terme initial :math:`a=11` et de raison
:math:`r=-2`. Elle est égale à la suite :

.. math::

   \begin{aligned}
       f : \mathbb{N}&\to \mathbb{R}\\
       n &\mapsto 11 + (-2).n
       \end{aligned}

Et en effet, on calcule : :math:`f(0)=11+(-2).0 = 11`,
:math:`f(1)=11+(-2).1 = 9`, :math:`f(2)=11+(-2).2 = 7`,
:math:`f(3)=11+(-2).3 = 5`, ...

| 

**Exercice 2.2.5.** Soit :math:`{(s_n)}_{n \in \mathbb{N}}` une suite arithmétique telle que
:

#. :math:`a=-1` et :math:`r=-7`

#. :math:`s_0 = 2` et :math:`s_1 = 5`

#. :math:`\left\{\begin{array}{l}s_0 = -\frac{1}{2} \\s_{n+1} = s_{n} + \frac{3}{2} ~~~~~~ n \in \mathbb{N}\end{array}\right.`

#. :math:`s_n = 3n`        :math:`(n \in \mathbb{N})`

#. :math:`s_4 = 15` et :math:`s_{31} = 20 + \frac{2}{5}`

Pour chacune de ces possibilités, calculer :math:`a`, :math:`r` et le
terme de rang :math:`20`.

.. inginious:: suite2_1
.. inginious:: suite2_2
.. inginious:: suite2_3
.. inginious:: suite2_4
.. inginious:: suite2_5

| 

**Exercice 2.2.6.** Soit :math:`{(s_n)}_{n \in \mathbb{N}}` une suite telle que :

#. :math:`s_n = 3^0`        :math:`(n \in \mathbb{N})`

#. :math:`\left\{\begin{array}{l}s_0 = 1 \\s_{n+1} = 2s_{n} + \frac{3}{2} ~~~~~~ n \in \mathbb{N}\end{array}\right.`

#. :math:`\left\{\begin{array}{l}s_0 = 1 \\s_1 = 2 \\s_{n+2} = s_{n+1} + s_{n} - 6 ~~~~~~ n \in \mathbb{N}\end{array}\right.`

#. :math:`\left\{\begin{array}{l}s_0 = 0 \\s_{n+1} = s_{n} . 3 ~~~~~~ n \in \mathbb{N}\end{array}\right.`

Pour chacune de ces possibilités, déterminer s’il s’agit d’une suite
arithmétique.

.. inginious:: suite3_1
.. inginious:: suite3_2
.. inginious:: suite3_3
.. inginious:: suite3_4

| 

**Exercice 2.2.7.** 

.. inginious:: suite4

| 

2.3 Suites géométriques
-------------------

| Considérons les trois suites dont les premiers termes sont :

| :math:`1,2,4,8,16,32,...`
| :math:`10,-10,10,-10,10,...`
| :math:`81,27,9,3,1,\frac{1}{3},\frac{1}{9},...`

| Elles ont un point commun : pour passer d’un terme au suivant, on
  multiplie toujours par un même nombre. Pour la première suite, ce
  nombre est :math:`2`, pour la deuxième, ce nombre est :math:`-1`, pour
  la troisième, ce nombre est :math:`\frac{1}{3}`. C’est le principe qui
  définit les suites géométriques.

**Définition 2.3.1.**  

  Une *suite géométrique* est une suite :math:`{(s_n)}_{n \in \mathbb{N}}` telle que :

  .. math::

     \left\{
         \begin{array}{l}
         s_0 = b \\
         s_{n+1} = s_{n} . q ~~~~~~ n \in \mathbb{N}
         \end{array}
         \right.

  où :math:`b \in \mathbb{R}` est le *terme initial* et
  :math:`q \in \mathbb{R}` est la *raison* (ce par quoi on multiplie
  pour passer d’un terme au suivant).

| 

**Exemple 2.3.2.** La suite dont les premiers termes sont
:math:`81,27,9,3,1,\frac{1}{3},\frac{1}{9},...` est une suite
géométrique de terme initial :math:`b=81` et de raison
:math:`q=\frac{1}{3}`.

**Remarque 2.3.3.** Puisque pour passer d’un terme au suivant dans une suite géométrique, il
suffit de multiplier par la raison, les termes successifs d’une suite
géométrique de terme initial :math:`b \in \mathbb{R}` et de raison
:math:`q \in \mathbb{R}` peuvent être notés :

.. math:: b,b.q,b.q^2,b.q^3,,b.q^4,b.q^5,...

Il n’est dès lors pas surprenant qu’on puisse démontrer qu’une suite
géométrique de terme initial :math:`b \in \mathbb{R}` et de raison
:math:`q \in \mathbb{R}` est égale à la suite :

.. math::

   \begin{aligned}
       f : \mathbb{N}&\to \mathbb{R}\\
       n &\mapsto b.q^n
       \end{aligned}

Ce qui correspond à la définition de cette suite en fonction du rang.

**Exemple 2.3.4.** La suite dont les premiers termes sont
:math:`81,27,9,3,1,\frac{1}{3},\frac{1}{9},...` est une suite
arithmétique de terme initial :math:`b=81` et de raison
:math:`q=\frac{1}{3}`. Elle est égale à la suite :

.. math::

   \begin{aligned}
       f : \mathbb{N}&\to \mathbb{R}\\
       n &\mapsto 81 . (\frac{1}{3})^n
       \end{aligned}

Et en effet, on calcule : :math:`f(0)=81 . (\frac{1}{3})^0 = 81`,
:math:`81 . (\frac{1}{3})^1 = 27`, :math:`81 . (\frac{1}{3})^2 = 9`,
:math:`81 . (\frac{1}{3})^3 = 3`, ...

| 

**Exercice 2.3.5.** Soit :math:`{(s_n)}_{n \in \mathbb{N}}` une suite géométrique telle que
:

#. :math:`b=1` et :math:`q=-2`

#. :math:`s_0 = 2` et :math:`s_1 = 6`

#. :math:`\left\{\begin{array}{l}s_0 = -27 \\s_{n+1} = s_{n} . \frac{1}{3} ~~~~~~ n \in \mathbb{N}\end{array}\right.`

#. :math:`s_n = (\frac{1}{5})^n`        :math:`(n \in \mathbb{N})`

#. :math:`s_4 = \frac{7}{16}` et :math:`s_{10} = 28`

Pour chacune de ces possibilités, calculer :math:`b`, :math:`q` et le
terme de rang :math:`6`.

.. inginious:: suite5_1
.. inginious:: suite5_2
.. inginious:: suite5_3
.. inginious:: suite5_4
.. inginious:: suite5_5

| 

**Exercice 2.3.6.** Soit :math:`{(s_n)}_{n \in \mathbb{N}}` une suite telle que :

#. :math:`s_n = 4^0`        :math:`(n \in \mathbb{N})`

#. :math:`\left\{\begin{array}{l}s_0 = 1 \\s_{n+1} = 2s_{n} + \frac{3}{2} ~~~~~~ n \in \mathbb{N}\end{array}\right.`

#. :math:`\left\{\begin{array}{l}s_0 = -1 \\s_1 = 1 \\s_{n+2} = s_{n+1} + 2s_{n} ~~~~~~ n \in \mathbb{N}\end{array}\right.`

#. :math:`\left\{\begin{array}{l}s_0 = 0 \\s_{n+1} = s_{n} + s_0 ~~~~~~ n \in \mathbb{N}\end{array}\right.`

Pour chacune de ces possibilités, déterminer s’il s’agit d’une suite
géométrique.

.. inginious:: suite6_1
.. inginious:: suite6_2
.. inginious:: suite6_3
.. inginious:: suite6_4

| 

**Exercice 2.3.7.** 

.. inginious:: suite7

| 

2.4 Intérêts simples et intérêts composés
-------------------------------------

**Problème** Considérons le problème suivant : nous disposons de :math:`100`\ € et
nous avons la possibilité de déposer ces :math:`100`\ € sur un compte
d’une première banque qui nous propose des intérêts mensuels de
:math:`1` % de la somme initiale déposée sur le compte (c’est-à-dire,
dans notre cas, :math:`100`\ €) ou sur un compte d’une seconde banque
qui elle nous propose des intérêts mensuels de :math:`0,5` % de la
somme présente sur le compte ce mois-là, somme qui évolue donc chaque
mois. En supposant que nous allons laisser l’argent sur le compte
pendant :math:`12` mois, sans y toucher ni y ajouter quelque chose,
quelle est la banque la plus avantageuse (pour nous) ?


Commençons par donner la suite des sommes d’argent dont nous
disposerons après les premiers mois si nous choisissons la première
banque : après :math:`1` mois, nous disposerons de
:math:`100 + 0,01 . 100 = 101`\ €. Après :math:`2` mois, nous
disposerons de :math:`101 + 0,01 . 100 = 102`\ €. Et ainsi de suite :
on remarque qu’on a affaire à une suite arithmétique de terme initial
:math:`a=100` et de raison :math:`1`. Après :math:`12` mois, nous
disposerons donc de :math:`100 + 12 . 1 = 112`\ €.


Passons au cas de la deuxième banque. Après le premier mois, nous
disposerons de
:math:`100 + 0,005 . 100 = 100 . (1 + 0,005) = 100 . 1,005 = 100,5`\ €.
Après le deuxième mois, nous disposerons de
:math:`100,5 + 0.005 . 100,5 = 100,5 . (1 + 0,005) = 100,5 . 1,005 = 101,0025`\ €.
Et ainsi de suite : on remarque qu’on a affaire à une suite
géométrique de terme initial :math:`b=100` et de raison :math:`1,005`.
Après :math:`12` mois, nous disposerons donc de
:math:`100 . (1,005)^{12} \simeq 106,17`\ €.


Conclusion : la première banque est la plus intéressante. Néanmoins,
ce ne sera pas éternellement le cas : puisque les intérêts de la
seconde banque grandissent sans cesse et de plus en plus vite, il est
clair que sur le plus long terme (pouvez-vous déterminer à partir de
combien de mois ?), la seconde banque est plus intéressante.

Les intérêts que propose la première banque sont ce qu’on appelle des
*intérêts simples*, tandis que ceux que propose la seconde banque sont
ce qu’on appelle des *intérêts composés*. Il est important de se
souvenir que les intérêts simples correspondent à une suite
arithmétique, tandis que les intérêts composés correspondent à une suite
géométrique.

| 

**Exercice 2.4.1.** 

.. inginious:: suite8

2.5 Sommes de suites
----------------

Dans cette section, nous allons découvrir les méthodes et formules pour
la somme des :math:`k` premiers termes d’une suite arithmétique ou
géométrique donnée, où :math:`k` est un nombre naturel choisi. Mais
commençons par l’exemple de l’introduction :

| **Exemple 2.5.1.** Que vaut :math:`1+2+3+...+49+50+51+...+98+99+100` ?
| Bien entendu, nous pourrions commencer à calculer cette somme en
  additionnant successivement tous les termes. Néanmoins, cette méthode
  serait quelque peu longue et pénible. Voici une autre méthode : on
  peut grouper les termes de la sommes deux-à-deux, :math:`1` avec
  :math:`100`, :math:`2` avec :math:`99`, :math:`3` avec :math:`98`, ...
  , :math:`50` avec :math:`51`. Toutes ces paires donnent :math:`101` et
  il y a :math:`50` paires. On en déduit que :

  .. math:: 1+2+3+...+49+50+51+...+98+99+100  = 101 . 50 = 5050

  Cette simple idée va nous permettre de démontrer la formule pour la
  somme des :math:`k` (:math:`k\in \mathbb{N}`) premiers termes d’une
  suite arithmétique.

| 

**Proposition 2.5.2.** Soit :math:`{(s_n)}_{n \in \mathbb{N}}` une suite
arithmétique de terme initial :math:`a \in \mathbb{R}` et de raison
:math:`r \in \mathbb{R}`. Choisissons un nombre
:math:`k \in \mathbb{N}`. Notons la somme des termes de la suite
:math:`{(s_n)}_{n \in \mathbb{N}}` pour les rangs de :math:`0` à
:math:`k` de la façon suivante :

.. math:: \sum\limits_{i=0}^{k} s_i = s_0 + s_1 + s_2 + ... + s_{k-2} + s_{k-1} + s_k

Alors on a :

.. math:: \sum\limits_{i=0}^{k} s_i = \frac{(2a + k r)(k+1)}{2}

*Démonstration* Puisque :math:`{(s_n)}_{n \in \mathbb{N}}` une suite arithmétique de
terme initial :math:`a \in \mathbb{R}` et de raison
:math:`r \in \mathbb{R}`, on a pour :math:`i \in \mathbb{N}` :
:math:`s_i = a + i  r`. Dès lors :

.. math:: \sum\limits_{i=0}^{k} s_i = a + (a+r)  + (a+2r) + ... + (a+(k-2)r) + (a+(k-1)r) + (a+kr)

On peut écrire cette somme dans l’autre sens :

.. math:: \sum\limits_{i=0}^{k} s_i = (a+kr) + (a+(k-1))r  + (a+(k-2)r) ... + (a+2r) + (a+r) + a

Additionnons les deux égalités précédentes et groupons ensemble le
premier terme de la somme du membre de droite de la première égalité
avec le premier terme de la somme du membre de droite de la deuxième
égalité, le deuxième terme de la somme du membre de droite de la
première égalité avec le deuxième terme de la somme du membre de droite
de la deuxième égalité, le troisième terme de la somme du membre de
droite de la première égalité avec le troisième terme de la somme du
membre de droite de la deuxième égalité et ainsi de suite :

.. math::

   \begin{aligned}
           2 \sum\limits_{i=0}^{k} s_i =& [a+(a+kr)] + [(a+r)+(a+(k-1))r]  + [(a+2r)+(a+(k-2)r)] + {}... \\
           &{}+ [(a+(k-2)r)+(a+2r)] + [(a+(k-1))r+(a+r)] + [(a+kr)+a]
       \end{aligned}

On observe que tous ces rassemblements donnent le même résultat :
:math:`2a+kr`. Ces rassemblements sont au nombre de :math:`k+1`, on a
donc :

.. math:: 2 \sum\limits_{i=0}^{k} s_i =(2a + k  r)(k+1)

Conclusion :

.. math:: \sum\limits_{i=0}^{k} s_i = \frac{(2a + k  r)(k+1)}{2}

| 

Nous avons une proposition similaire pour les suites géométriques :

**Proposition 2.5.3.** Soit :math:`{(s_n)}_{n \in \mathbb{N}}` une suite géométrique
de terme initial :math:`b \in \mathbb{R}` et de raison
:math:`q \in {\mathbb{R}} \backslash \{1\}`. Choisissons un nombre
:math:`k \in \mathbb{N}`. On a :

.. math:: \sum\limits_{i=0}^{k} s_i = b. \frac{1-q^{k+1}}{1-q}

*Démonstration* Puisque :math:`{(s_n)}_{n \in \mathbb{N}}` une suite géométrique de
terme initial :math:`b \in \mathbb{R}` et de raison
:math:`q \in \mathbb{R}`, on a pour :math:`i \in \mathbb{N}` :
:math:`s_i = bq^i`. Dès lors :

.. math:: \sum\limits_{i=0}^{k} s_i = b + (bi)  + (bi^2) + ... + (bq^{k-2}) + (bq^{k-1}) + (bq^{k})

On peut multiplier cette égalité par :math:`q` :

.. math:: q \sum\limits_{i=0}^{k} s_i = (bi)  + (bi^2) + (bi^3) ... + (bq^{k-1}) + (bq^{k}) + (bq^{k+1})

Soustrayons la deuxième égalité à la première en groupant ensemble le
deuxième terme de la somme du membre de droite de la première égalité
avec le premier terme de la somme du membre de droite de la deuxième
égalité, le troisième terme de la somme du membre de droite de la
première égalité avec le deuxième terme de la somme du membre de droite
de la deuxième égalité, le quatrième terme de la somme du membre de
droite de la première égalité avec le troisième terme de la somme du
membre de droite de la deuxième égalité et ainsi de suite :

.. math:: \sum\limits_{i=0}^{k} s_i - q \sum\limits_{i=0}^{k} s_i = b + [bi - bi] + [bi^2 - bi^2]   + ... + [bq^{k-1} - bq^{k-1}] + [bq^{k}-bq^{k}] - bq^{k+1}

On observe que tous ces rassemblements donnent le même résultat :
:math:`0`. On a donc :

.. math:: (1-q) \sum\limits_{i=0}^{k} s_i=b- bq^{k+1}

Puisque :math:`q \neq 1`, on conclut :

.. math:: \sum\limits_{i=0}^{k} s_i= \frac{b-bq^{k+1}}{1-q} = b. \frac{1-q^{k+1}}{1-q}

**Remarque 2.5.4.** Si on souhaite calculer la somme des termes d’une suite arithmétique ou
géométrique non pas à partir de :math:`0` mais à partir d’un autre
nombre naturel choisi, disons :math:`l`, il est possible de s’en sortir
facilement grâce aux formules des propositions
`[sommeari] <#sommeari>`__ et `[sommegéo] <#sommegéo>`__ puisque pour
une suite :math:`{(s_n)}_{n \in \mathbb{N}}`, on a :

.. math:: \sum\limits_{i=l}^{k} s_i = \sum\limits_{i=0}^{k}s_i - \sum\limits_{i=0}^{l-1}s_i

| 

**Exercice 2.5.5.**

.. inginious:: suite9_1
.. inginious:: suite9_2

| 

**Exercice 2.5.6.** 

.. inginious:: suite10_1
.. inginious:: suite10_2
.. inginious:: suite10_3
.. inginious:: suite10_4

| 

**Exercice 2.5.7.** 

.. inginious:: suite10_5
.. inginious:: suite10_6

| 

**Exercice 2.5.8.** 

.. inginious:: suite11

| 

3 Introduction aux limites de suites (optionnel)
==============================================

L’infini est une notion qui a intéressé et effrayé les hommes depuis
au moins la Grèce Antique. Manipulée de façon intuitive, cette notion
est difficile à cerner et peut mener à ce qu’on appelle des paradoxes,
des affirmations qui semblent défier la logique car ne pouvant être ni
vraies, ni fausses. C’est seulement au dix-neuvième siècle, grâce au
travail de Karl Weierstrass, que les mathématiciens sont parvenus à
formaliser correctement cette idée étrange qu’est l’infini. Cette
découverte est d’autant plus incroyable qu’elle a mené à la naissance
de l’analyse mathématique moderne, la branche des mathématiques qui
étudie les nombres (réels) et ce qu’il est possible de faire à l’aide
de ceux-ci.


Il est à noter que le travail de Georg Cantor, quelques années plus
tard, a permis d’étudier mathématiquement l’infini d’une autre manière
que ce que permet l’analyse. Néanmoins, nous ne pourrons
malheureusement pas aborder cet autre point de vue dans ce chapitre.
Pour commencer notre voyage vers la compréhension de l’infini,
intéressons-nous à quelques situations simples où l’infini semble
jouer un rôle et où un point de vue purement naïf et intuitif de cette
notion nous mène à de mystérieuses considérations.

3.1 0,999999... = 1 ?
-----------------

| Comment comparer les deux nombres :math:`0,99999...` (avec une
  infinité de chiffres :math:`9` derrière la virgule) et :math:`1`. Si
  le premier peut sembler plus petit que le second, les règles de
  transformation des nombres à virgules en fraction laisse à penser que
  non :

  .. math:: 0,999999... = \frac{9}{9} = 1

  Bien entendu, à ce stade, ces règles peuvent sembler complétement
  arbitraires. Néanmoins, remarquons qu’un peu de calcul algébrique
  audacieux nous fait arriver à la même conclusion :

  .. math:: x=0,999999...

  .. math:: 10x=9,999999...

  .. math:: 10x=9+0,999999...

  .. math:: 10x=9+x

  .. math:: 9x=9

  .. math:: x=1

  .. math:: 0,999999...=1

  Mais le passage de la première ligne à la deuxième pose question :
  s’il y a une infinité de chiffres :math:`9` derrière la virgule,
  peut-on vraiment dire que :math:`10.0,999999...=9,999999...` ?
|   
| On voit que cette infinité de chiffres après la virgule n’est pas si
  simple à interpréter. Alors qu’il s’agit d’une notation à laquelle de
  nombreuses personnes sont habituées (par exemple avec
  :math:`\frac{1}{3}=0,333333...`), il est inquiétant de constater que
  le sens de cette notation n’est pas sans équivoque. Cette notation est
  d’autant plus problématique qu’elle ouvre la porte à d’autres
  questions difficiles faisant intervenir l’infini, telles que
  :math:`0,999999...` est-il infiniment proche de :math:`1`, sans être
  égal à :math:`1` ? ou si :math:`0,999999...` est un nombre, qu’en
  est-il de :math:`...999999` ? .
|   
| Il semble clair que nous avons besoin de clarifier ce que nous
  entendons par cette infinité de chiffres après la virgule.

3.2 La division par 0
-----------------

| L’impossibilité de diviser par :math:`0` est parfois présentée comme
  une règle d’or des mathématiques. Mais finalement, pourquoi ne peut-on
  pas diviser par :math:`0` ? Essayons de braver cet interdit.
| Remarquons d’abord que plus on divise par quelque chose de petit, plus
  le résultat est grand :

  .. math:: 1 / \frac{1}{10} = 10

  .. math:: 1 / \frac{1}{100} = 100

  .. math:: 1 / \frac{1}{1000} = 1000

:math:`\vdots`

.. math:: 1 / \frac{1}{1000000000000} = 1000000000000

:math:`\vdots`

| Si on voulait attribuer une valeur à la division de, par exemple,
  :math:`1` par :math:`0`, il semble a priori raisonnable d’affirmer que
  le résultat de cette division doit être un nombre plus grand que tous
  les autres : :math:`\infty`.

  .. math:: \frac{1}{0} = \infty

  Cette idée pose cependant vite question. En effet, si :math:`\infty`
  est un nombre plus grand que tous les nombres, on devrait avoir :

  .. math:: \infty + 1 = \infty

  Mais alors, en soustrayant :math:`\infty` des deux côtés de l’équation
  :

  .. math:: 1=0

  Ce qui est assez problématique.
|   
| Autre complication : on peut également considérer que le résultat de
  :math:`2` par :math:`0` donne :math:`\infty`. Mais si
  :math:`\frac{1}{0} = \infty` et :math:`\frac{2}{0} = \infty`, on
  devrait avoir :math:`1 = 0.\infty` et :math:`2 = 0.\infty` et donc
  :math:`1=2`. En fait, si on considère intuitivement que le résultat de
  n’importe quel nombre strictement positif par :math:`0` doit donner
  :math:`\infty`, on peut montrer ainsi que :math:`1` est égal à
  n’importe quel nombre strictement positif !
|   
| Cette fois-ci, il semble clair que considérer naïvement l’infini comme
  un nombre (réel) nous mène à d’étranges résultats.

3.3 Le paradoxe de la flèche
------------------------

Ce paradoxe date d’il y a plus de :math:`2000` ans et est généralement
associé à Zénon, un Grec de la Grèce antique qui collectionnait les
paradoxes. Le paradoxe est connu comme le paradoxe de la flèche (ou le
paradoxe de l’archer) et a une variante faisant intervenir une tortue
et Achille (ou un lièvre). Nous allons donner ici la première version.
Imaginons un archer situé à une distance de :math:`1`\ dam de sa
cible. Lorsque l’archer va décocher une flèche, celle-ci va parcourir
la distance qui la sépare de la cible, jusqu’au moment où elle la
touchera, ce qui arrive en un temps fini.


Néanmoins, Zénon fait remarquer que la flèche, avant d’atteindre la
cible, devra d’abord parcourir la moitié de la distance qui la sépare
de la cible. De plus, une fois que la flèche aura parcouru cette
première moitié de la distance qui la sépare de la cible (une distance
de :math:`\frac{1}{2}`\ dam), la flèche devra d’abord parcourir la
moitié de la distance restante (c’est-à-dire
:math:`\frac{1}{4}`\ dam). Ensuite, à nouveau, la flèche devra d’abord
parcourir la moitié de la distance restante (c’est-à-dire
:math:`\frac{1}{8}`\ dam). Et ainsi de suite sans qu’il arrive un
moment où la distance qui sépare la flèche de la cible soit nulle !
Puisque la flèche devrait parcourir une infinité de distances, Zénon
en conclut qu’il lui faudrait un temps infini pour arriver à la cible.
Néanmoins, Zénon est bien conscient que s’il réalise l’expérience...
la flèche touchera la cible. C’est un paradoxe.

 
  Si on souhaite formuler un peu plus mathématiquement le paradoxe, on
  peut le faire comme suit. L’intuition physique nous dit que :

  .. math:: \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16} + \frac{1}{32} + ... = 1

  Tandis que l’argument de Zénon consiste à dire que :

  .. math:: \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16} + \frac{1}{32} + ... = \infty

  Nous verrons plus tard que la notion de limite permet de choisir
  l’égalité la plus pertinente et de comprendre d’où provient la
  confusion.

3.4 Des sommes infinies
-------------------

| À la section précédente, nous avons rencontré notre première somme
  infinie , autrement dit une somme avec une infinité de termes :

  .. math:: \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16} + \frac{1}{32} + ...

  A priori, il n’est pas clair qu’on puisse attribuer à cette suite de
  symboles un sens quelconque. Après tout, les êtres humains que nous
  sommes ne peuvent jamais qu’additionner un nombre fini de termes
  puisqu’il semble que notre vie est finie.
|   
| Est-il possible de donner sens à toutes les sommes infinies ? Nous
  verrons une fois de plus grâce à la notion de limite qu’il nous faut
  prendre des précautions lorsqu’on souhaite parler de tels objets. De
  plus, nous verrons que le sujet des sommes infinies est un sujet
  subtil et riche, comme en témoignent les résultats ci-dessous :

-  | Il ne fait pas sens de considérer :math:`1+2+3+4+5+6+...` comme un
     nombre réel.

-  | Il fait sens de considérer
     :math:`\frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16} + \frac{1}{32} + ...`
     comme un nombre réel et on a l’égalité
     :math:`\frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16} + \frac{1}{32} + ...=1`.

-  | Il ne fait pas sens de considérer :math:`1-1+1-1+1-1+...` comme un
     nombre réel (on ne dira donc pas que cette somme infinie est égale
     à :math:`-1`, :math:`0` ou :math:`1`).

-  Il ne fait pas sens de considérer
   :math:`\frac{1}{1}+\frac{1}{2}+\frac{1}{3}+\frac{1}{4}+...` comme un
   nombre réel... mais il fait sens de considérer
   :math:`\frac{1}{2^2}+\frac{1}{3^2}+\frac{1}{4^2}+...` comme un nombre
   réel et on a l’égalité
   :math:`\frac{1}{2^2}+\frac{1}{1^2}+\frac{1}{2^2}+\frac{1}{3^2}+\frac{1}{4^2}+...=\frac{{\pi}^2}{6}`.

4 Limites de suites (optionnel)
=============================

| Dans cette section, nous allons présenter une notion qui nous
  accompagnera tout au long des deux prochains chapitres : la notion de
  limite. Dans un premier temps, nous allons nous intéresser à cette
  notion dans un cadre simple, celui des limites de suites.
| Malheureusement, les démonstrations des résultats présentés dans cette
  section ne pourront être données dans le cadre de ce cours.

4.1 Définition
----------

Dans l’introduction, nous avons discuté des problèmes qui surgissent
rapidement si l’on considère l’infini comme un nombre réel tel que
:math:`\frac{1}{0}=\infty` ou encore :math:`\frac{1}{\infty}=0`.
 
  Néanmoins, si l’on considère par exemple la suite

  .. math::

     \begin{aligned}
     s : \mathbb{N}&\to \mathbb{R}\\
     n &\mapsto \frac{1}{n+1}\end{aligned}

  on aimerait malgré tout pouvoir exprimer clairement l’idée que les
  termes de cette suite se rapprochent de :math:`0`, de façon
  définitive, au fur et à mesure que le rang grandit :

  .. math:: \frac{1}{10}=0,1

  .. math:: \frac{1}{100}=0,01

  .. math:: \vdots

  .. math:: \frac{1}{10000}=0,0001

  .. math:: \vdots

  .. math:: \frac{1}{1000000}=0,000001

  .. math:: \vdots

| Une définition rigoureuse de ce phénomène peut être obtenue en prenant
  le point de vue suivant : si on affirme que la suite
  :math:`(s_n)_{n \in \mathbb{N}}` définie ci-dessus se rapproche de
  :math:`0`, de façon définitive, au fur et à mesure que le rang
  grandit, il est nécessaire que que pour toute borne réelle strcitement
  positive :math:`\epsilon` que l’on se fixe, il doit avoir un certain
  :math:`N \in \mathbb{N}` tel qu’à partir de ce moment :math:`N`, tous
  les termes de la suite sont à une distance au plus :math:`\epsilon` de
  :math:`0` (sinon, il existera toujours des termes de la suite qui
  s’éloigneront de :math:`0` plutôt que de s’en rapprocher, quel que
  soit l’endroit où on est arrivé dans la suite).
| De cet exemple, on tire la définition suivante :

| 

**Définition 4.1.1.** Soit une suite :math:`(s_n)_{n \in \mathbb{N}}`. La suite
:math:`(s_n)_{n \in \mathbb{N}}` a une limite :math:`S \in \mathbb{R}`
si pour tout nombre réel strictement positif :math:`\epsilon`, il existe
:math:`N \in \mathbb{N}` tel que pour tout :math:`n \in \mathbb{N}` avec
:math:`n \ge N`, on a

.. math:: |s_n - S | < \epsilon

Dans ce cas, on note :math:`\lim\limits_{n \to \infty} s_n = S` et on
dit que la suite converge vers :math:`S`.

| 

Passons en revue les suites issues des fonctions de référence et
déterminons si elles ont une limite.

#. Suite obtenue à partir de la fonction constante de constante
   :math:`c` (:math:`c` est un nombre réel quelconque) :

   .. math::

      \begin{aligned}
              s : \mathbb{N}&\to \mathbb{R}\\
              n &\mapsto c
              \end{aligned}

   Cette suite a trivialement pour limite :math:`c` :
   :math:`\lim\limits_{n \to \infty} c = c`.

#. Suite obtenue à partir de la fonction identité :

   .. math::

      \begin{aligned}
              f : \mathbb{N}&\to \mathbb{R}\\
              n &\mapsto n
              \end{aligned}

   Cette suite n’a pas de limite.

#. Suite obtenue à partir de la fonction carrée :

   .. math::

      \begin{aligned}
              f : \mathbb{N}&\to \mathbb{R}\\
              n &\mapsto n^2
              \end{aligned}

   Cette suite n’a pas de limite.

#. Suite obtenue à partir de la fonction cubique :

   .. math::

      \begin{aligned}
              f : \mathbb{N}&\to \mathbb{R}\\
              n &\mapsto n^3
              \end{aligned}

   Cette suite n’a pas de limite.

#. Suite obtenue à partir de la fonction racine carrée :

   .. math::

      \begin{aligned}
              f : \mathbb{N}&\to \mathbb{R}\\
              n &\mapsto \sqrt{n}
              \end{aligned}

   Cette suite n’a pas de limite.

#. Suite obtenue à partir de la fonction racine cubique :

   .. math::

      \begin{aligned}
              f : \mathbb{N}&\to \mathbb{R}\\
              n &\mapsto \sqrt[3]{n}
              \end{aligned}

   Cette suite n’a pas de limite.

#. Suite obtenue à partir de la fonction inverse :

   .. math::

      \begin{aligned}
              f : \mathbb{N}&\to \mathbb{R}\\
              n &\mapsto \frac{1}{n+1}
              \end{aligned}

   Cette suite a comme limite :math:`0` :
   :math:`\lim\limits_{n \to \infty} \frac{1}{n+1} = 0`.

#. Suite obtenue à partir de la fonction valeur absolue :

   .. math::

      \begin{aligned}
              f : \mathbb{N}&\to \mathbb{R}\\
              n &\mapsto |n|
              \end{aligned}

   Cette suite n’a pas de limite.

Ces limites de base vont nous permettre de calculer des limites plus
complexes grâce aux résultats de la prochaine section.

| 

**Exercice 4.1.2** (Difficile). À partir de la définition de limite, démontrer que si
:math:`c \in \mathbb{R}`, la suite

.. math::

   \begin{aligned}
       s : \mathbb{N}&\to \mathbb{R}\\
       n &\mapsto c
       \end{aligned}

a pour limite :math:`c`.

**Solution** Soit un nombre réel strictement positif :math:`\epsilon` fixé. Prenons
:math:`N =0`. Alors, pour tout :math:`n \in \mathbb{N}` avec
:math:`n \ge N`, on a :math:`| s_n - c | = | c - c | = |0| = 0`, donc
:math:`| s_n - c | < \epsilon`.

| 

**Exercice 4.1.3** (Très difficile). À partir de la définition démontrer que la suite

.. math::

   \begin{aligned}
       s : \mathbb{N}&\to \mathbb{R}\\
       n &\mapsto \frac{1}{n+1}
       \end{aligned}

a pour limite :math:`0`.

**Solution** Soit un nombre réel strictement positif :math:`\epsilon` fixé. Prenons
:math:`N \in \mathbb{N}` tel que :math:`N` soit strictement plus grand
que :math:`\frac{1}{\epsilon}` (ce qui implique que
:math:`\epsilon > \frac{1}{N}`). Alors, pour tout
:math:`n \in \mathbb{N}` avec :math:`n \ge N`, on a
:math:`| s_n - 0 | = | \frac{1}{n+1} - 0 | = |\frac{1}{n+1}| = \frac{1}{n+1}`,
donc :math:`| s_n - 0 | < \frac{1}{N+1} < \frac{1}{N} < \epsilon`.

| 

4.2 Propriétés des limites
----------------------

Donnons à présent plusieurs résultats importants concernant les limites.
Commençons par une proposition qui décrit comment se combinent les
limites de deux suites convergentes lorsqu’on les combinent entre elles.

**Proposition 4.2.1.** Soient deux suites :math:`(s_n)_{n \in \mathbb{N}}` et
:math:`(u_n)_{n \in \mathbb{N}}` qui convergent respectivement vers
:math:`S \in \mathbb{R}` et :math:`U \in \mathbb{R}`. Alors :

-  La suite :math:`(s_n + u_n)_{n \in \mathbb{N}}` converge et on a
   :math:`\lim\limits_{n \to \infty} s_n + u_n = S+U`.

-  Si :math:`a \in \mathbb{R}`, la suite
   :math:`(a.s_n)_{n \in \mathbb{N}}` converge et on a
   :math:`\lim\limits_{n \to \infty} a.s_n = a.S`.

-  La suite :math:`(s_n . u_n)_{n \in \mathbb{N}}` convergent et on a
   :math:`\lim\limits_{n \to \infty} s_n . u_n = S.U`.

-  Si :math:`U \neq 0`, la suite
   :math:`(\frac{s_n}{u_n})_{n \in \mathbb{N}}` converge et on a
   :math:`\lim\limits_{n \to \infty} \frac{s_n}{u_n} = \frac{S}{U}`.

À présent, décrivons comme intéragissent les limites avec les inégalités
(non-strictes) :

| 

**Théorème 4.2.2** (Théorème du sandwich). Soient trois suites :math:`(s_n)_{n \in \mathbb{N}}`,
:math:`(u_n)_{n \in \mathbb{N}}` et :math:`(v_n)_{n \in \mathbb{N}}`
avec pour tout :math:`n \in \mathbb{N}` : :math:`s_n \le u_n \le v_n` et
telles que :math:`(s_n)_{n \in \mathbb{N}}` converge vers
:math:`S \in \mathbb{R}` et :math:`(V_n)_{n \in \mathbb{N}}` converge
vers :math:`V \in \mathbb{R}`. Alors :

-  Sa suite :math:`(u_n)_{n \in \mathbb{N}}` converge vers
   :math:`U \in \mathbb{R}`, on a nécessairement :math:`S \le U \le V`.

-  Si :math:`S=V`, alors la suite :math:`(u_n)_{n \in \mathbb{N}}`
   converge nécessairement vers un nombre :math:`U \in \mathbb{R}` qui
   est en fait égal à :math:`S` et :math:`V`.

Pour terminer, donnons un théorème nommé en l’honneur du mathématicien
qui a inventé la définition moderne de limite :

| 

**Théorème 4.2.3** (Théorème du Weierstrass). Soit une suite :math:`(s_n)_{n \in \mathbb{N}}`. Si
:math:`(s_n)_{n \in \mathbb{N}}` est croissante et est majorée, alors
:math:`(s_n)_{n \in \mathbb{N}}` converge nécessairement et sa limite
est le plus petit de ses majorants.

**Remarque 4.2.4.** Ce théorème reste valable si l’on remplace croissante par décroissante,
majorée par minorée et plus petit de ses majorants par plus grand de ses
minorants .

| 

**Exercice 4.2.5.** 

.. inginious:: suite12_1
.. inginious:: suite12_2
.. inginious:: suite12_3
.. inginious:: suite12_4
.. inginious:: suite12_5

| 

4.3 Divergence vers :math:`+ \infty` et :math:`- \infty`
----------------------------------------------------

De la même manière que la notion de limite nous permet d’exprimer
clairement l’idée que la suite qui provient de la fonction inverse se
rapproche de :math:`0`, de façon définitive, au fur et à mesure que le
rang grandit, la notion de divergence va nous permettre d’exprimer
clairement l’idée que la suite qui provient de la fonction identité (par
exemple) grandit de plus en plus, de façon définitive, au fur et à
mesure que le rang augmente :

**Théorème 4.3.1.** Soit une suite :math:`(s_n)_{n \in \mathbb{N}}`. La suite
:math:`(s_n)_{n \in \mathbb{N}}` diverge vers :math:`+ \infty` si pour
tout nombre réel :math:`M`, il existe :math:`N \in \mathbb{N}` tel que
pour tout :math:`n \in \mathbb{N}` avec :math:`n \ge N`, on a

.. math:: s_n  \ge M

Dans ce cas, on note :math:`\lim\limits_{n \to \infty} s_n = \infty` et
on dit que la suite diverge vers :math:`+ \infty`.

**Remarque 4.3.2.** Attention ! Lorsqu’on écrit
:math:`\lim\limits_{n \to \infty} s_n = \infty`, on ne dit absolument
pas la suite :math:`(s_n)_{n \in \mathbb{N}}` a une limite et que cette
limite est le nombre :math:`\infty` ! La notation est extrêmement
similaire à celle de limite, mais le sens de celle-ci est très
différent.

On peut définir de façon similaire la divergence vers :math:`- \infty` :

| 

**Définition 4.3.3.** Soit une suite :math:`(s_n)_{n \in \mathbb{N}}`. La suite
:math:`(s_n)_{n \in \mathbb{N}}` diverge vers :math:`- \infty` si pour
tout nombre réel :math:`M`, il existe :math:`N \in \mathbb{N}` tel que
pour tout :math:`n \in \mathbb{N}` avec :math:`n \ge N`, on a

.. math:: s_n  \le M

Dans ce cas, on note :math:`\lim\limits_{n \to \infty} s_n = -\infty` et
on dit que la suite diverge vers :math:`- \infty`.

| 

Passons en revue les suites issues des fonctions de référence et
déterminons si elles divergent.

#. Suite obtenue à partir de la fonction constante de constante
   :math:`c` (:math:`c` est un nombre réel quelconque) :

   .. math::

      \begin{aligned}
          s : \mathbb{N}&\to \mathbb{R}\\
          n &\mapsto c
          \end{aligned}

   Cette suite a pour limite :math:`c` et ne diverge pas.

#. Suite obtenue à partir de la fonction identité :

   .. math::

      \begin{aligned}
          f : \mathbb{N}&\to \mathbb{R}\\
          n &\mapsto n
          \end{aligned}

   Cette suite diverge vers :math:`+\infty`.

#. Suite obtenue à partir de la fonction carrée :

   .. math::

      \begin{aligned}
          f : \mathbb{N}&\to \mathbb{R}\\
          n &\mapsto n^2
          \end{aligned}

   Cette suite diverge vers :math:`+\infty`.

#. Suite obtenue à partir de la fonction cubique :

   .. math::

      \begin{aligned}
          f : \mathbb{N}&\to \mathbb{R}\\
          n &\mapsto n^3
          \end{aligned}

   Cette suite diverge vers :math:`+\infty`.

#. Suite obtenue à partir de la fonction racine carrée :

   .. math::

      \begin{aligned}
          f : \mathbb{N}&\to \mathbb{R}\\
          n &\mapsto \sqrt{n}
          \end{aligned}

   Cette suite diverge vers :math:`+\infty`.

#. Suite obtenue à partir de la fonction racine cubique :

   .. math::

      \begin{aligned}
          f : \mathbb{N}&\to \mathbb{R}\\
          n &\mapsto \sqrt[3]{n}
          \end{aligned}

   Cette suite diverge vers :math:`+\infty`.

#. Suite obtenue à partir de la fonction inverse :

   .. math::

      \begin{aligned}
          f : \mathbb{N}&\to \mathbb{R}\\
          n &\mapsto \frac{1}{n+1}
          \end{aligned}

   Cette suite a comme limite :math:`0` et ne diverge pas.

#. Suite obtenue à partir de la fonction valeur absolue :

   .. math::

      \begin{aligned}
          f : \mathbb{N}&\to \mathbb{R}\\
          n &\mapsto |n|
          \end{aligned}

   Cette suite diverge vers :math:`+\infty`.

| 

On a des résultats similaires à ceux de la proposition
4.2.1 pour deux suites divergentes :

**Proposition 4.3.4.** Soient deux suites :math:`(s_n)_{n \in \mathbb{N}}` et
:math:`(u_n)_{n \in \mathbb{N}}` qui divergent toutes les deux vers
:math:`+ \infty`. Alors :

-  La suite :math:`(s_n + u_n)_{n \in \mathbb{N}}` diverge vers
   :math:`+\infty`.

-  Soit :math:`a \in \mathbb{R}`. Si :math:`a>0`, la suite
   :math:`(a.s_n)_{n \in \mathbb{N}}` diverge vers :math:`+\infty`. Si
   :math:`a< 0`, la suite :math:`(a.s_n)_{n \in \mathbb{N}}` converge
   vers :math:`0`. Si :math:`a<0`, la suite
   :math:`(a.s_n)_{n \in \mathbb{N}}` diverge vers :math:`-\infty`.

-  La suite :math:`(s_n . u_n)_{n \in \mathbb{N}}` diverge vers
   :math:`+\infty`.

-  Pour la division, il n’existe pas de règle générale.

On a également des résultats similaires à ceux de la proposition
4.2.1 pour une suite convergente et une suite
divergente :

**Proposition 4.3.5.** Soient deux suites :math:`(s_n)_{n \in \mathbb{N}}` et
:math:`(u_n)_{n \in \mathbb{N}}` telles que
:math:`(s_n)_{n \in \mathbb{N}}` converge vers :math:`S \in \mathbb{R}`
et :math:`(u_n)_{n \in \mathbb{N}}` diverge vers :math:`+\infty`. Alors
:

-  La suite :math:`(s_n + u_n)_{n \in \mathbb{N}}` diverge vers
   :math:`+\infty`.

-  Si :math:`S > 0`, la suite :math:`(s_n . u_n)_{n \in \mathbb{N}}`
   diverge vers :math:`+\infty`. Si :math:`S < 0`, la suite
   :math:`(s_n . u_n)_{n \in \mathbb{N}}` diverge vers :math:`-\infty`.
   Si :math:`S=0`, pas de règle générale.

-  La suite :math:`(\frac{s_n}{u_n})_{n \in \mathbb{N}}` converge vers
   :math:`0`.

-  Si :math:`S>0`, alors la suite
   :math:`(\frac{u_n}{s_n})_{n \in \mathbb{N}}` diverge vers
   :math:`+\infty`. Si :math:`S<0`, alors la suite
   :math:`(\frac{u_n}{s_n})_{n \in \mathbb{N}}` diverge vers
   :math:`-\infty`. Si :math:`S=0`, pas de règle générale.

| 

**Exercice 4.3.6.** 

.. inginious:: suite13_1
.. inginious:: suite13_2
.. inginious:: suite13_3
.. inginious:: suite13_4
.. inginious:: suite13_5
.. inginious:: suite13_6
.. inginious:: suite13_7
.. inginious:: suite13_8
.. inginious:: suite13_9
.. inginious:: suite13_10

| 

**Exercice 4.3.7.** Un élève a écrit que

.. math::

   \begin{aligned}
       0=\lim\limits_{n \to \infty} 0 &= \lim\limits_{n \to \infty} ((-1)^n -(-1)^n) \\
       &= \lim\limits_{n \to \infty} ((-1)^n +(-1)^{n+1}) \\
       &= \lim\limits_{n \to \infty} (-1)^n +\lim\limits_{n \to \infty}(-1)^{n+1} \\
       &= \lim\limits_{n \to \infty} (-1)^n +\lim\limits_{n \to \infty}(-1)^{n} \\
       &= 2\lim\limits_{n \to \infty} (-1)^n
       \end{aligned}

et donc

.. math:: \lim\limits_{n \to \infty} (-1)^n = 0

Êtes-vous d’accord avec cette conclusion ? Quelle proposition l’élève
a-t-il mal utilisé ? Où se situe son erreur ?

**Solution**
| L’élève a utilisé la proposition `[proplim] <#proplim>`__ à l’envers
  (ce qui n’est pas correct) : on a bien que
  :math:`\lim\limits_{n \to \infty} ((-1)^n +(-1)^{n+1}) = 0`, mais ça
  n’implique pas que les suites

  .. math::

     \begin{aligned}
         s : \mathbb{N}&\to \mathbb{R}\\
         n &\mapsto ((-1)^n
         \end{aligned}

  et

  .. math::

     \begin{aligned}
         s : \mathbb{N}&\to \mathbb{R}\\
         n &\mapsto (-1)^{n+1}
         \end{aligned}

  aient une limite et que
  :math:`\lim\limits_{n \to \infty} ((-1)^n +(-1)^{n+1}) = \lim\limits_{n \to \infty} (-1)^n +\lim\limits_{n \to \infty}(-1)^{n+1}`.

| 

5 Conclusion : retour sur les problèmes de l’introduction (optionnel)
===================================================================

Finalement, rassemblons tout ce que nous avons appris dans ce chapitre
pour résoudre certains des problèmes de l’introduction.

5.1 Paradoxe de la flèche : la solution
-----------------------------------

| Selon Zénon, la distance que doit parcourir la flèche pour atteindre
  la cible,
  :math:`\frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16} + ...`
  ne peut qu’être infinie car correspondant à une somme d’une infinité
  de distances/de termes strictement positifs. Cela contredit
  l’intuition géométrique et l’expérience physique, d’où le paradoxe.
| Heureusement, nous sommes à présent capables d’exprimer clairement le
  sens de l’expression
  :math:`\frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16} + ...` :
  on peut en effet la voir comme la limite d’une suite consistant en les
  sommes finies des :math:`n+1` premiers termes d’une suite géométrique
  de terme initial :math:`b=\frac{1}{2}` et de raison
  :math:`q=\frac{1}{2}` :

  .. math:: \lim\limits_{n \to \infty} \sum\limits_{i=0}^{n} \frac{1}{2} . \left(\frac{1}{2}\right)^i

  De plus, nous avons à présent une formule pour calculer ces sommes
  finies :

  .. math:: \sum\limits_{i=0}^{n} \frac{1}{2} . \left(\frac{1}{2}\right)^i = \frac{1}{2} . \frac{1-\left(\frac{1}{2}\right)^{n+1}}{1-\frac{1}{2}}

  Et nous sommes donc en mesure de calculer notre limite :

  .. math:: \lim\limits_{n \to \infty} \sum\limits_{i=0}^{n} \frac{1}{2} . \left(\frac{1}{2}\right)^i = \lim\limits_{n \to \infty} \frac{1}{2} . \frac{1-\left(\frac{1}{2}\right)^{n+1}}{1-\frac{1}{2}} = \lim\limits_{n \to \infty} 1-\left(\frac{1}{2}\right)^{n+1} = 1-0=1

  Contrairement à ce que Zénon pensait, la suite
  :math:`(\sum\limits_{i=0}^{n} \frac{1}{2} . (\frac{1}{2})^i)_{n \in \mathbb{N}}`
  ne diverge pas vers :math:`+\infty` mais converge bien vers :math:`1`
  ! Cela rejoint l’intuition géométrique et l’expérience physique : le
  paradoxe est donc résolu.

| 

5.2 0,999... < 1 ou 0,999... = 1 ?
------------------------------

| Nous allons à présent pouvoir trancher : a-t-on :math:`0,999... < 1`
  ou :math:`0,999... = 1` ?
| À nouveau, les :math:`...` expriment la présence d’une limite
  dissimulée. En fait, lorsqu’on écrit :math:`0,999...`, on écrit de
  façon raccourcie la limite suivante :

  .. math::

     \begin{aligned}
     0,999...& = 0,9 + 0,09 + 0,009 + ... \\
     &= \frac{9}{10} + \frac{9}{100} + \frac{9}{1000} + ... \\
     &= \lim\limits_{n \to \infty} \sum\limits_{i=0}^{n} \frac{9}{10} . \left(\frac{1}{10}\right)^i\end{aligned}

  (Le fait que les :math:`...` correspondent à une limite n’est pas
  révélé en primaire ou en début de secondaire pour des raisons
  évidentes.)
|   
| Puisque nous sommes à présent d’exprimer clairement le nombre
  :math:`0,999...`, nous devrions être également capables de démontrer
  si ce nombre est strictement plus petit que :math:`1` ou égal à
  :math:`1` :

  .. math:: \lim\limits_{n \to \infty} \sum\limits_{i=0}^{n} \frac{9}{10} . \left(\frac{1}{10}\right)^i = \lim\limits_{n \to \infty} \frac{9}{10} . \frac{1-\left(\frac{1}{10}\right)^{n+1}}{1-\frac{1}{10}} = \lim\limits_{n \to \infty} \frac{90}{90}\left(1-\left(\frac{1}{10}\right)^{n+1}\right) = 1.(1-0)=1

  Ce qui clôt la discussion.

| 

**Exercice 5.2.1.** On vous affirme depuis longtemps que :math:`\frac{1}{3} = 0,333...`. En
écrivant correctement :math:`0,333...` sous la forme d’une limite,
démontrez-le.

**Solution**
|   
| :math:`\lim\limits_{n \to \infty} \sum\limits_{i=0}^{n} \frac{3}{10} . \left(\frac{1}{10}\right)^i = \lim\limits_{n \to \infty} \frac{3}{10} . \frac{1-\left(\frac{1}{10}\right)^{n+1}}{1-\frac{1}{10}} = \lim\limits_{n \to \infty} \frac{30}{90}\left(1-\left(\frac{1}{10}\right)^{n+1}\right) = \frac{1}{3}.(1-0)=\frac{1}{3}`

| 

**Exercice 5.2.2.** 

.. inginious:: suite14_1

| 

**Exercice 5.2.3.** 

.. inginious:: suite14_2

.. [1]
   Nous les retrouverons avec un autre point de vue dans le prochain
   chapitre.
