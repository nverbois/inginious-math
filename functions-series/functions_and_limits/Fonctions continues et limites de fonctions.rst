| Cours de mathématiques de cinquième année
  4 périodes/semaine
| Fonctions continues et
  limites de fonctions
| Lycée Martin V

1 Introduction
==============

| Ce chapitre est probablement le plus difficile de ce cours, au moins
  sur le plan conceptuel. Nous allons y introduire la notion de fonction
  continue, mais surtout de limite (de fonction). Cette notion de limite
  et les idées sous-jacentes à sa définition sont les idées
  fondamentales qui ont mené à la naissance de l’analyse mathématique
  moderne. Leur portée est immense et de nombreux futurs chapitres du
  cours de mathématiques de cinquième année et de sixième année
  secondaire utiliseront d’ailleurs directement ou indirectement ce que
  nous allons construire dans ce chapitre.
| Pour cette raison, il est indispensable de maîtriser la matière de ce
  chapitre au terme de celui-ci, sans quoi la compréhension de ce qui
  suivra sera rendue difficile, sinon impossible.
|  
| Étant donné la difficulté conceptuelle de la notion de limite et
  l’optique que le programme lui réserve dans le cours de mathématiques
  du secondaire, nous avons choisi de la faire apparaître par
  l’intermédiare des fonctions continues plutôt que par les limites de
  suites. Par expérience, cette dernière approche à l’énorme défaut que
  les élèves semblent avoir énormément de mal à généraliser rapidement
  l’idée de limite de suite pour arriver à l’idée de limite de fonction.
  Néanmoins, la partie optionnelle du chapitre précédent contient tout
  de même une telle approche et il est grandement conseillé de lire
  celle-ci dans le courant du début de ce chapitre sur les fonctions
  continues et les limites de fonctions.
|  
| Si le sujet des fonctions continues peut être amené de façon
  relativement intuitive et introduit à l’aide d’un problème (et de sa
  solution) assez amusant et intéressant, le sujet des limites de
  fonctions devra être découvert au moins dans un premier temps de façon
  purement technique. Pas d’inquiétude néanmoins : nous découvrirons dès
  le prochain chapitre des exemples concrets d’application de cette
  notion.
|  
| Enfin, il est vivement conseillé de maîtriser parfaitement l’ensemble
  de la matière vue jusqu’à présent portant sur les fonctions. Il serait
  extrêmement dommageable que la compréhension de ce chapitre soit
  rendue encore plus difficile par un manque de maîtrise des prérequis.

2 Fonctions continues
=====================

2.1 Définition et exemples
--------------------------

| L’idée de continuité est déjà présente dans le langage courant. Par
  exemple, on dira que la température d’une pièce (qui n’est chauffée
  que durant la journée) évolue de façon continue au cours du temps. Sa
  température est plus basse durant la nuit que durant la journée, mais
  elle ne passe subitement d’une température basse à une température
  élevée : la température évolue progressivement et continuement.
| On peut donner de nombreux autres exemples de phénomènes continus :
  les déplacements, la vitesse, l’accélération, le son... En fait, la
  supposition que tous les phénomènes naturels sont continus est souvent
  une supposition implicite de notre vie de tous les jours et de la
  physique classique. Puisque nous avons le réflexe intuitif de
  formaliser tous ces phénomènes de la nature sous la forme de processus
  continus, il est pertinent de s’intéresser à cette formalisation que
  sont les fonctions continues.
| De plus, les fonctions continues ont un intérêt mathématique non
  négligeable et nous permettront d’introduire l’idée de limite de
  fonction.

**Définition 2.1.1.**  Soit :math:`I` un intervalle éventuellement privé d’un point. Soit 
:math:`f : I \to \mathbb{R}`.

  On dit que :math:`f` est une fonction continue en :math:`c \in I` si
  et seulement si pour tout :math:`\epsilon > 0`, il existe
  :math:`\delta > 0` tel que pour tout :math:`x \in I` tel que
  :math:`|x-c| < \delta`, on a :math:`|f(x) - f(c)| < \epsilon`.

**Remarque 2.1.2.** Cette définition, assez technique, ne doit pas vous faire peur. Une
lecture intuitive de cette définition est la suivante : si un
processus :math:`f` qui dépend d’une variable :math:`x` est continu
autour d’une certaine valeur de :math:`x` qui vaut :math:`c`, alors je
dois pouvoir approcher les valeurs de :math:`f(c)` autant que je le
souhaite si je suis capable d’approcher la valeur de :math:`c` autant
que nécessaire.
Il est recommandé d’appliquer cette définition sur les deux exemples
suivants afin d’analyser celle-ci en profondeur et comprendre en quoi
elle formalise l’idée intutive de continuité.

| 

**Exemple 2.1.3.**

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};

		\draw[thick] plot[domain=-4:3](\x,{((\x)*(\x)*(1/2)-4});
		\draw (-4,4)node{$\bullet$};
		\draw (3,0.5)node{$\bullet$};

|  
| Voici le graphe d’une fonction continue en :math:`-2` définie sur
  :math:`[-4,3]`. En effet, quelle que soit l’erreur maximale autorisée
  :math:`\epsilon >0`, quitte à sélectionner des valeurs pour :math:`x`
  assez proche de :math:`-2` (à une distance de :math:`-2` d’au plus
  :math:`\delta >0`), les valeurs :math:`f(x)` approcheront bien la
  valeur :math:`f(-2)` avec une erreur plus petite ou égale à
  :math:`\epsilon`.
| Géométriquement, cela correspond au fait qu’il n’y a pas de saut
  vertical en :math:`-2` et que le graphe peut être réalisé d’un seul
  trait.

**Exemple 2.1.4.**

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
		\draw[thick] plot[domain=-4:-2](\x,{((\x)*(\x)*(1/2)-4});
		\draw[thick] plot[domain=-2:3](\x,{((\x)*(\x)*(1/2)-1});
		\draw (-4,4)node{$\bullet$};
		\draw (3,3.5)node{$\bullet$};
		\draw (-2,1)node{$\bullet$};
		\draw[thick, fill=white](-2,-2)circle(0.1);

|  
| Voici le graphe d’une fonction discontinue en :math:`-2` définie sur
  :math:`[-4,3]`. En effet, en prenant comme erreur maximale autorisée
  :math:`\epsilon =1`, il est impossible de trouver un :math:`\delta >0`
  tel qu’à toutes les valeurs de :math:`x` possibles à une distance au
  plus :math:`\delta` de :math:`-2`, la fonction :math:`f` associera un
  nombre :math:`f(x)` dont la distance avec :math:`f(-2)` est plus
  petite que :math:`1`. La raison étant que juste à gauche de :math:`-2`
  , la fonction prend des valeurs strictement négative alors que
  :math:`f(-2)=1`.
| Géométriquement, cela correspond au fait qu’il y a un saut vertical en
  :math:`-2` et que le graphe ne peut pas être réalisé d’un seul trait.

**Remarque 2.1.5.** Une caractérisation intuitive des graphes de fonctions continues est
qu’il s’agit des fonctions dont le graphe peut être tracé d’un seul
trait. Néanmoins, celle-ci est imprécise et peut mener à des erreurs,
puisque la continuité ne concerne que les sauts dans les valeurs d’une
fonction (autrement dit : les sauts verticaux dans le graphe de la
fonction) et non son domaine de définition (les sauts horizontaux dans
le graphe de la fonction).
Permettons-nous d’insister : il ne fait pas sens de parler de
continuité d’une fonction en un point où elle n’est pas définie !
Par exemple, la fonction inverse :

.. tikz:: 

    \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

    \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
  \draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

    \foreach \x in {1}
  \draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

    \foreach \y in {1}
  \draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
  \draw[thick] plot[domain=-5:-0.2](\x,{1/(\x)});
  \draw[thick] plot[domain=0.2:5](\x,{1/(\x)});

Cette fonction est bien partout continue ! Il ne fait pas sens
d’affirmer qu’elle est discontinue en :math:`0`, puisqu’elle n’est même
pas définie en :math:`0`.

| 

**Définition 2.1.6.** Soit :math:`I` un intervalle éventuellement privé d’un point. Soit :math:`f : I \to \mathbb{R}`.

  On dit que :math:`f` est une fonction continue si elle est continue en
  tous les points de son domaine de définition.

| 

**Exercice 2.1.7.** Donner le domaine de définition des fonctions dont les graphes sont les
suivants, puis déterminer si elles sont continues ou non. Si elles ne
sont pas continues, donner l’ensemble des points où elles sont
discontinues.

.. inginious:: cont1_1
.. inginious:: cont1_2
.. inginious:: cont1_3
.. inginious:: cont1_4
.. inginious:: cont1_5
.. inginious:: cont1_6
.. inginious:: cont1_7
.. inginious:: cont1_8
.. inginious:: cont1_9
.. inginious:: cont1_10

| 

2.2 Continuité des fonctions de référence
-----------------------------------------

| Les fonctions de référence servent de briques de base pour construire
  des fonctions plus complexes. Il serait intéressant de déterminer si
  les fonctions de références sont continues et si les fonctions créées
  à partir de celles-ci héritent de cette propriété.
| Pour commencer, nous avons le théorème :

**Théorème 2.2.1.** Toutes les fonctions de référence sont continues.

*Démonstration* Pas en math 4. [1]_

**Remarque 2.2.2.** De toutes les fonctions de référence, seule la fonction inverse n’a pas
un graphe qui peut être tracé d’un seul trait . À nouveau, il s’agit
dans ce cas d’une question de domaine (la fonction inverse n’est pas
définie en :math:`0` puisqu’il ne fait pas sens de diviser par
:math:`0`) et non de continuité.

| 

**Exemple 2.2.3.** Par exemple, la fonction racine cubique est continue :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
		\draw[thick] plot[domain=0.01:5,samples=1000](\x,{(\x)^(1/3)});
		\draw[thick] plot[domain=-5:-0.01,samples=1000](\x,{-(abs(\x))^(1/3)});

| 

2.3 Propriétés des fonctions continues
--------------------------------------

Commençons avec un exemple :

**Exemple 2.3.1.** Considérons les deux fonctions :

.. math::

   \begin{aligned}
       f : [1,3] &\to \mathbb{R}\\
       x &\mapsto (x-2)^2 - 1
       \end{aligned}

et

.. math::

   \begin{aligned}
       g : [1,3] &\to \mathbb{R}\\
       x &\mapsto -\frac{1}{2}x+\frac{1}{2}
       \end{aligned}

dont les graphes sont les suivants :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
		\draw[thick,blue] plot[domain=1:3](\x,{-1+2*(\x-2)^(2)});
		\draw[thick,red] plot[domain=1:3](\x,{1.5-(0.5)*(\x)});

| Ces deux fonctions sont continues : leurs graphes peuvent être tracés
  d’un seul trait, il n’y a pas de saut vertical.
| Que se passe-t-il si on additionne ces deux fonctions, autrement dit
  si on considère la fonction :math:`f+g` ? Au niveau des graphes, cela
  revient à additionner les ordonnées des points des graphes de
  :math:`f` et :math:`g` qui ont la même abscisse.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
		\draw[thick] plot[domain=1:3](\x,{-1+2*(\x-2)^(2)+1.5-(0.5)*(\x)});

Sans surprise, aucune discontinuité n’est apparue. En additionnant deux
fonctions continues, on a obtenu une nouvelle fonction continue. Ce
n’est pas un hasard, comme l’indique la proposition suivante.

| 

**Proposition 2.3.2.** Soit :math:`I` un intervalle éventuellement privé d’un point. Soient
:math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}` deux
fonctions continues. Alors :

#. La fonction :math:`f+g : I \to \mathbb{R}` est continue.

#. La fonction :math:`f-g : I \to \mathbb{R}` est continue.

#. La fonction :math:`f.g : I \to \mathbb{R}` est continue.

#. La fonction
   :math:`\frac{f}{g} : \{x \in I ~|~ g(x) \neq 0\} \to \mathbb{R}` est
   continue.

*Démonstration* Pas en math 4. Voir annexe pour les curieux.

De manière éventuellement plus surprenante, la composée de deux
fonctions continues (compatibles) est également toujours une fonction
continue :

**Proposition 2.3.3.** Soit :math:`I,J` deux intervalles. Soient
:math:`f : I \to \mathbb{R}` et :math:`g : J \to \mathbb{R}` deux
fonctions continues telle que
:math:`\mathop{\mathrm{im}}(g) \subseteq I`. Alors :
:math:`f \circ g : J \to \mathbb{R}` est continue.

*Démonstration* Pas en math 4.

Une dernière opération qui conserve la continuité est la **restriction** :

**Définition 2.3.4.** Soit :math:`I` un intervalle éventuellement privé d’un point. Soit
:math:`f : I \to \mathbb{R}`.
Soit :math:`A \subseteq I`. Alors la **restriction** de :math:`f` sur
:math:`A` est la fonction :

  .. math::

     \begin{aligned}
         f_{|A} : A &\to \mathbb{R}\\
         x &\mapsto f(x)
         \end{aligned}

| 

**Exemple 2.3.5.** Soit la fonction :

  .. math::

    \begin{aligned}
        f : [-4,3] &\to \mathbb{R}\\
        x &\mapsto x+1
        \end{aligned}

dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
		\draw[thick] plot[domain=-4:3](\x,{1+ \x });

La restriction de :math:`f` sur, par exemple,
:math:`[-4,-3[ \cup \{-2\} \cup [-1,1]`, est la fonction :

.. math::

   \begin{aligned}
       f_{[-4,-3[ \cup \{-2\} \cup [-1,1]} : [-4,-3[ \cup \{-2\} \cup [-1,1] &\to \mathbb{R}\\
       x &\mapsto x+1
       \end{aligned}

et son graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
		\draw (-4,-3)node{$\bullet$};
		\draw[thick] plot[domain=-4:-3.1](\x,{1+(\x)});
		\draw (-2,-1)node{$\bullet$};
		\draw[thick, fill=white](-3,-2)circle(0.2);
		\draw (-1,0)node{$\bullet$};
		\draw[thick] plot[domain=-1:1](\x,{1+(\x)});
		\draw (1,2)node{$\bullet$};

| 

Comme annoncé, la restriction d’une fonction continue est toujours
continue :

**Proposition 2.3.6.** Soit :math:`I` un intervalle éventuellement privé d’un point.
Soit :math:`f : I \to \mathbb{R}` une fonction continue. Soit
:math:`A \subseteq I`.
Alors la *restriction* de :math:`f` sur :math:`A` est continue.

*Démonstration* Pas en math 4. Notons néanmoins que la démonstration est extrêment
simple.

Grâce au théorème 2.2.1, nous savons que toutes les
fonctions de référence sont continues. 
Or, les propositions
2.3.2, 2.3.3 et 2.3.6 nous disent que
lorsqu’on combine deux fonctions continues selon une des opérations
sur les fonctions les plus simples, nous pouvons être certains que le
résultat est lui aussi une fonction continue. 
Ainsi, nous sommes à
présent capables de justifier la continuité de nombreuses fonctions.  

| 

**Exercice 2.3.7.** Les fonctions suivantes sont-elles continues ? Si oui, justifier. Si
non, faire le graphe de la fonction et donner l’ensemble des points de
discontinuité.

.. inginious:: cont2_1
.. inginious:: cont2_2
.. inginious:: cont2_3
.. inginious:: cont2_4
.. inginious:: cont2_5
.. inginious:: cont2_6
.. inginious:: cont2_7
.. inginious:: cont2_8

| 

2.4 Grands théorèmes des fonctions continues (optionnel)
--------------------------------------------------------

| Dans cette section, nous allons lister les grands résultats associés
  aux fonctions continues.
| Le premier est assez intuitif. Pour reprendre l’exemple de
  l’introduction de la température dans une pièce, si on suppose que la
  température de la pièce était de :math:`10\degree` à minuit et
  qu’elle est de :math:`20\degree` à midi et qu’on choisit une
  température en :math:`10\degree` et :math:`20\degree`, par exemple
  :math:`15\degree`, on est intuitivement convaincu qu’il y a eu au
  moins un court instant dans la matinée où la température de la pièce
  était de :math:`15\degree` (puisque le phénomène est continu, on doit
  bien passer par toutes les valeurs intermédiaires entre
  :math:`10\degree` et :math:`20\degree` pour passer de
  :math:`10\degree` à :math:`20\degree`). Cette intuition est
  formalisée par le théorème suivant :

**Théorème 2.4.1** (Théorème des valeurs intermédiaires). Soit :math:`I` un intervalle de la forme :math:`I=[a,b]`. Soit
:math:`f : I \to \mathbb{R}` une fonction continue.
Pour tout :math:`y \in \mathbb{R}` compris entre :math:`f(a)` et
:math:`f(b)`, il existe :math:`x \in I` tel que :math:`f(x) = y`.

*Démonstration* Pas en math 4. [2]_

| 

**Exemple 2.4.2.** Considérons la fonction suivante qui est la restriction de la fonction
carrée sur :math:`[0,2]`.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
		\draw[thick] plot[domain=0:2](\x,{(\x)^(2)});

Puisque cette fonction est continue, :math:`f(0)=0`, :math:`f(2)=4` et
:math:`0 \le \pi \le 4`, on peut être certain qu’il existe une abscisse
:math:`x` entre :math:`0` et :math:`2` telle que la valeur de cette
fonction en :math:`x` vaut exactement :math:`\pi` (dans ce cas-ci, il
est possible de déterminer ce :math:`x` (qui est ici unique) :
:math:`\sqrt{\pi}`).

**Remarque 2.4.3.** Le théorème n’affirme pas que l’abscisse :math:`x` telle que
:math:`f(x) = y` est unique ! Comme le montre l’exemple suivant (où on
choisit pour :math:`y` l’ordonnée :math:`0`, qui se trouve entre
:math:`f(-4)=-3` et :math:`f(4)=3`), il peut y avoir plusieurs abscisses
de cette sorte :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
		\draw[thick] plot[domain=-4:4](\x,{(1/16)*(\x-2)*(\x)*(\x+2)});
		\draw (4,3)node{$\bullet$};
		\draw (-4,-3)node{$\bullet$};

La fonction vaut :math:`0` en :math:`-2`, en :math:`0` et en :math:`2`.

| Le théorème des valeurs intermédiaires a de nombreuses applications et
  pas seulement des applications purement théoriques. Il permet par
  exemple de justifier la validité d’une solution à un problème
  relativement courant dans la vie de tous les jours : une table
  bancale.
| Nous renvoyons vers cette vidéo de l’excellente chaîne youtube
  *Numberphile* de vulgarisation mathématique pour plus de détails à ce
  sujet : https://www.youtube.com/watch?v=OuF-WB7mD6k. 
  À présent, donnons l’autre fameux théorème concernant les fonctions continues :

| 

**Théorème 2.4.4.** Soit :math:`I` un intervalle de la forme :math:`I=[a,b]`. Soit
:math:`f : I \to \mathbb{R}` une fonction continue.
:math:`f` est nécessairement bornée et atteint ses bornes, autrement
dit :math:`f` a un point de minimum et un point de maximum.

*Démonstration* Pas en math 4. [3]_

**Remarque 2.4.5.** Dans le prochain chapitre, nous nous intéresserons beaucoup aux (points
de) minimum et maximum d’une fonction. Ce théorème des bornes atteintes
nous dit que pour une fonction continue définie sur un intervalle fermé,
nous pouvons être certain qu’un point de minimum et qu’un point de
maximum existe, mais il ne nous dit pas comment les trouver.

**Remarque 2.4.6.** La fonction dont le graphe est ci-dessous est définie sur un intervalle
de la forme :math:`[a;b]` et est continue :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
		\draw[thick, samples=50] plot[domain=-2:2](\x,{(15/16)*(\x-2)*(\x)*(\x+2)});
		\draw (2,0)node{$\bullet$};
		\draw (-2,-0)node{$\bullet$};

Il s’agit de la fonction :

.. math::

   \begin{aligned}
       f : [-2;2] &\to \mathbb{R}\\
       x &\mapsto \frac{15}{16}.(x-2).(x).(x+2)
       \end{aligned}

Nous serions bien incapables (à ce stade) de déterminer quel est le
(point de) maximum et le (point de) minimum de cette fonction, mais nous
sommes certains que ceux-ci existent bel et bien (visuellement, on les
identifie immédiatement sans pour autant être capable de les déterminer
exactement).

.. _procont:

| 

2.5 Prolongements continus
--------------------------

**Exemple 2.5.1.** Voici le graphe d’une fonction définie sur
:math:`[-4;4] \backslash \{1\}` qui est continue :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
			\draw (-4,-2.2)node{$\bullet$};
			\draw[thick] plot[domain=-4:0.93,samples=50](\x,{-2.2-0.1*\x*(\x-2)*(\x+1)*sin(90*\x)});
			\draw[thick, fill=white](1,-2)circle(0.176);
			\draw[thick, fill=white](1,1)circle(0.176);
			\draw[thick] plot[domain=1.13:4,samples=50](\x,{0.8-0.1*\x*(\x-2)*(\x+1)*sin(90*\x)});
			\draw (4,0.8)node{$\bullet$};

Il ne fait pas sens de dire qu’elle est discontinue (ou continue) en
:math:`1` puisqu’elle n’est pas définie en :math:`1`.

| 

**Exemple 2.5.2.** Voici le graphe d’une autre fonction définie sur
:math:`[-4;4] \backslash \{1\}` qui est continue :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
			\draw (-4,-2.2)node{$\bullet$};
			\draw[thick] plot[domain=-4:0.93,samples=50](\x,{-2.2-0.1*\x*(\x-2)*(\x+1)*sin(90*\x)});
			\draw[thick, fill=white](1,-2)circle(0.176);
			\draw[thick] plot[domain=1.13:4,samples=50](\x,{-2.2-0.1*\x*(\x-2)*(\x+1)*sin(90*\x)});
			\draw (4,-2.2)node{$\bullet$};

Il ne fait pas sens de dire qu’elle est continue (ou discontinue) en
:math:`1` puisqu’elle n’est pas définie en :math:`1`.

|  
| Dans les deux cas, nous avons une fonction continue. Néanmoins,
  intuitivement, il y a une différence de ces deux situations. Pour la
  première fonction, il n’est pas possible de la prolonger en une
  fonction continue, c’est-à-dire d’étendre la fonction en la
  définissant en :math:`1` de sorte que le résultat final soit continu,
  même en :math:`1`. Par contre, pour la deuxième fonction, il est
  possible de trouver un tel prolongement continu : il suffit d’étendre
  la fonction en la définissant en :math:`1` en décidant que le
  prolongement de la fonction vaut :math:`-2` en :math:`1`. Cette
  intuition correspond au fait que la deuxième fonction possède un
  prolongement continu tandis que la première non.
| Donnons la définition de prolongement continu d’une fonction.

| 

**Définition 2.5.3.** Soit un intervalle :math:`I` et soit :math:`c \in I`. Soit :math:`f : I \backslash \{c\} \to \mathbb{R}`.

  Un *prolongement continu* de :math:`f` sur :math:`I` est une fonction
  :math:`g : I \to \mathbb{R}` qui est continue (y compris en :math:`c`)
  et telle que pour tout :math:`x \in I \backslash \{c\}`, on a
  :math:`g(x)=f(x)`.

| 

**Exemple 2.5.4.** La fonction de l’exemple 2.5.1 ne possède pas de
prolongement continu. Par contre, la fonction de l’exemple
2.5.2 possède un prolongement continu dont le graphe
est le suivant :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
			\draw (-4,-2.2)node{$\bullet$};
			\draw[thick] plot[domain=-4:4,samples=100](\x,{-2.2-0.1*\x*(\x-2)*(\x+1)*sin(90*\x)});
			\draw (4,-2.2)node{$\bullet$};

Dans le cas de cet exemple, puisque nous possédions déjà le graphe de la
fonction, ce prolongement continu n’était pas très difficile à trouver.

|  
| Mais plus généralement, comment savoir si pour une fonction
  :math:`f : I \backslash \{c\} \to \mathbb{R}` (où :math:`I` est un
  intervalle et :math:`c \in I`) donnée, cette fonction admet un
  prologement continu ? Intuitivement, il n’est pas très difficle de
  répondre à cette question : il faut que la fonction :math:`f` se
  rapproche d’une certaine valeur lorsqu’on se rapproche de :math:`c`,
  et ce de manière uniforme (il faut que la valeur de laquelle :math:`f`
  se rapproche par la gauche soit la même que celle de laquelle
  :math:`f` se rapproche par la droite ). Néanmoins, cette réponse
  intuitive soulève au moins trois questions.

#. Que signifie rigoureusement que la fonction :math:`f` se rapproche
   d’une valeur lorsqu’on se rapproche de :math:`c` ?

#. Comment savoir si la fonction :math:`f` se rapproche bien d’une
   certaine valeur de manière uniforme et définitive lorsqu’on se
   rapproche de :math:`c` ?

#. Si :math:`f` se rapproche bien d’une certaine valeur de manière
   uniforme et définitive lorsqu’on se rapproche de :math:`c`, comment
   calculer cette valeur ?

Pour répondre à ces questions, nous avons besoin d’une nouvelle notion :
celle de limite de fonction.

| 

3 Limites de fonctions
======================

.. _définition-et-exemples-1:

3.1 Définition et exemples
--------------------------

Pour découvrir la notion de limite qui est la formalisation de l’idée
intuitive se rapprocher de (de façon définitive et uniforme) ,
commençons avec un exemple :

**Définition 3.1.1.** Soit la fonction

.. math::

   \begin{aligned}
       f : \mathbb{R}&\to \mathbb{R}\\
       x &\mapsto \begin{cases}
           x^3 +1 & \text{si } x \neq 0  \\
           0 & \text{si } x = 0
           \end{cases}
       \end{aligned}

Son graphe est le suivant :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
			\draw[thick] plot[domain=0.05:1.5874](\x,{1+\x*\x*\x});
      \draw[thick] plot[domain=-1.8171:-0.05](\x,{1+\x*\x*\x});
			\draw[thick, fill=white](0,1)circle(0.15);
			\draw (0,0)node{$\bullet$};

Au fur et à mesure que la variable :math:`x` se rapproche de :math:`0`,
de quelle valeur se rapproche :math:`f(x)` ? Pour nous aider à y voir
plus clair, évaluons la fonction :math:`f` en plusieurs nombres qui se
rapprochent de :math:`0` :

.. hlist::
   :columns: 2

   * :math:`f(\frac{1}{10}) = \frac{1}{1000}+1 =1,001`

   * :math:`f(\frac{1}{100}) = \frac{1}{1000000}+1 = 1,000001`

   * :math:`f(\frac{1}{1000}) = \frac{1}{1000000000} =1,000000001`

   * :math:`f(-\frac{1}{10}) = -\frac{1}{1000}+1 = 0,999`

   * :math:`f(-\frac{1}{100}) = -\frac{1}{1000000}+1 = 0,999999`

   * :math:`f(-\frac{1}{1000}) = -\frac{1}{1000000000}+1 = 0,999999999`

| 

| Plus la variable :math:`x` se rapproche de :math:`0`, plus
  :math:`f(x)` se rapproche de :math:`1` et ce de manière uniforme et
  définitive : non seulement on se rapproche de cette valeur :math:`1`
  aussi bien par la droite que par la gauche , mais ce rapprochement se
  fait autant que possible (sans pour autant que la fonction ne prenne
  jamais la valeur :math:`1`) : les valeurs de :math:`f(x)` se
  rapprochent autant qu’on le souhaite de la valeur :math:`1` à
  condition que les valeurs de :math:`x` soient assez proches de
  :math:`0`.

| Pour préciser cette idée intuitive, on peut se donner un petit test
  pour vérifier si la fonction :math:`f` se rapproche bien de :math:`1`
  quand les :math:`x` se rapprochent de :math:`0` : si on se fixe une
  certaine marge d’erreur autour de :math:`1` (par exemple une marge
  d’erreur de :math:`\frac{1}{1000000}`), les valeurs de la fonction
  :math:`f(x)` ne s’éloignent pas de :math:`1` d’une distance supérieure
  à l’erreur fixée à condition que les :math:`x` choisis soient assez
  proches de :math:`0` (avec une marge d’erreur de
  :math:`\frac{1}{1000000}`, les :math:`x` disponibles sont ceux ne
  s’éloignant pas de :math:`0` de plus de :math:`\frac{1}{100}`). 
  Si la
  fonction :math:`f` se rapproche bien de :math:`1` quand les :math:`x`
  se rapprochent de :math:`0`, alors ce test devrait fonctionner quel
  que soit la marge d’erreur (non nulle) qu’on s’est donnée, même si
  celle-ci est extrêmement petite. Cette idée relativement naturelle
  mais complexe est en fait la définition rigoureuse de la notion de
  limite.

| 

**Définition 3.1.2.** Soit un intervalle :math:`I` éventuellement privé d’un point :math:`c`. Soit :math:`f : I \to \mathbb{R}`.

  On dit que :math:`f` a *une limite* :math:`L \in \mathbb{R}` en
  :math:`c` si pour toute marge d’erreur :math:`\epsilon >0`, il existe
  :math:`\delta > 0` tel que pour tout :math:`x \in I \backslash \{c\}`
  qui est à une distance plus petite ou égale de :math:`c` que
  :math:`\delta`, c’est-à-dire tel que :math:`|x-c| \le \delta`, on a
  nécessairement que :math:`f(x)` est à une distance plus petite ou
  égale de :math:`L` que :math:`\epsilon`, c’est-à-dire qu’on a
  :math:`|f(x)-L| \le \epsilon`.
  Dans ce cas, on note :

  .. math:: \lim\limits_{x \to c} f(x)=L

| 

**Exemple 3.1.3.** La fonction

.. math::

   \begin{aligned}
       f : \mathbb{R}&\to \mathbb{R}\\
       x &\mapsto \begin{cases}
           x^3 +1 & \text{si } x \neq 0  \\
           0 & \text{si } x = 0
           \end{cases}
       \end{aligned}

a comme limite :math:`1` en :math:`0`. On note :
:math:`\lim\limits_{x \to 0} f(x)=1`

**Remarque 3.1.4.** Notons que dans l’exemple ci-dessus, la fonction :math:`f` possède une
limite en :math:`1` qui vaut :math:`0` mais est également définie en
:math:`0` de telle sorte que :math:`f(0)=0`. Il est important de
comprendre qu’une limite d’une fonction en un point (si elle existe)
n’est pas toujours égale à la valeur de la fonction en ce point (la
fonction peut même ne pas être définie en ce point). C’est d’ailleurs
tout l’intérêt de la notion de limite : elle permet de parler d’une
valeur de laquelle se rapproche une fonction en un point sans que cette
fonction ne soit jamais égale à cette valeur.

| 

Voici à présent un théorème important mais que nous ne pourrons
malheureusement pas démontrer :

**Théorème 3.1.5.** Soit un intervalle :math:`I` éventuellement privé d’un point
:math:`c`. Soit :math:`f : I \to \mathbb{R}`.
Si :math:`f` possède une limite en :math:`c`, alors cette limite est
unique.

  Il fait donc sens de parler de LA limite d’une fonction en un point.
  Ce théorème ne devrait pas vous surprendre : si on se rapproche de
  manière uniforme et définitive d’un endroit, on ne peut pas en même
  temps se rapprocher de manière uniforme et définitive d’un autre
  endroit.
 
| Donnons à présent quelques exemples de limites de fonction pour
  visualiser cette nouvelle notion.

| 

**Exemple 3.1.6.** Soit la fonction carrée, dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
			\draw[thick] plot[domain=-2.2361:2.2361](\x,{\x*\x});

| Cette fonction possède une limite en :math:`2` et cette limite vaut
  :math:`4` : :math:`\lim\limits_{x \to 2} x^2 = 4`.
| Pour cette fonction, notons qu’on a
  :math:`\lim\limits_{x \to 2} x^2 = f(2)`.

**Exemple 3.1.7.** Soit la fonction dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
			\draw[thick] plot[domain=-5:-3.05](\x,{\x});
    \draw[thick] plot[domain=-2.95:4](\x,{1+\x});
			\draw[thick, fill=white](-3,-3)circle(0.15);
			\draw (-3,-2)node{$\bullet$};

Cette fonction ne possède pas de limite en :math:`-3` : quand les
:math:`x` se rapprochent de :math:`-3`, les :math:`f(x)` ne se
rapprochent pas uniformément d’un unique nombre (ils se rapproche de
:math:`-3` par la gauche et de :math:`-2` par la droite ).

**Exemple 3.1.8.** Soit la fonction dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:3.95](\x,{2+0.25*\x*cos(180*\x)});
    \draw[thick] plot[domain=4.05:5](\x,{2+0.25*\x*cos(180*\x)});
			\draw[thick, fill=white](4,3)circle(0.15);

La fonction n’est pas définie en :math:`4` mais elle possède néanmoins
une limite en :math:`4` : quand les :math:`x` se rapprochent de
:math:`4`, les :math:`f(x)` se rapprochent uniformément et
définitivement de :math:`3`. On note :
:math:`\lim\limits_{x \to 2} f(x) = 3`

| 

**Définition 3.1.9.** Soit la fonction dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=0:1.95](\x,{sqrt(\x)});
    \draw[thick] plot[domain=2.05:5](\x,{sqrt(\x)});
			\draw[thick, fill=white](2,1.4142)circle(0.15);
			\draw (2,-3)node{$\bullet$};

La fonction n’est pas définie en :math:`4` mais elle possède néanmoins
une limite en :math:`4` : quand les :math:`x` se rapprochent de
:math:`4`, les :math:`f(x)` se rapprochent uniformément et
définitivement de :math:`3`. On note :
:math:`\lim\limits_{x \to 2} f(x) = 3`

| 

**Exercice 3.1.10.** À l’aide d’un graphique, déterminer si les limites suivantes existent.
Si oui, donner les valeurs de celles-ci.

.. inginious:: limite10_1
.. inginious:: limite10_2
.. inginious:: limite10_3
.. inginious:: limite10_4

| 

**Exercice 3.1.11.** Voici le graphe de la fonction :math:`f`. Déterminer si les limites
suivantes existent. Si oui, donner les valeurs de celles-ci.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-7,-3) grid (7,4);

      \draw[very thick,->] (-7,0) -- (8,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-3) -- (0,5) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-7:-3,samples=100](\x,\x+5);
    \draw[thick] plot[domain=-3:0,samples=100](\x,0.45*\x*\x-2);
    \draw[thick] plot[domain=0:1.9457,samples=100](\x,{ln(1.95-\x)+2.3});
    \draw[thick] plot[domain=2.0543:7,samples=100](\x,{ln(\x-2.05)+2.3});
    \draw [thick] (-3,2) node[circle,fill=white,draw=black,inner sep=0.4mm] {};
    \draw [thick] (0,-2) node[circle,fill=black,draw=black,inner sep=0.4mm] {};
    \draw [thick] (0,3) node[circle,fill=white,draw=black,inner sep=0.4mm] {};


#. :math:`\lim\limits_{x\to -3} f(x)`

#. :math:`\lim\limits_{x\to -2} f(x)`

#. :math:`\lim\limits_{x\to 0} f(x)`

#. :math:`\lim\limits_{x\to 2} f(x)`

#. :math:`\lim\limits_{x\to 4} f(x)`

.. inginious:: limite11

| 

**Exercice 3.1.12.** Tracer le graphe d’une fonction :math:`f` définie sur
:math:`\mathbb{R}\backslash \{-3;0\}` qui n’a pas de limite en
:math:`-3` et qui a une limite en :math:`0` qui vaut :math:`3`.

**Solution.**

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-3.05](\x,{-1*\x-1});
    \draw[thick, fill=white](-3,2)circle(0.15);
    \draw[thick, fill=white](-3,3)circle(0.15);
    \draw[thick] plot[domain=-2.90:-0.05](\x,{3});
    \draw[thick, fill=white](0,3)circle(0.15);
    \draw[thick] plot[domain=0.09:5](\x,{-1*\x+3});

| 

**Exercice 3.1.13.** Déterminer si les limites suivantes si elles existent.

.. inginious:: limite12_1
.. inginious:: limite12_2
.. inginious:: limite12_3
.. inginious:: limite12_4
.. inginious:: limite12_5
.. inginious:: limite12_6
.. inginious:: limite12_7
.. inginious:: limite12_8
.. inginious:: limite12_9
.. inginious:: limite12_10

| 

**Exercice 3.1.14.** Tracer le graphe d’une fonction :math:`f` ayant les propriétés suivantes
:

#. dom :math:`f=[-4,3] \backslash \{1;2\}`

#. :math:`f` est continue partout sauf en :math:`-2`.

#. :math:`f` n’a pas de limite en :math:`-2` et en :math:`2`

#. :math:`f` a une limite en :math:`-1` qui vaut :math:`2` et une limite
   en :math:`1` qui vaut :math:`2`

#. :math:`f(0)=3` et :math:`f(-2)=1`

#. :math:`f` a exactement deux racines et elles se trouvent entre
   :math:`1` et :math:`2`.

**Solution.**

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw (-4,-4)node{$\bullet$};
    \draw[thick] plot[domain=-4:-2.05](\x,{\x});
    \draw[thick, fill=white](-2,-2)circle(0.15);
    \draw (-2,1)node{$\bullet$};
    \draw[thick] plot[domain=-1.95:-0.05](\x,{1+0.5*(\x+2)*(\x+2)});
    \draw (0,3)node{$\bullet$};
    \draw[thick] plot[domain=0.05:0.95](\x,{-1*\x+3});
    \draw[thick, fill=white](1,2)circle(0.15);
    \draw[thick] plot[domain=1.09:1.95](\x,{(1+\x)*(cos(360*(\x-1)))});
    \draw[thick, fill=white](2,3)circle(0.15);
    \draw[thick, fill=white](2,-4)circle(0.15);
    \draw[thick] plot[domain=2.09:3](\x,{-4});
			\draw (3,-4)node{$\bullet$};

| 

3.2 Lien entre la continuité et les limites de fonctions
--------------------------------------------------------

Dans la section précédente, nous avons pu observer que dans certains
cas, la limite d’une fonction en un point où cette fonction est définie
existe et est simplement égale à la valeur de la fonction en ce point.
Dans tous les cas observés, la fonction était justement définie et
continue en ce point. Il ne s’agit pas d’un hasard.

**Théorème 3.2.1.** Soit un intervalle :math:`I`. Soit :math:`f : I \to \mathbb{R}`.
Soit :math:`c \in I`.
Alors :math:`f` est continue en :math:`c` si et seulement si :math:`f`
a une limite en :math:`c` et :math:`\lim\limits_{x \to c} f(x) =f(c)`.

Malheureusement, la démonstration de ce théorème sort du cadre de ce
cours.

**Remarque 3.2.2.** Il est vraiment dommage que nous ne puissions pas nous attarder sur la
démonstration de ce théorème. En effet, celui-ci permet de relier la
continuité aux limites, dont les définitions se ressemblent. Cette
ressemblance n’est pas anodine : historiquement, ces deux notions ont
été développées parallèlement et les mêmes idées ont été utilisées de
part et d’autre pour arriver aux définitions actuelles.

Nous pouvons néanmoins expliquer brièvement la démonstration du
théorème à partir de nos intuitions. Si une fonction est continue en
un point, cela correspond au fait que son graphe ne possède pas de
saut vertical en ce point, autrement dit que je peux approcher autant
que je le souhaite la valeur de cette fonction en ce point à condition
d’être assez proche de ce point. On retrouve assez directement
l’intuition de limite : si les abscisses du graphe de la fonction se
rapprochent du point considéré, les ordonnées se rapprochent donc
nécessairement de l’image de ce point par la fonction, autrement dit
la limite de la fonction en ce point est égale à l’image de la
fonction en ce point. L’autre sens de la démonstration est tout aussi
intuitif.

Avec ce théorème, nous pouvons calculer des limites de certaines
fonctions sans pour autant pouvoir/devoir réaliser leurs graphes !
Donnons immédiatement un exemple.

| 

**Exemple 3.2.3.**  Soit la fonction

.. math::

   \begin{aligned}
       f : \mathbb{R}&\to \mathbb{R}\\
       x &\mapsto x^3+\sqrt[3]{x}
       \end{aligned}

Supposons qu’on souhaite calculer la limite de cette fonction en
:math:`8`. Cette fonction est continue car c’est la somme de deux
fonctions de référence (la fonction cubique et la fonction racine
cubique) qui sont continues. Par le théorème 3.2.1, puisque
:math:`f` est bien définie et continue en :math:`2`, on peut donc
affirmer que la limite :math:`\lim\limits_{x \to 2}` existe et vaut
:math:`f(8)=8^3+\sqrt[3]{8}=514`.

**Exercice 3.2.4.** Calculer les limites suivantes et justifier.

.. inginious:: limite13_1
.. inginious:: limite13_2
.. inginious:: limite13_3
.. inginious:: limite13_4

3.3 Lien entre les prolongements continus et les limites de fonctions
---------------------------------------------------------------------

Dans la section précédente, nous avons vu que calculer la limite d’une
fonction en un point où elle est définie et continue est on ne peut plus
simple. Mais qu’en est-il si on veut calculer la limite d’une fonction
en un point où elle n’est pas définie ? Commençons avec un exemple.

**Exemple 3.3.1.** 

  Considérons la fonction :

  .. math::

     \begin{aligned}
         f : \mathbb{R}\backslash \{2\} &\to \mathbb{R}\\
         x &\mapsto \frac{x^2-4x+4}{x-2}
         \end{aligned}

  Cette fonction n’est pas définie en :math:`2` mais on pourrait se
  demander si elle possède malgré tout une limite en :math:`2`.
  Malheureusement, nous ne pouvons pas invoquer le théorème
  3.2.1 pour cette éventuelle limite puisque bien que la
  fonction soit continue partout sur son domaine de définition, elle
  n’est pas définie en :math:`2`.
  Si nous pouvions trouver un prolongement continu de cette fonction
  défini en :math:`2`, nous pourrions aisément calculer cette limite en
  appliquant le théorème 3.2.1. En fait, l’existence de ce
  prolongement continu correspond précisément à l’existence de la limite
  que nous recherchons et la valeur de cet éventuel prolongement continu
  en :math:`2` est précisément la valeur de la limite recherchée ?
  Dès lors, comment déterminer si la fonction :math:`f` possède un
  prolongement continu en :math:`2` ? Pour ce faire, jouons un peu avec
  l’expression de :math:`f` et simplifions. Pour tout
  :math:`x \in \mathbb{R}\backslash \{2\}` :

  .. math:: \frac{x^2-4x+4}{x-2}=\frac{(x-2)^2}{x-2}=x-2

  Pour tout :math:`x \in \mathbb{R}\backslash \{2\}`, nous avons donc
  :math:`f(x)=x-2`. Attention néanmoins : cette égalité est valable
  seulement si :math:`x \neq 2`. Elle n’a pas de sens si :math:`x=2`.
| 

  Malgré cela, remarquons que l’expression :math:`x-2` fait sens même si
  :math:`x=2` : :math:`2-2=0`. Autrement dit, si on pose :

  .. math::

     \begin{aligned}
         g : \mathbb{R}&\to \mathbb{R}\\
         x &\mapsto x-2
         \end{aligned}

  La fonction :math:`g` est définie partout même en :math:`2`, est
  continue (y compris en :math:`2`) et est telle que pour tout
  :math:`x \in \mathbb{R}\backslash \{2\}` : :math:`g(x)=f(x)`. Il
  s’agit d’un prolongement continu de :math:`f` !
| 
  
  Pour la fonction :math:`g`, nous pouvons appliquer le théorème
  3.2.1 : :math:`\lim\limits_{x \to 2} g(x)=g(2)=2-2=0`. Or,
  comme pour tout :math:`x \in \mathbb{R}\backslash \{2\}` :
  :math:`g(x)=f(x)`, on a donc :

  .. math:: \lim\limits_{x \to 2} f(x) = \lim\limits_{x \to 2} g(x) =0

  En conclusion, la limite que nous recherchions existe et vaut
  :math:`0`.

Dans l’exemple ci-dessus, nous avons relié l’existence d’une limite en
un point où une fonction n’était pas définie à l’existence d’un
prolongement continu de cette fonction en ce point. Nous avons vu qu’un
tel prolongement continu existait et que sa valeur au point où la
fonction initiale n’était pas définie correspondant précisément à la
valeur recherchée. Ce n’est pas un hasard :

|

**Théorème 3.3.2.** Soit un intervalle :math:`I`. Soit :math:`c \in I`. Soit :math:`f : I \backslash \{c\} \to \mathbb{R}`.

  Alors :math:`f` admet une limite en :math:`c` si et seulement si
  :math:`f` admet un prolongement continu en :math:`c`.
  De plus, si la valeur de cette éventuelle limite est égale à l’image
  de cet éventuel prolongement continu en :math:`c`.

Une fois de plus, nous ne pouvons malheureusement pas démontrer ce
théorème dans ce cours. Mais à ce stade, celui-ci ne devrait pas vous
surprendre. En effet, la notion de limite est précisément l’outil dont
nous avions besoin pour répondre aux trois questions finales de la
section `2.5 <#procont>`__. Grâce au théorème 3.3.2, nous
pouvons à présent calculer des limites un peu moins triviales que celles
que nous avons calculées dans la section précédente. En effet, lorsqu’on
souhaite calculer la limite d’une fonction en un point où elle n’est pas
défini, il suffit donc de rechercher un prolongement continu de cette
fonction, ce qui peut se faire en manipulant et en simplifiant son
expression.

|

**Exercice 3.3.3.** Les limites suivantes existent. Calculer celles-ci.

.. inginious:: limite1_1
.. inginious:: limite1_2
.. inginious:: limite1_3
.. inginious:: limite1_4
.. inginious:: limite1_5
.. inginious:: limite1_6
.. inginious:: limite1_7
.. inginious:: limite1_8

|

**Remarque 3.3.4.** Certaines personnes (pour être honnête : de nombreuses personnes) peu
rigoureuses appliquent parfois la conclusion du théorème
3.2.1 même dans des cas où cette application n’est pas
légitime, par exemple quand la fonction dont ils veulent calculer la
limite n’est pas définie au point où ils veulent déterminer
l’éventuelle limite. Pour donner un exemple précis, ces personnes
écrivent :

.. math:: \lim\limits_{x \to -1} \frac{x^2-1}{x+1}=\frac{(-1)^2-1}{-1+1}=\frac{0}{0}

Ces personnes appellent alors ce genre de situation une
indétermination .

**Je vous interdis de faire de même dans ce cours.**

Ce type de pratique est non rigoureuse et illogique (on applique un
théorème alors que les hypothèses de ce théorème ne sont pas
respectées), dangereuse (cela nuit à la compréhension de l’idée de
limite (et d’infini) et fait écrire des suites de symboles qui n’ont pas
de sens) et inutile (de nombreux mathématiciens dans le monde calculent
des limites très efficacement sans avoir besoin d’écrire de telles
horreurs). Plutôt que de ne pas réfléchir et d’écrire de façon
automatique des choses qui n’ont pas de sens, prenez toujours le temps
de vérifier si les hypothèses des résultats que vous souhaitez invoquer
sont vérifiées et d’être certain de comprendre ce que vous êtes en train
de faire.

|

3.4 Divergence de fonctions en un point
---------------------------------------

| Lorsqu’une fonction possède une limite en un point, on dit qu’elle
  *converge* en ce point. Que peut-il se passer lorsque qu’une fonction
  ne converge pas en un point, c’est-à-dire ne possède pas de limite en
  ce point ?
| Il y a de nombreuses possibilités, mais une de ces possibilités est
  particulièrement intéressante : la fonction peut diverger. Pour
  découvrir cette nouvelle notion, commençons avec un exemple.

**Exemple 3.4.1.** Considérons la fonction :

.. math::

   \begin{aligned}
       f : {{\mathbb{R}}_{0}}^{+} &\to \mathbb{R}\\
       x &\mapsto \frac{1}{\sqrt{x}}
       \end{aligned}

dont voici le graphe :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[samples=50,domain=0.04:5](\x,{1/(sqrt(\x))});

Que se passe-t-il quand les :math:`x` se rapprochent de :math:`0` ? Les
:math:`f(x)` ne se rapprochent certainement pas d’un nombre réel ! Si on
teste avec certaines valeurs de :math:`x` qui se rapprochent de
:math:`0`, on constate immédiatement que les :math:`f(x)` deviennent de
plus en plus grands :

.. math:: f(\frac{1}{100})=\frac{1}{\sqrt{\frac{1}{100}}}= \frac{1}{\frac{1}{10}}=10

.. math:: f(\frac{1}{10000})=\frac{1}{\sqrt{\frac{1}{10000}}}= \frac{1}{\frac{1}{100}}=100

.. math:: f(\frac{1}{1000000})=\frac{1}{\sqrt{\frac{1}{1000000}}}= \frac{1}{\frac{1}{1000}}=1000

|

On remarque même qu’à condition de se rapprocher suffisament de
:math:`0`, les valeurs de la fonction deviendront aussi grandes que l’on
veut. Autrement dit, on peut se donner n’importe quelle borne
supérieure, les valeurs :math:`f(x)` de cette fonction dépassent par le
haut cette borne supérieure de façon uniforme et définitive à condition
de choisir des :math:`x` suffisament proche de :math:`0`. Ce
comportement est appelé divergence (vers :math:`+\infty`) et nous venons
d’en donner la définition intuitive.

Donnons à présent la définition rigoureuse de divergence (vers
:math:`+\infty`).

|

**Définition 3.4.2.** Soit un intervalle :math:`I` éventuellement privé d’un point :math:`c`. Soit :math:`f : I \to \mathbb{R}`.

  On dit que :math:`f` *diverge* (vers :math:`+\infty`) en :math:`c` si
  pour toute borne supérieure :math:`M >0`, il existe :math:`\delta > 0`
  tel que pour tout :math:`x \in I \backslash \{c\}` qui est à une
  distance plus petite ou égale de :math:`c` que :math:`\delta`,
  c’est-à-dire tel que :math:`|x-c| \le \delta`, on a nécessairement que
  :math:`f(x)` est plus grand ou égal à :math:`M`, c’est-à-dire que
  :math:`f(x)\ge M`.
  Dans ce cas, on note :

  .. math:: \lim\limits_{x \to c} f(x)=+\infty

**Remarque 3.4.3.** **Attention : cette remarque est extrêmement importante.**

  Lorsqu’une fonction diverge (vers :math:`+\infty`) en un point, **elle
  n’a pas de limite en ce point**. Diverger vers :math:`+\infty` **ne
  signifie pas** se rapprocher d’un nombre appelé :math:`+\infty`
  (:math:`+\infty` **n’est pas** un nombre réel). On utilise pourtant la
  même notation pour parler de limite et de divergence : cela est
  extrêmement malheureux et absolument pas pédagogique. Cette notation
  étant néanmoins utilisée par tous, nous l’utiliserons également.

| Insistons bien : :math:`\lim\limits_{x \to c} f(x)=+\infty` **ne se
  lit pas** la fonction :math:`f` a comme limite/converge vers
  :math:`+\infty` en :math:`c` mais bien la fonction :math:`f` diverge
  vers :math:`+\infty` en :math:`c` . La convergence (avoir une limite)
  et la divergence sont deux notions complétement différentes.

|

**Exemple 3.4.4.** La fonction

.. math::

   \begin{aligned}
       f : {\mathbb{R}}_{0} &\to \mathbb{R}\\
       x &\mapsto \frac{1}{x^2}
       \end{aligned}

dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-0.44721](\x,{1/(\x*\x)});
    \draw[thick] plot[domain=0.44721:5](\x,{1/(\x*\x)});

diverge vers :math:`+\infty` en :math:`0`. On note :
:math:`\lim\limits_{x \to 0} \frac{1}{x^2}=+\infty`.

Il existe un autre phénomène possible lorsqu’une fonction ne converge
pas en un point, très semblable à la divergence vers :math:`+\infty` :
il s’agit de la divergence vers :math:`-\infty`. Pour l’introduire,
commençons avec un exemple.

|

**Exemple 3.4.5.** Considérons la fonction

.. math::

   \begin{aligned}
       f : \mathbb{R}\backslash \{1\} &\to \mathbb{R}\\
       x &\mapsto \frac{-1}{|x-1|}
       \end{aligned}

dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:0.8](\x,{1/(abs(\x -1))});
    \draw[thick] plot[domain=1.2:5](\x,{1/(abs(\x -1))});
			

Que se passe-t-il quand les :math:`x` se rapprochent de :math:`1` ? À
nouveau, les :math:`f(x)` ne se rapprochent certainement pas d’un nombre
réel ! Si on teste avec certaines valeurs de :math:`x` qui se
rapprochent de :math:`1`, on constate immédiatement que les :math:`f(x)`
deviennent de plus en plus grands négativement :

.. math:: f(1+\frac{1}{100})=\frac{1}{\frac{1}{|100|}}= \frac{1}{\frac{1}{100}}=100

.. math:: f(1+\frac{1}{10000})=\frac{1}{\frac{1}{|10000|}}= \frac{1}{\frac{1}{10000}}=10000

.. math:: f(1+\frac{1}{1000000})=\frac{1}{\frac{1}{|1000000|}}= \frac{1}{\frac{1}{1000000}}=1000000

.. math:: f(1-\frac{1}{100})=\frac{1}{\frac{1}{|-100|}}= \frac{1}{\frac{1}{100}}=100

.. math:: f(1-\frac{1}{10000})=\frac{1}{\frac{1}{|-10000|}}= \frac{1}{\frac{1}{10000}}=10000

.. math:: f(1-\frac{1}{1000000})=\frac{1}{\frac{1}{|-1000000|}}= \frac{1}{\frac{1}{1000000}}=1000000

On remarque même qu’à condition de se rapprocher suffisament de
:math:`1`, les valeurs de la fonction deviendront aussi grandes
négativement que l’on veut. Autrement dit, on peut se donner n’importe
quelle borne inférieure, les valeurs :math:`f(x)` de cette fonction
dépassent par le bas cette borne supérieure de façon uniforme et
définitive à condition de choisir des :math:`x` suffisament proche de
:math:`1`. Ce comportement est appelé divergence (vers :math:`-\infty`)
et nous venons d’en donner la définition intuitive.

Donnons à présent la définition rigoureuse de divergence (vers
:math:`-\infty`).

|

**Définition 3.4.6.** Soit un intervalle :math:`I` éventuellement privé d’un point :math:`c`. Soit :math:`f : I \to \mathbb{R}`.

  On dit que :math:`f` *diverge* (vers :math:`-\infty`) en :math:`c` si
  pour toute borne supérieure :math:`M >0`, il existe :math:`\delta > 0`
  tel que pour tout :math:`x \in I \backslash \{c\}` qui est à une
  distance plus petite ou égale de :math:`c` que :math:`\delta`,
  c’est-à-dire tel que :math:`|x-c| \le \delta`, on a nécessairement que
  :math:`f(x)` est plus grand ou égal à :math:`M`, c’est-à-dire tel que
  :math:`f(x)\le M`.
  Dans ce cas, on note :

  .. math:: \lim\limits_{x \to c} f(x)=-\infty

**Remarque 3.4.7.** Même remarque que pour la divergence vers :math:`+\infty` : diverger
vers :math:`-\infty` **ne signifie pas** avoir comme limite un nombre
appelé :math:`-\infty`.

|

**Exemple 3.4.8.** La fonction

.. math::

   \begin{aligned}
       f : ]2;+\infty[ &\to \mathbb{R}\\
       x &\mapsto \frac{-1}{\sqrt{x-2}}
       \end{aligned}

dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-8) grid (8,5);

      \draw[very thick,->] (-5,0) -- (9,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-8) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[samples=50,domain=2.01563:8](\x,{-1/(sqrt(\x - 2))});
			

diverge vers :math:`-\infty` en :math:`2`. On note :
:math:`\lim\limits_{x \to 2} \frac{-1}{\sqrt{x-2}}=-\infty`.


| Les trois notions de convergence (avoir une limite), divergence vers
  :math:`+\infty` et divergence
| vers :math:`-\infty` sont mutuellement exclusives. En effet :

-  | Si une fonction converge (a une limite) en un point, ses valeurs ne
     peuvent pas devenir arbitrairement grandes (que ce soit
     positivement ou négativement) puisque qu’elle se rapproche de la
     limite (qui est un nombre réel).

-  Si une fonction diverge vers :math:`+\infty` en un point, ses valeurs
   ne peuvent se rapprocher d’un nombre réel (puisque celles-ci
   deviennent de plus en plus grandes positivement au fur et à mesure
   qu’on se rapproche du point où la fonction diverge) et ne peuvent
   devenir arbitrairement grandes négativement (puisque celles-ci
   deviennent de plus en plus grandes **positivement** au fur et à
   mesure qu’on se rapproche du point où la fonction diverge).

-  Si une fonction diverge vers :math:`-\infty` en un point, ses valeurs
   ne peuvent se rapprocher d’un nombre réel (puisque celles-ci
   deviennent de plus en plus grandes négativement au fur et à mesure
   qu’on se rapproche du point où la fonction diverge) et ne peuvent
   devenir arbitrairement grandes négativement (puisque celles-ci
   deviennent de plus en plus grandes **négativement** au fur et à
   mesure qu’on se rapproche du point où la fonction diverge).

|  
| Pour résumer ces trois remarques, nous avons la proposition suivante :

|

**Proposition 3.4.9.** Soit un intervalle :math:`I` éventuellement privé d’un point :math:`c`. Soit :math:`f : I \to \mathbb{R}`.

-  Si :math:`f` possède une limite en :math:`c`, alors :math:`f` ne
   diverge pas vers :math:`+\infty` en :math:`c` et ne diverge pas vers
   :math:`-\infty` en :math:`c`.

-  Si :math:`f` diverge vers :math:`+\infty` en :math:`c`, alors
   :math:`f` ne possède pas une limite en :math:`c` et ne diverge pas
   vers :math:`-\infty` en :math:`c`.

-  Si :math:`f` diverge vers :math:`-\infty` en :math:`c`, alors
   :math:`f` ne possède pas une limite en :math:`c` et ne diverge pas
   vers :math:`+\infty` en :math:`c`.

|  
|  
|  
| Avant de nous lancer dans les exercices pour nous familiariser avec
  ces deux nouvelles notions de divergence vers :math:`+\infty` et de
  divergence vers :math:`-\infty`, donnons quelques exemples et
  contre-exemples supplémentaires.

|

**Contre-exemple 3.4.10.** Les seules fonctions de référence qui ne sont pas définies sur tout :math:`\mathbb{R}` sont la fonction racine carrée et la fonction
inverse. Nous savons déjà que la fonction racine carrée a comme limite
:math:`0` lorsque :math:`x` tend vers :math:`0`, mais qu’en est-il de
la fonction inverse ? Diverge-t-elle ?
Rappelons que la fonction inverse est la fonction :

.. math::

   \begin{aligned}
      f : {\mathbb{R}}_{0} &\to \mathbb{R}\\
      x &\mapsto \frac{1}{x}
      \end{aligned}

Son graphe est le suivant.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-0.2](\x,{1/(\x)});
    \draw[thick] plot[domain=0.2:5](\x,{1/(\x)});
			

Lorsque les :math:`x \in {\mathbb{R}}_{0}` se rapprochent de :math:`0`,
les nombres :math:`\frac{1}{x}` ne se rapprochent certainement pas d’un
nombre de manière uniforme et définitive. Mais ils ne deviennent pas non
plus arbitrairement grands positivement de manière uniforme et
définitive (ils le deviennt à droite de :math:`0`, mais pas à gauche )
et ils ne deviennent pas non plus arbitrairement grands négativement de
manière uniforme et définitive (ils le deviennt à gauche de :math:`0`,
mais pas à droite ). En conclusion, la fonction inverse n’a pas de
limite en :math:`0`, mais ne diverge pas non plus en :math:`0` (que ce
soit vers :math:`+\infty` ou vers :math:`-\infty`).

**Remarque 3.4.11.** La fonction inverse ne diverge pas vers :math:`+\infty` ou vers
:math:`-\infty` en :math:`0`, mais par contre son produit avec elle-même
diverge vers :math:`+\infty` en :math:`0` : voir exemple
3.4.4.

|

**Exemple 3.4.12.** La fonction :math:`f : \mathbb{R}\backslash \{-1\} \to \mathbb{R}` dont
le graphe est le suivant :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-1.125](\x,{-3-1/(\x +1)});
    \draw[thick] plot[samples=50,domain=-0.993:5](\x,{-1*ln(\x+1)});
			

diverge vers :math:`+\infty` en :math:`-1`. On note :
:math:`\lim\limits_{x \to 0} f(x) = -\infty`.

**Exemple 3.4.13.** La fonction :math:`f : [0;+\infty[ \to \mathbb{R}` dont le graphe est le
suivant :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
      \draw[thick] plot[samples=50,domain=0.007:5](\x,{ln(\x)});
		\draw (0,4)node{$\bullet$};
			

diverge vers :math:`-\infty` en :math:`0` (même si la fonction est
définie en :math:`0` de telle sorte que :math:`f(0)=4`). On note :
:math:`\lim\limits_{x \to 0} f(x) = -\infty`.

|

**Contre-exemple 3.4.14.** La fonction :math:`f : \mathbb{R}\to \mathbb{R}` dont le graphe est le
suivant :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-1.125](\x,{-3-1/(\x +1)});
    \draw[thick] plot[samples=50,domain=-0.993:5](\x,{ln(\x+1)});
    \draw (-1,0)node{$\bullet$};
          

ne converge pas et ne diverge pas en :math:`-1`.

**Contre-exemple 3.4.15.** La fonction :math:`f : \mathbb{R}\backslash \{0\} \to \mathbb{R}` dont
le graphe est le suivant :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[samples=50,domain=0.007:5](\x,{ln(\x)});
        \draw (0,3.5)node{$\bullet$};
    \draw[thick] plot[domain=-5:0](\x,{3.5});
			

ne converge pas et ne diverge pas en :math:`0`.

|

À présent, exerçons-nous un peu.

**Exercice 3.4.16.** À l’aide d’un graphique, déterminer si les fonctions divergent au point
considéré. Si oui, donner le type de divergence (vers :math:`+\infty` ou
vers :math:`-\infty`).

.. inginious:: limite2_1
.. inginious:: limite2_2
.. inginious:: limite2_3
.. inginious:: limite2_4

|

**Exercice 3.4.17.** Voici le graphe d'une fonction réelle :math:`f`. Déterminer l’ensemble
des points où elle diverge.

.. inginious:: limite14

|

**Exercice 3.4.18.** Tracer le graphe d’une fonction :math:`f` définie sur
:math:`\mathbb{R}\backslash \{-2;0\}` qui diverge vers :math:`-\infty`
en :math:`-2` et qui ne diverge et ne converge pas en :math:`0`.

**Solution.**

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
      \draw[thick] plot[domain=-5:-2.3536](\x,{3-1/((\x+2)*(\x+2))});
      \draw[thick] plot[domain=-1.4453:-0.05](\x,{-1.75-1/((\x+2)*(\x+2))});
      \draw[thick, fill=white](0,-2)circle(0.15);
      \draw[thick] plot[domain=0.2:5](\x,{1/(\x)});

|

**Exercice 3.4.19.** Déterminer si les fonctions dont les graphes sont donnés ci-dessous divergent aux points indiqués.

.. hlist::
   :columns: 2

   * .. tikz:: 

      \draw[step=1cm,gray,very thin] (-4,-4) grid (4,4);

      \draw[very thick,->] (-4,0) -- (5,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-4) -- (0,5) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
      \draw[thick] plot[domain=0.046:5,samples=100,xshift=-28](\x,{-ln(\x)});

   * :math:`\lim\limits_{x\to 2}f(x)`

   * .. tikz:: 

      \draw[step=1cm,gray,very thin] (-4,-4) grid (4,4);

      \draw[very thick,->] (-4,0) -- (5,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-4) -- (0,5) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
      \draw[thick] plot[domain=-2.65:1,samples=100](\x,{0.3*(\x*\x-2*\x+1)-1});
      \draw[thick] plot[domain=0.3333:3.1,samples=100,xshift=25](\x,{1/\x});
      \draw [thick] (1,-1) node[circle,fill=white,draw=black,inner sep=0.4mm] {};

   * :math:`\lim\limits_{x\to 1}f(x)`

   * .. tikz:: 

      \draw[step=1cm,gray,very thin] (-4,-4) grid (4,4);

      \draw[very thick,->] (-4,0) -- (5,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-4) -- (0,5) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
      \draw[thick] plot[domain=-4:2,samples=100](\x,0.5*\x);
      \draw[thick] plot[domain=2:4,samples=100](\x,-1.5*\x + 5);
      \draw [thick] (2,1) node[circle,fill=white,draw=black,inner sep=0.4mm] {};
      \draw [thick] (2,2) node[circle,fill=white,draw=black,inner sep=0.4mm] {};
      \draw [thick] (2,-1) node[circle,fill=black,draw=black,inner sep=0.4mm] {};

   * :math:`\lim\limits_{x\to 0}f(x)`

   * .. tikz:: 

      \draw[step=1cm,gray,very thin] (-4,-4) grid (4,4);

      \draw[very thick,->] (-4,0) -- (5,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-4) -- (0,5) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
      \draw[thick] plot[domain=-4.135:-0.499,samples=100,xshift=4](\x,{-1/(\x*\x)+2});
      \draw[thick] plot[domain=0.577:4.27,samples=100,xshift=-8](\x,{-1/(\x*\x)+1});
      \draw [thick] (0,2) node[circle,fill=black,draw=black,inner sep=0.4mm] {};

   * :math:`\lim\limits_{x\to 0}f(x)`

   * .. tikz:: 

      \draw[step=1cm,gray,very thin] (-4,-4) grid (4,4);

      \draw[very thick,->] (-4,0) -- (5,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-4) -- (0,5) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
      \draw[thick] plot[domain=-4:1.75,samples=100](\x,{-1-1/(\x-2)});
      \draw[thick] plot[domain=2:4,samples=100](\x,2);
      \draw [thick] (2,2) node[circle,fill=white,draw=black,inner sep=0.4mm] {};
      \draw [thick] (2,1) node[circle,fill=black,draw=black,inner sep=0.4mm] {};

   * :math:`\lim\limits_{x\to 2}f(x)`

   * .. tikz:: 

      \draw[step=1cm,gray,very thin] (-4,-4) grid (4,4);

      \draw[very thick,->] (-4,0) -- (5,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-4) -- (0,5) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
      \draw[thick] plot[domain=-4.48:-0.48,samples=100,xshift=13](\x,{-1/\x-0.1});
      \draw[thick] plot[domain=0.48:4.48,samples=100,xshift=-13](\x,{-1/\x+2.1});
      \draw [thick] (0,2) node[circle,fill=black,draw=black,inner sep=0.4mm] {};
      \draw [thick] (0,0) node[circle,fill=white,draw=black,inner sep=0.4mm] {};

   * :math:`\lim\limits_{x\to 0}f(x)`

   * .. tikz:: 

      \draw[step=1cm,gray,very thin] (-4,-4) grid (4,4);

      \draw[very thick,->] (-4,0) -- (5,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-4) -- (0,5) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
      \draw[thick] plot[domain=-4:4,samples=100](\x,2);

   * :math:`\lim\limits_{x\to -\pi}f(x)`

   * .. tikz:: 

      \draw[step=1cm,gray,very thin] (-4,-4) grid (4,4);

      \draw[very thick,->] (-4,0) -- (5,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-4) -- (0,5) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
      \draw[thick] plot[domain=-4.135:-2.499,samples=100,xshift=4](\x,{-1/((\x+2)*(\x+2))+2});
      \draw[thick] plot[domain=2.577:4.27,samples=100,xshift=-8](\x,{-1+1/((\x-2)*(\x-2))+1});
      \draw [thick] (-2,2) node[circle,fill=black,draw=black,inner sep=0.4mm] {};
      \draw [thick] (2,-1) node[circle,fill=black,draw=black,inner sep=0.4mm] {};

   * :math:`\lim\limits_{x\to 2}f(x)`


 
**Solution.**

.. hlist::
   :columns: 2

   * :math:`\lim\limits_{x\to -1}f(x)=+\infty`

   * La fonction ne diverge pas en :math:`1`.

   * La fonction ne diverge pas en :math:`2`.

   * :math:`\lim\limits_{x\to 0}f(x)=-\infty`

   * La fonction ne diverge pas en :math:`2`.

   * La fonction ne diverge pas en :math:`0`.

   * La fonction ne diverge pas en :math:`-\pi`.

   * :math:`\lim\limits_{x\to 2}f(x)=+\infty`.

|

**Exercice 3.4.20** Tracer le graphe d’une fonction :math:`f` ayant les propriétés suivantes
:

.. hlist::
  :columns: 2

   * dom :math:`f=]-4,3]`

   * :math:`f` est continue partout sauf en :math:`-2` et :math:`3`.

   * :math:`\lim\limits_{x\to -4}f(x)=+\infty`

   * :math:`\lim\limits_{x\to 3}f(x)=-\infty`

**Solution.**

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-3.8:-2.05](\x,{1/(\x+4)});
    \draw[thick, fill=white](-2,0.5)circle(0.15);
    \draw (-2,1.609)node{$\bullet$};
    \draw[thick] plot[domain=-1.95:2.9933](\x,{ln(-1*\x+3)});
    \draw (3,1)node{$\bullet$};
			
|

**Exercice 3.4.21** Tracer le graphe d’une fonction
:math:`f : ]-\infty;-3[ \cup ]-3;2[ \cup ]2;4] \to \mathbb{R}` qui est
continue partout sauf en :math:`-1` et :math:`0`, qui a comme limite
:math:`1` en :math:`-1` et comme limite :math:`\frac{1}{2}` en
:math:`4`, qui n’a pas de limite en :math:`0`, qui diverge vers
:math:`+\infty` en -3 et qui ne diverge pas en :math:`2`.

**Solution.**

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-3.4472](\x,{1/((\x+3)*(\x+3))});
    \draw[thick] plot[domain=-2.7777:-1.05](\x,{0.5+1/(\x+3)});
    \draw[thick, fill=white](-1,1)circle(0.15);
    \draw (-1,-1)node{$\bullet$};
    \draw[thick] plot[domain=-0.95:-0.05](\x,{-1-2*\x});
    \draw (0,-1)node{$\bullet$};
    \draw[thick, fill=white](0,-3)circle(0.15);
    \draw[thick] plot[domain=0.05:1.95](\x,{\x-3});
    \draw[thick, fill=white](2,-1)circle(0.15);
    \draw[thick] plot[domain=2.2:4](\x,{1/(\x-2)});
			\draw (4,0.5)node{$\bullet$};
			
|

**Exercice 3.4.22** Déterminer si les fonctions convergent ou divergent au point considéré.
Si elles convergent, donner la limite. Si elles divergent, donner le
type de divergence (vers :math:`+\infty` ou vers :math:`-\infty`).

.. inginious:: limite3_1
.. inginious:: limite3_2
.. inginious:: limite3_3
.. inginious:: limite3_4
.. inginious:: limite3_5
.. inginious:: limite3_6
.. inginious:: limite3_7
.. inginious:: limite3_8

|

3.5 Limites à gauche et limites à droite
----------------------------------------

| Dans certains cas, il peut être intéressant d’étudier le comportement
  d’une fonction au fur et à mesure que l’on se rapproche d’un point où
  il est possible de parler de limite pour cette fonction mais en ne
  considérant que les points du graphe de la fonction dont les abscisses
  sont plus grandes ou plus petites que le point considéré.
| Donnons immédiatement un exemple.

**Exemple 3.5.1.** La fonction :math:`f : \mathbb{R}\to \mathbb{R}` dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:0](\x,{1/(\x - 1)});
    \draw[thick] plot[domain=0:5](\x,{1/(\x + 1)});
    \draw (0,-1)node{$\bullet$};
    \draw[thick, fill=white](0,1)circle(0.15);
          

| n’a pas de limite en :math:`0`. Lorsque les abscisses se rapprochent
  de :math:`0`, les points du graphe de :math:`f` ne se rapprochent pas
  définitivement et uniformément d’une seule valeur.
|  
| Par contre, si nous ne considérons que les points du graphe dont les
  abscisses sont supérieures à :math:`0`, la fonction réduite
  :math:`f_{[0;+\infty[} : [0;+\infty[ \to \mathbb{R}` possède bien une
  limite en :math:`0` :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=0:5](\x,{1/(\x + 1)});
    \draw (0,-1)node{$\bullet$};
    \draw[thick, fill=white](0,1)circle(0.15);
			

On a : :math:`\lim\limits_{x \to 0} f_{[0;+\infty[} (x) = 1`. De même,
si nous ne considérons que les points du graphe dont les abscisses sont
inférieures à :math:`0`, la fonction réduite
:math:`f_{]-\infty;0]} : ]-\infty;0] \to \mathbb{R}` possède bien une
limite en :math:`0` :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:0](\x,{1/(\x - 1)});
    \draw (0,-1)node{$\bullet$};
			

| On a : :math:`\lim\limits_{x \to 0} f_{]-\infty;0]} (x) = -1`.
|  
| Une autre façon d’exprimer ce que nous venons de dire est d’utiliser
  les notions de limite à gauche et de limite à droite. Lorsqu’on
  affirme que :math:`\lim\limits_{x \to 0} f_{[0;+\infty[} (x) = 1`,
  cela signifie précisément que la fonction :math:`f` possède une limite
  à droite de 0 et que celle-ci vaut :math:`1`, ce qu’on note :

  .. math:: \lim\limits_{x \underset{>}{\to} 0} f = 1

  Lorsqu’on affirme que
  :math:`\lim\limits_{x \to 0} f_{]-\infty;0]} (x) = -1`, cela signifie
  précisément que la fonction :math:`f` possède une limite à gauche de 0
  et que celle-ci vaut :math:`-1`, ce qu’on note :

  .. math:: \lim\limits_{x \underset{<}{\to} 0} f = 1

Donnons à présent la définition générale de limite à droite et de limite
à gauche : il s’agit simplement d’utiliser la définition de limite et de
restriction de fonction.

|

**Définition 3.5.2.** Soit un intervalle :math:`I` éventuellement privé d’un point :math:`c`. Soit :math:`f : I \to \mathbb{R}`.

  On dit que :math:`f` a *une limite à droite* :math:`L \in \mathbb{R}`
  en :math:`c` si la fonction
  :math:`f_{[c;+\infty[} : I \cap [c;+\infty[ \to \mathbb{R}` a comme
  limite :math:`L` en :math:`c`. On note :

  .. math:: \lim\limits_{x \underset{>}{\to} c} f(x)=L

  On dit que :math:`f` a *une limite à gauche* :math:`L \in \mathbb{R}`
  en :math:`c` si la fonction
  :math:`f_{]-\infty;c]} : I \cap ]-\infty;c] \to \mathbb{R}` a comme
  limite :math:`L` en :math:`c`. On note :

  .. math:: \lim\limits_{x \underset{<}{\to} c} f(x)=L

**Remarque 3.5.3.** Certaines personnes préfèrent utiliser les notations
:math:`\lim\limits_{x \to c^{+}} f(x)` pour les limites à droite et
:math:`\lim\limits_{x \to c^{-}} f(x)` pour les limites à gauche. Je
vous déconseille d’utiliser ces notations.

Donnons quelques exemples et contre-exemples.

|

**Exemple 3.5.4.** La fonction :math:`f : \mathbb{R}\to \mathbb{R}` dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:0.8](\x,{1/(\x - 1)});
    \draw[thick] plot[domain=1:5](\x,{1+1/(\x)});
    \draw (1,-1)node{$\bullet$};
    \draw[thick, fill=white](1,2)circle(0.15);
			

| a une limite à droite en :math:`1` qui vaut :math:`2` :
  :math:`\lim\limits_{x \underset{>}{\to} 1} f(x)=2`.
| Par contre, elle n’a pas de limite à gauche en :math:`1`.

**Exemple 3.5.5.** La fonction carrée :math:`f : \mathbb{R}\to \mathbb{R}` dont le graphe
est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-2.236:2.236](\x,{\x * \x});
			

| a une limite à droite en :math:`-2` qui vaut :math:`4` :
  :math:`\lim\limits_{x \underset{>}{\to} -2} f(x)=4`.
| Par ailleurs, :math:`f` a aussi une limite à gauche en :math:`-2` qui
  vaut aussi :math:`4` :
  :math:`\lim\limits_{x \underset{<}{\to} -2} f(x)=4`.

|

**Contre-exemple 3.5.6.** La fonction inverse :math:`f : \mathbb{R}\to \mathbb{R}` dont le graphe
est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-0.2](\x,{1/(\x)});
    \draw[thick] plot[domain=0.2:5](\x,{1/(\x)});
			

n’a pas de limite à droite en :math:`0` et n’a pas de limite à gauche en
:math:`0`.

|

Dans tous les exemples déjà rencontrés, remarquons que le seul où la
fonction admet une limite à droite et une limite à gauche au point
considéré et que ces deux limites sont égales correspond au cas où la
fonction admet une (véritable) limite en ce point, qui est d’ailleurs
égale à l’unique valeur de la limite à droite et de la limite à gauche.

Ce n’est pas un hasard : pour avoir une limite en un point :math:`c`,
une fonction :math:`f` doit se rapprocher de façon définitive et
uniforme d’une unique valeur, elle doit donc avoir une limite à gauche
en ce point et une limite à droite en ce point et celles-ci doivent être
identiques. L’inverse est vrai aussi : si une fonction :math:`f` a une
limite à gauche en un point :math:`c` et une limite à droite en
:math:`c` et que celles-ci sont égales, alors :math:`f` se rapprochent
bien définitivement et uniformément de cet unique nombre au fur et à
mesure qu’on se rapproche de :math:`c` ! Plus rigoureusement, on peut
démontrer :

**Proposition 3.5.7.** Soit un intervalle :math:`I` éventuellement privé d’un point :math:`c`. Soit :math:`f : I \to \mathbb{R}`.

  Alors :math:`f` possède une limite
  :math:`\lim\limits_{x \to c} f(x)=L` en :math:`c` si et seulement si
  :math:`f` possède une limite à droite
  :math:`\lim\limits_{x \underset{>}{\to} c} f(x)` en :math:`c` et une
  limite à gauche :math:`\lim\limits_{x \underset{<}{\to} c} f(x)` en
  :math:`c` et que celles-ci sont égales :
  :math:`\lim\limits_{x \underset{>}{\to} c} f(x)=\lim\limits_{x \underset{<}{\to} c} f(x)`.

| Ce résultat est assez intuitif. Malheureusement, nous ne le
  démontrerons pas dans le cadre de ce cours.

**Remarque 3.5.8.** Certaines personnes aiment beaucoup les limites à droite et les
limites à gauche, à tel point qu’elles définissent celles-ci en
premier et les utilisent pour définir la notion de limite générale.

Pourtant, c’est bien la notion de limite qui est fondamentale, si
utile et qui permet de démontrer d’impressionnants résultats
mathématiques. De plus, les notions de limite à droite et limite à
gauche ne se généralisent pas lorsqu’on ne peut pas parler de droite
et de gauche tandis que la notion de limite plus gobale se généralise
dans de nombreux contextes.

Pour ces raisons, nous n’insisterons volontairement pas sur les
notions de limites à droite et de limite à gauche dans ce cours.

|

| Avant de nous familiariser un peu avec ces nouvelles notions que sont
  les limites à droite et les limites à gauche, découvrons l’équivalent
  de ces notions pour la divergence. Commençons avec un exemple.

**Exemple 3.5.9.** Considérons la fonction inverse
:math:`f : {\mathbb{R}}_{0}\to \mathbb{R}` dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-0.2](\x,{1/(\x)});
    \draw[thick] plot[domain=0.2:5](\x,{1/(\x)});
			

Comme nous l’avons vu dans la section précédente, cette fonction ne
diverge pas (que ce soit vers :math:`+\infty` ou :math:`-\infty` en
:math:`0`). Par contre, si nous ne considérons que les points de son
domaine qui sont plus grands ou égaux à :math:`0`, on obtient la
fonction :math:`f_{[0;+\infty[} : ]0;+\infty[ \to \mathbb{R}` dont le
graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=0.2:5](\x,{1/(\x)});
			

| Cette fonction diverge bien vers :math:`+\infty` en :math:`0` :
  :math:`\lim\limits_{x \to 0} f_{[0;+\infty[}(x)=+\infty`.
| De même, si nous ne considérons que les points du domaine de la
  fonction inverse qui sont plus petits ou égaux à :math:`0`, on obtient
  la fonction
  :math:`f_{]-\infty;0]} : ]-\infty;0[]-\infty;0[ \to \mathbb{R}` dont
  le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-0.2](\x,{1/(\x)});
			

| Cette fonction diverge bien vers :math:`+\infty` en :math:`0` :
  :math:`\lim\limits_{x \to 0} f_{[0;+\infty[}(x)=+\infty`.
|  
| Comme avec les limites à droite et les limites à gauche, on peut
  exprimer ce que nous venons de dire avec les notions de divergence à
  droite et divergence à gauche . Pour cette exemple, on peut dire que
  la fonction inverse :math:`f` diverge vers :math:`+\infty` à droite de
  :math:`0`, ce qu’on note
  :math:`\lim\limits_{x \underset{>}{\to} 0} f(x) = +\infty` et qu’elle
  diverge vers :math:`-\infty` à gauche de :math:`0`, ce qu’on note
  :math:`\lim\limits_{x \underset{<}{\to} 0} f(x) = -\infty`.

|  
| Pour donner la définition générale de divergence à droite et de
  divergence à gauche, il suffit de combiner les notions de divergence
  générale avec celle de restriction.

|

**Définition 3.5.10.** Soit un intervalle :math:`I` éventuellement privé d’un point :math:`c`. Soit :math:`f : I \to \mathbb{R}`.

  On dit que :math:`f` *diverge vers :math:`+\infty` à droite* en
  :math:`c` si la fonction
  :math:`f_{[c;+\infty[} : I \cap [c;+\infty[ \to \mathbb{R}` diverge
  vers :math:`+\infty` en :math:`c`. On note :

  .. math:: \lim\limits_{x \underset{>}{\to} c} f(x)=+\infty

  On dit que :math:`f` *diverge vers :math:`-\infty` à droite* en
  :math:`c` si la fonction
  :math:`f_{[c;+\infty[} : I \cap [c;+\infty[ \to \mathbb{R}` diverge
  vers :math:`-\infty` en :math:`c`. On note :

  .. math:: \lim\limits_{x \underset{>}{\to} c} f(x)=-\infty

  On dit que :math:`f` a *diverge vers :math:`+\infty` à gauche* en
  :math:`c` si la fonction
  :math:`f_{]-\infty;c]} : I \cap ]-\infty;c] \to \mathbb{R}` diverge
  vers :math:`+\infty` en :math:`c`. On note :

  .. math:: \lim\limits_{x \underset{<}{\to} c} f(x)=+\infty

  On dit que :math:`f` a *diverge vers :math:`-\infty` à gauche* en
  :math:`c` si la fonction
  :math:`f_{]-\infty;c]} : I \cap ]-\infty;c] \to \mathbb{R}` diverge
  vers :math:`-\infty` en :math:`c`. On note :

  .. math:: \lim\limits_{x \underset{<}{\to} c} f(x)=-\infty

  On a un résultat équivalent pour les divergence à gauche et à droite à
  celui qu’on avait pour les limites :

**Proposition 3.5.11.** Soit un intervalle :math:`I` éventuellement privé d’un point :math:`c`. Soit :math:`f : I \to \mathbb{R}`.

  Alors :math:`f` diverge vers :math:`+\infty` en :math:`c` si et
  seulement si :math:`f` diverge vers :math:`+\infty` à droite en
  :math:`c` et :math:`f` diverge vers :math:`+\infty` à gauche en
  :math:`c`.

  De plus, :math:`f` diverge vers :math:`-\infty` en :math:`c` si et
  seulement si :math:`f` diverge vers :math:`-\infty` à droite en
  :math:`c` et :math:`f` diverge vers :math:`-\infty` à gauche en
  :math:`c`.

| Une fois de plus, nous ne pourrons malheureusement pas démontrer cette
  proposition dans le cadre de ce cours.


|

| Avant de passer aux exercices, quelques exemples et contre-exemples.

**Exemple 3.5.12.** La fonction :math:`f : \mathbb{R}\to \mathbb{R}` dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:1.55279](\x,{1/((\x-2)*(\x-2))});
    \draw[thick] plot[domain=2.44721:5](\x,{1/((\x-2)*(\x-2))});
			

diverge vers :math:`+\infty` à droite en :math:`2` et diverge vers
:math:`+\infty` à gauche en :math:`2`. Elle diverge vers :math:`+\infty`
en :math:`2`.

**Exemple 3.5.13.** La fonction :math:`f : \mathbb{R}\to \mathbb{R}` dont le graphe est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:0.8](\x,{1/(\x - 1)});
    \draw[thick] plot[domain=1:5](\x,{1+1/(\x)});
    \draw (1,-1)node{$\bullet$};
    \draw[thick, fill=white](1,2)circle(0.15);
			

diverge vers :math:`-\infty` à gauche en :math:`1`. Elle ne diverge pas
à droite en :math:`1`.

**Exemple 3.5.14.** La fonction carrée :math:`f : \mathbb{R}\to \mathbb{R}` dont le graphe
est :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-2.236:2.236](\x,{\x * \x});
			

ne diverge ni à gauche ni à droite en :math:`-2`.

|

**Exercice 3.5.15.** Pour la fonction dont le graphe est ci-dessous, quels sont les points où
la fonction a une limite à gauche ou à droite mais n’a pas de limite ?
Quels sont les points où la fonction diverge à gauche ou à droite mais
ne diverge pas ? Pour tous ces points, donner les limites ou les
divergences à gauche ou à droite éventuelles.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-2.3536](\x,{3-1/((\x+2)*(\x+2))});
    \draw[thick] plot[domain=-1.4453:-0.05](\x,{-1.75-1/((\x+2)*(\x+2))});
    \draw[thick, fill=white](0,-2)circle(0.15);
    \draw[thick] plot[domain=0.2:5](\x,{1/(\x)});
			

**Solution.** Le seul point où la fonction n’a pas de limite ou ne diverge pas est
:math:`0`. La fonction a une limite à gauche en :math:`0` qui vaut
:math:`-2` et diverge vers :math:`+\infty` à droite en :math:`0`.

|

**Exercice 3.5.16.** Tracer le graphe d’une fonction :math:`f` ayant les propriétés suivantes
:

.. hlist::
   :columns: 2

   * dom :math:`f=[-2,2]`

   * :math:`f` est continue partout sauf en :math:`-1` et
   :math:`\frac{1}{2}`.

   * :math:`f(-1)=2`

   * :math:`\lim\limits_{x \underset{<}{\to} -1} f(x)` existe et est égale à
   :math:`2`.

   * :math:`\lim\limits_{x \underset{>}{\to} -1} f(x)` existe mais n’est pas
   égale à :math:`2`.

   * :math:`\lim\limits_{x \underset{<}{\to} \frac{1}{2}}f(x)=-\infty`

   * :math:`f(\frac{1}{2})=1`

   * :math:`\lim\limits_{x \underset{>}{\to} \frac{1}{2}}f(x)=+\infty`

**Solution.**

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw (-2,3)node{$\bullet$};
    \draw[thick] plot[domain=-2:-1](\x,{-\x+1});
    \draw (-1,2)node{$\bullet$};
    \draw[thick, fill=white](-1,-1.6666)circle(0.15);
    \draw[thick] plot[domain=-1:0.25](\x,{-1+1/(\x-(1/2))});
    \draw (0.5,1)node{$\bullet$};
    \draw[thick] plot[domain=0.66667:2](\x,{-1+1/(\x-(1/2))});
    \draw (2,-0.3333)node{$\bullet$};

|		

**Exemple 3.5.17.** Déterminer quelles sont les limites et les divergence à gauche et à droite.

.. inginious:: limite4_1
.. inginious:: limite4_2
.. inginious:: limite4_3
.. inginious:: limite4_4
.. inginious:: limite4_5

|  

**Exercice 3.5.18.** Tracer le graphe d’une fonction
:math:`f : ]-\infty;-3[ \cup ]-3;2[ \cup ]2;4] \to \mathbb{R}` qui est
continue partout sauf en :math:`-1` et :math:`0`, qui vaut :math:`1` en
:math:`-1`, :math:`4` en :math:`0` et :math:`-\frac{1}{2}` en :math:`4`,
qui a comme limite à gauche :math:`1` en :math:`-1` et comme limite à
droite :math:`-1` en :math:`1`, qui a comme limite à gauche :math:`-3`
en :math:`0` et qui diverge vers :math:`+\infty` à droite en :math:`0`,
qui diverge vers :math:`+\infty` à gauche en :math:`2` et qui diverge
vers :math:`-\infty` à droite en :math:`2`.

**Solution.**

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-3.4472](\x,{1/((\x+3)*(\x+3))});
    \draw[thick] plot[domain=-2.7777:-1.05](\x,{0.5+1/(\x+3)});
          \draw (-1,1)node{$\bullet$};
    \draw[thick, fill=white](-1,-1)circle(0.15);
    \draw[thick] plot[domain=-0.95:-0.05](\x,{-3-2*\x});
    \draw[thick, fill=white](0,-3)circle(0.15);
    \draw (0,4)node{$\bullet$};
    \draw[thick] plot[domain=0.14278:1](\x,{-2+1/(\x)});
    \draw[thick] plot[domain=1:1.857](\x,{-2-1/(\x-2)});
    \draw[thick, fill=white](2,-1)circle(0.15);
    \draw[thick] plot[domain=2.2:4](\x,{-1/(\x-2)});
          \draw (4,-0.5)node{$\bullet$};

|	

**Exercice 3.5.19.** Déterminer si les fonctions convergent ou divergent à droite ou à gauche
au point considéré. Si elles convergent à droite ou à gauche, donner la
limite à droite ou à gauche. Si elles divergent à droite ou à gauche,
donner le type de divergence (vers :math:`+\infty` ou vers
:math:`-\infty`). N’hésitez pas à vous aider d’un graphe.

.. inginious:: limite5_1
.. inginious:: limite5_2
.. inginious:: limite5_3
.. inginious:: limite5_4
.. inginious:: limite5_5


|

3.6 Limites et divergence de fonctions en :math:`+\infty` et :math:`-\infty`
----------------------------------------------------------------------------

| Jusqu’à présent, nous avons toujours parlé de limite ou de divergence
  d’une fonction :math:`f : I \to \mathbb{R}` en un point
  :math:`c \in \mathbb{R}`. Mais l’idée de limite (et de divergence)
  peut également être déclinée pour parler du comportement
  *asymptotique* d’une fonction, c’est-à-dire du comportement des
  nombres :math:`f(x)` pour des valeurs de l’argument :math:`x` qui
  deviennt de plus en plus grandes ou de plus en plus petites (grandes
  négativement).
| En fait, si nous avions introduit les limites et les divergences à
  l’aide des suites et non des fonctions continues, nous aurions
  commencé par ce type de limite et de divergence. L’idée fondamentale
  est la même que pour la limite d’une fonction en un point et est au
  moins aussi importante et utile.
| Une fois de plus, introduisons nos nouveaux concepts avec un exemple.

|

**Exemple 3.6.1.** Nous souhaiterions pouvoir parler du comportement asymptotique de la
fonction inverse, dont le graphe est pour rappel le suivant.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-0.2](\x,{1/(\x)});
    \draw[thick] plot[domain=0.2:5](\x,{1/(\x)});

|	

Nous aimerions savoir ce que deviennent les nombres :math:`f(x)` au fur
et à mesure que nous considérons des :math:`x` de plus en plus grands.
Voyons d’abord ce que vaut :math:`f(x)` pour certaines valeurs de
:math:`x` particulières qui sont de plus en plus grandes :

.. math:: f(10)=\frac{1}{10}= 0,1

.. math:: f(100)=\frac{1}{100}= 0,01

.. math:: f(1000)=\frac{1}{1000}= 0,001

.. math:: f(1000000)=\frac{1}{1000000}= 0,000001

.. math:: f(1000000000000000)=\frac{1}{1000000000000000}= 0,000000000000001

| Plus généralement, si nous divisons :math:`1` par des nombres positifs
  arbitrairement grands, le résultat sera un nombre positif
  arbitrairement proche de :math:`0`. Au fur à mesure que les abscisses
  :math:`x` des points du graphes grandissent, les ordonnées
  :math:`f(x)` associées se rapprochent uniformément et définitivement
  de :math:`0`. Nous retrouvons l’idée de limite : la nouveauté étant
  que nous observons le comportement de la fonction non pas à l’approche
  d’un point, mais son comportement pour des nombres de plus en plus
  grands.
| Pour cet exemple, on dit que la fonction inverse a pour limite
  :math:`0` quand :math:`x` tend vers :math:`+\infty`. On note :

  .. math:: \lim\limits_{x \to +\infty} \frac{1}{x}=0

   
| Nous pouvons également étudier le comportement de la fonction inverse
  pour des nombres de plus en plus petits ! Commençons avec des valeurs
  particulières pour :math:`x` qui sont de plus en plus petites :

  .. math:: f(-10)=\frac{1}{-10}= -0,1

  .. math:: f(-100)=\frac{1}{-100}= -0,01

  .. math:: f(-1000)=\frac{1}{-1000}= -0,001

  .. math:: f(-1000000)=\frac{1}{-1000000}= -0,000001

  .. math:: f(-1000000000000000)=\frac{1}{-1000000000000000}= -0,000000000000001

  Plus généralement, si nous divisons :math:`1` par des nombres négatifs
  arbitrairement petits, le résultat sera un nombre négatif
  arbitrairement proche de :math:`0`. Au fur à mesure que les abscisses
  :math:`x` des points du graphes diminuent, les ordonnées :math:`f(x)`
  associées se rapprochent uniformément et définitivement de :math:`0`.
  Nous retrouvons une fois de plus l’idée de limite : la nouveauté étant
  que nous observons le comportement de la fonction non pas à l’approche
  d’un point, mais son comportement pour des nombres de plus en plus
  petits.
| Pour cet exemple, on dit que la fonction inverse a pour limite
  :math:`0` quand :math:`x` tend vers :math:`-\infty`. On note :

  .. math:: \lim\limits_{x \to -\infty} \frac{1}{x}=0

|

**Remarque 3.6.2.** Il se trouve que la fonction inverse a la même limite pour :math:`x`
tendant vers :math:`+\infty` et pour :math:`x` tendant vers
:math:`-\infty`. Ce n’est bien évidemment pas toujours le cas. Par
exemple, la fonction dont le graphe est ci-dessous a comme limite
:math:`-1` pour :math:`x` tendant vers :math:`+\infty` et :math:`2` pour
:math:`x` tendant vers :math:`-\infty`.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-7,-5) grid (7,5);

      \draw[very thick,->] (-7,0) -- (8,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-7:-1](\x,{1-1/(\x)});
    \draw[thick] plot[domain=-1:1](\x,{(5/2)-(\x)*(\x)/2});
    \draw[thick] plot[domain=1:2](\x,{4-2*\x});
    \draw[thick] plot[domain=2:7](\x,{-2+8/((\x)*(\x))});
			

.. math:: \lim\limits_{x \to +\infty} \frac{1}{x}=-2

.. math:: \lim\limits_{x \to -\infty} \frac{1}{x}=1

Donnons les définitions de limite d’une fonction pour :math:`x` qui tend
vers :math:`+\infty` ou vers :math:`-\infty`. Celle-ci est très
similaire à la définition de limite d’une fonction en un point et est
construite de la même manière.

|

**Définition 3.6.3.** Soit un intervalle :math:`I` non majoré. Soit :math:`f : I \to \mathbb{R}`.

  On dit que :math:`f` a *une limite* :math:`L \in \mathbb{R}` pour
  :math:`x` qui tend vers :math:`+\infty` si pour toute marge d’erreur
  :math:`\epsilon >0`, il existe :math:`N > 0` tel que pour tout
  :math:`x \in I` qui est plus grand ou égal à :math:`N`, c’est-à-dire
  tel que :math:`x \ge N`, on a nécessairement que :math:`f(x)` est à
  une distance plus petite ou égale de :math:`L` que :math:`\epsilon`,
  c’est-à-dire qu’on a :math:`|f(x)-L| \le \epsilon`.
  Dans ce cas, on note :

  .. math:: \lim\limits_{x \to +\infty} f(x)=L

**Définition 3.6.4.** Soit un intervalle :math:`I` non minoré. Soit :math:`f : I \to \mathbb{R}`.
  
  On dit que :math:`f` a *une limite* :math:`L \in \mathbb{R}` pour
  :math:`x` qui tend vers :math:`-\infty` si pour toute marge d’erreur
  :math:`\epsilon >0`, il existe :math:`N < 0` tel que pour tout
  :math:`x \in I` qui est plus petit ou égal à :math:`N`, c’est-à-dire
  tel que :math:`x \le N`, on a nécessairement que :math:`f(x)` est à
  une distance plus petite ou égale de :math:`L` que :math:`\epsilon`,
  c’est-à-dire qu’on a :math:`|f(x)-L| \le \epsilon`.
  Dans ce cas, on note :

  .. math:: \lim\limits_{x \to -\infty} f(x)=L

|

Donnons quelques exemples et contre-exemples.

**Exemple 3.6.5.** La fonction dont le graphe est donné ci-dessous a comme limite :math:`3`
pour :math:`x` qui tend vers :math:`+\infty`.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
		\draw (-4,-2)node{$\bullet$};
    \draw[thick] plot[domain=-4:-2](\x,{(1/2)*\x});
        \draw (-2,-1)node{$\bullet$};
        \draw (2,2.5)node{$\bullet$};
    \draw[thick] plot[domain=2:5](\x,{3-1/(\x)});
			

.. math:: \lim\limits_{x \to +\infty} f(x)=3

Pour cette fonction, il ne fait pas sens de parler d’une éventuelle
limite pour :math:`x` qui tend vers :math:`-\infty` puisque son domaine
de définition est :math:`[-4;-2] \cup [2;\rightarrow[`.

**Exemple 3.6.6.** La fonction dont le graphe est donné ci-dessous a comme limite
:math:`-1` pour :math:`x` qui tend vers :math:`+\infty` et pour
:math:`x` qui tend vers :math:`-\infty`.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[samples=150,domain=-5:-0.01](\x,{-1+sin(3*180*\x)*(1/(3*\x))});
    \draw[thick] plot[samples=150,domain=0.01:5](\x,{-1+sin(3*180*\x)*(1/(3*\x))});
          

.. math:: \lim\limits_{x \to +\infty} f(x)=-1

.. math:: \lim\limits_{x \to -\infty} f(x)=-1

|

**Contre-exemple 3.6.7.** La fonction dont le graphe est donné ci-dessous n’a pas de limite pour
:math:`x` qui tend vers :math:`+\infty` et n’a pas de limite pour
:math:`x` qui tend vers :math:`-\infty`.

| Note : le graphe de cette fonction se répète : on dit qu’elle est
  périodique.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[samples=300,domain=-5:5](\x,{sin(3*180*\x)});
			

En effet, peu importe si on considère des nombres :math:`x` de plus en
plus grands ou de plus en plus petits, les nombres :math:`f(x)`
associées ne finiront jamais par se rapprocher de manière uniforme et
définitive d’une valeur unique. Ils continueront d’osciller autour de
:math:`0` encore et encore.

**Contre-exemple 3.6.8.** La fonction dont le graphe est donné ci-dessous n’a pas de limite pour
:math:`x` qui tend vers :math:`+\infty` mais a comme limite :math:`1`
pour :math:`x` qui tend vers :math:`-\infty`.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:4](\x,{1+(1/4)*2^\x});
			

.. math:: \lim\limits_{x \to -\infty} f(x)=1


|

| De la même manière qu’on peut parler d’une limite d’une fonction pour
  :math:`x` qui tend vers :math:`+\infty` ou pour :math:`x` qui tend
  vers :math:`-\infty`, on peut parler de la divergence vers
  :math:`+\infty` ou vers :math:`-\infty` pour :math:`x` qui tend vers
  :math:`+\infty` ou pour :math:`x` qui tend vers :math:`-\infty`. Une
  fois de plus, introduisons cette nouvelle notion avec un exemple.

**Exemple 3.6.9.** Nous souhaiterions pouvoir parler du comportement asymptotique de la
fonction cubique, dont le graphe est pour rappel le suivant.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-1.7099:1.7099](\x,{\x * \x * \x});
			

Nous aimerions savoir ce que deviennent les nombres :math:`f(x)` au fur
et à mesure que nous considérons des :math:`x` de plus en plus grands.
Voyons d’abord ce que vaut :math:`f(x)` pour certaines valeurs de
:math:`x` particulières qui sont de plus en plus grandes :

.. math:: f(10)=(10)^3= 1000

.. math:: f(100)=(100)^3= 1000000

.. math:: f(1000)=(1000)^3= 1000000000

.. math:: f(1000000)=(1000000)^3= 1000000000000000000

| Plus généralement, si nous prenons le cube de nombres positifs
  arbitrairement grands, le résultat sera un nombre positif
  arbitrairement grand. Au fur à mesure que les abscisses :math:`x` des
  points du graphes grandissent, les ordonnées :math:`f(x)` deviennent
  uniformément et définitivement aussi grandes que l’on veut. Nous
  retrouvons l’idée de divergence : la nouveauté étant que nous
  observons le comportement de la fonction non pas à l’approche d’un
  point, mais son comportement pour des nombres de plus en plus grands.
| Pour cet exemple, on dit que la fonction cubique diverge vers
  :math:`+\infty` quand :math:`x` tend vers :math:`+\infty`. On note :

  .. math:: \lim\limits_{x \to +\infty} x^3=+\infty

   
| Nous pouvons également étudier le comportement de la fonction cubique
  pour des nombres de plus en plus petits ! Commençons avec des valeurs
  particulières pour :math:`x` qui sont de plus en plus petites :

.. math:: f(-10)=(-10)^3= -1000

.. math:: f(-100)=(-100)^3= -1000000

.. math:: f(-1000)=(-1000)^3= -1000000000

.. math:: f(-1000000)=(-1000000)^3= -1000000000000000000

| Plus généralement, si nous prenons le cube de nombres négatifs
  arbitrairement petits, le résultat sera un nombre négatif
  arbitrairement petit. Au fur à mesure que les abscisses :math:`x` des
  points du graphes diminuent, les ordonnées :math:`f(x)` associées
  deviennent uniformément et définitivement aussi petites que l’on veut.
  Nous retrouvons une fois de plus l’idée de divergence : la nouveauté
  étant que nous observons le comportement de la fonction non pas à
  l’approche d’un point, mais son comportement pour des nombres de plus
  en plus petits.
| Pour cet exemple, on dit que la fonction cubique diverge vers
  :math:`-\infty` quand :math:`x` tend vers :math:`-\infty`. On note :

  .. math:: \lim\limits_{x \to -\infty} x^3=-\infty

|  
| Donnons les définitions de divergence vers :math:`+\infty` ou vers
  :math:`-\infty` d’une fonction pour :math:`x` qui tend vers
  :math:`+\infty` ou vers :math:`-\infty`. Celle-ci est très similaire à
  la définition de divergence d’une fonction en un point et est
  construite de la même manière.

|

**Définition 3.6.10.** Soit un intervalle :math:`I` non majoré. Soit :math:`f : I \to \mathbb{R}`.
  
  On dit que :math:`f` a diverge vers :math:`+\infty` pour :math:`x`
  qui tend vers :math:`+\infty` si pour toute borne supérieure
  :math:`M >0`, il existe :math:`N > 0` tel que pour tout
  :math:`x \in I` qui est plus grand ou égal à :math:`N`, c’est-à-dire
  tel que :math:`x \ge N`, on a nécessairement que :math:`f(x)` est plus
  grand ou égal à :math:`M`, c’est-à-dire qu’on a :math:`f(x) \ge M`.
  Dans ce cas, on note :

  .. math:: \lim\limits_{x \to +\infty} f(x)=+\infty

**Définition 3.6.11.** Soit un intervalle :math:`I` non majoré. Soit :math:`f : I \to \mathbb{R}`.
  
  On dit que :math:`f` a diverge vers :math:`-\infty` pour :math:`x`
  qui tend vers :math:`+\infty` si pour toute borne inférieure
  :math:`M <0`, il existe :math:`N > 0` tel que pour tout
  :math:`x \in I` qui est plus grand ou égal à :math:`N`, c’est-à-dire
  tel que :math:`x \ge N`, on a nécessairement que :math:`f(x)` est plus
  petit ou égal à :math:`M`, c’est-à-dire qu’on a :math:`f(x) \le M`.
  Dans ce cas, on note :

  .. math:: \lim\limits_{x \to +\infty} f(x)=-\infty

**Définition 3.6.12.** Soit un intervalle :math:`I` non minoré. Soit :math:`f : I \to \mathbb{R}`.
  
  On dit que :math:`f` a diverge vers :math:`+\infty` pour :math:`x`
  qui tend vers :math:`-\infty` si pour toute borne supérieure
  :math:`M >0`, il existe :math:`N < 0` tel que pour tout
  :math:`x \in I` qui est plus petit ou égal à :math:`N`, c’est-à-dire
  tel que :math:`x \le N`, on a nécessairement que :math:`f(x)` est plus
  grand ou égal à :math:`M`, c’est-à-dire qu’on a :math:`f(x) \ge M`.
  Dans ce cas, on note :

  .. math:: \lim\limits_{x \to -\infty} f(x)=+\infty

**Définition 3.6.13.** Soit un intervalle :math:`I` non majoré. Soit :math:`f : I \to \mathbb{R}`.
  
  On dit que :math:`f` a diverge vers :math:`-\infty` pour :math:`x`
  qui tend vers :math:`-\infty` si pour toute borne inférieure
  :math:`M <0`, il existe :math:`N < 0` tel que pour tout
  :math:`x \in I` qui est plus grand ou égal à :math:`N`, c’est-à-dire
  tel que :math:`x \le N`, on a nécessairement que :math:`f(x)` est plus
  petit ou égal à :math:`M`, c’est-à-dire qu’on a :math:`f(x) \le M`.
  Dans ce cas, on note :

  .. math:: \lim\limits_{x \to +\infty} f(x)=-\infty

|

Donnons quelques exemples et contre-exemples.

**Exemple 3.6.14.** La fonction valeur absolue diverge vers :math:`+\infty` pour :math:`x`
qui tend vers :math:`+\infty` et diverge ves :math:`+\infty` pour
:math:`x` qui tend vers :math:`-\infty`.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:5](\x,{abs(\x)});
			

.. math:: \lim\limits_{x \to +\infty} |x|=+\infty

.. math:: \lim\limits_{x \to +\infty} |x|=+\infty

**Exemple 3.6.15.** La fonction racine carrée diverge vers :math:`+\infty` pour :math:`x`
qui tend vers :math:`+\infty`. Il ne fait pas sens de parler d’une
limite ou de divergence pour :math:`x` qui tend vers :math:`-\infty`
pour la racine carrée puisqu’elle n’est pas définie sur l’ensemble des
réels strictement négatifs.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=0:5](\x,{sqrt(\x)});
			

.. math:: \lim\limits_{x \to +\infty} x=+\infty

**Exemple 3.6.16.** La fonction dont le graphe est donné ci-dessous diverge vers
:math:`-\infty` pour :math:`x` qui tend vers :math:`+\infty` et diverge
vers :math:`+\infty` pour :math:`x` qui tend vers :math:`-\infty`.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-3:0](\x,{-3+1/2^\x});
		\draw (0,-2)node{$\bullet$};
		\draw (1,2.5)node{$\bullet$};
    \draw[thick] plot[samples=150,domain=1:4](\x,{3-(1/2)*\x*\x});
			

.. math:: \lim\limits_{x \to +\infty} f(x)=-\infty

.. math:: \lim\limits_{x \to -\infty} f(x)=+\infty

|

**Contre-exemple 3.6.17.** La fonction dont le graphe est donné ci-dessous ne diverge pas pour
:math:`x` qui tend vers :math:`+\infty` et ne diverge pas pour :math:`x`
qui tend vers :math:`-\infty`.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[samples=300,domain=-5:5](\x,{sin(3*180*\x)});
			

**Contre-exemple 3.6.18.** La fonction dont le graphe est donné ci-dessous diverge vers
:math:`-\infty` pour :math:`x` qui tend vers :math:`+\infty` mais ne
diverge pas pour :math:`x` qui tend vers :math:`-\infty`.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:4](\x,{-1-(1/4)*2^\x});
			

.. math:: \lim\limits_{x \to +\infty} f(x)=-\infty

**Remarque 3.6.19.** Il existe une quantité non négligeable de résultats intéressants portant
sur les limites et les divergences de fonctions pour :math:`x` qui tend
vers :math:`+\infty` ou vers :math:`-\infty`. Néanmoins, dans ce cours,
nous nous contenterons d’utiliser ces notions comme des outils qui
permettent de décrire le comportement asymptotique d’une fonction.  

|

Passons aux exercices.

**Exercice 3.6.20.** (Exercice théorique un peu difficile.)

Les définitions 3.6.3 et 3.6.4
sont très similaires. Identifier la seule petite différence et
expliquer celle-ci.

|

**Exercice 3.6.21.** Tracer le graphe d’une fonction :math:`f` ayant les propriétés suivantes
:

.. hlist::
   :columns: 2

   * dom :math:`f=\mathbb{R}`

   * :math:`f` est continue partout sauf en :math:`-3` et :math:`2`.

   * :math:`\lim\limits_{x \underset{<}{\to} -3} f(x)` existe et est égale à
   :math:`1`.

   * :math:`\lim\limits_{x \underset{>}{\to} -3} f(x)` existe et est égale à
   :math:`2`.

   * :math:`\lim\limits_{x \underset{>}{\to} 2} f(x)` existe et est égale à
   :math:`-2`.

   * :math:`f(2)=2`

   * :math:`\lim\limits_{x \to -\infty}f(x)=-\infty`

   * :math:`\lim\limits_{x \to +\infty}f(x)=-\infty`

**Solution.**

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-3](\x,{\x+4});
    \draw (-3,1)node{$\bullet$};
    \draw[thick, fill=white](-3,2)circle(0.15);
    \draw[thick] plot[domain=-2.95:2](\x,{2});
    \draw (2,2)node{$\bullet$};
    \draw[thick, fill=white](2,-2)circle(0.15);
    \draw[thick] plot[domain=2.08:5](\x,{-1-(1/2)*\x});

|		

**Exercice 3.6.22.** Déterminer si les fonctions dont les graphes sont donnés ci-dessous
ont une limite ou divergent pour :math:`x` qui tend vers
:math:`+\infty` ou :math:`-\infty`.

.. inginious:: limite6_1
.. inginious:: limite6_2
.. inginious:: limite6_3
.. inginious:: limite6_4
.. inginious:: limite6_5
.. inginious:: limite6_6
.. inginious:: limite6_7
.. inginious:: limite6_8


|

**Exercice 3.6.23.** Déterminer si les fonctions convergent ou divergent pour :math:`x` qui
tend vers :math:`+\infty` ou pour :math:`x` qui tend vers
:math:`\infty`. Si elles convergent, donner la limite. Si elles
divergent, donner le type de divergence (vers :math:`+\infty` ou vers
:math:`-\infty`). N’hésitez pas à vous aider d’un graphe.

.. inginious:: limite7_1
.. inginious:: limite7_2
.. inginious:: limite7_3
.. inginious:: limite7_4
.. inginious:: limite7_5
.. inginious:: limite7_6

|

**Exercice 3.6.24.** Un homme souhaite changer la teneur en sel de son aquarium pour y
accueillir de nouveaux poissons. Alors que son aquarium contient
initialement 3 litres d’eau douce, il commence à remplir l’aquarium avec
à la fois de l’eau douce et de l’eau salée (avec deux pompes
différentes). La pompe d’eau douce a un débit d’un centilitre par
seconde, tandis que la pompe d’eau salée a un débit de deux centilitres
par seconde.

#. Quel est le rapport de la quantité d’eau douce et de la quantité
   d’eau salée après une minute de remplissage ?

#. Quel est le rapport de la quantité d’eau douce et de la quantité
   d’eau salée après :math:`r` secondes de remplissage ? (:math:`t`
   étant un nombre réel strictement positif quelconque.)

#. Au fur et à mesure que le temps passe, de quoi se rapproche le
   rapport de la quantité d’eau douce et de la quantité d’eau salée ?

.. inginious:: limite8_1

|

**Exercice 3.6.25.** Un avion a une panne de moteur en plein vol à une altitude de
:math:`10`\ km et menace de s’écraser. Le pilote va essayer de faire
planer l’avion jusqu’au prochain aréoport, mais il craint que l’avion
perde trop d’altitude en planant.

Il se souvient de ses cours d’aviation que dans ce genre de situation,
l’avion perd d’abord rapidement beaucoup d’altitude mais se stabilise
peu à peu. Il se souvient que dans ce genre de situation, l’altitude
de l’avion après :math:`t` heures est de :math:`A*\frac{t}{2(t+1)}` où
:math:`A` est l’altitude initiale de l’avion.

De quelle altitude se rapproche de l’avion au fur et à mesure que le
temps passe ? Risque-t-il de s’écraser ?

.. inginious:: limite8_2

|

3.7 Asymptotes
--------------

| Il existe une autre manière d’interpréter et de visualiser certaines
  limites. Ce point de vue plus géométrique des limites que sont les
  asymptotes plaît énormément à certains mais n’apporte rien de
  fondamental à l’idée de limite. Passons rapidement en revue les deux
  types les plus simples d’asymptotes : les asymptotes horizontales et
  les asymptotes verticales.
| Une fois de plus, commençons avec un exemple.

**Exemple 3.7.1.** Voici ci-dessous le graphe de la fonction :

.. math::

   \begin{aligned}
       f : \mathbb{R}\backslash\{1\} &\to \mathbb{R}\\
       x &\mapsto 2+\frac{1}{x-1}
       \end{aligned}

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:0.8571](\x,{2+1/(\x -1)});
    \draw[thick] plot[domain=1.3334:5](\x,{2+1/(\x -1)});
			

Les limites et les divergences intéressantes pour cette fonction sont :

.. math:: \lim\limits_{x \to +\infty} 2+\frac{1}{x-1}=2

.. math:: \lim\limits_{x \to -\infty} 2+\frac{1}{x-1}=2

.. math:: \lim\limits_{x \underset{>}{\to} 1} 2+\frac{1}{x-1}=+\infty

.. math:: \lim\limits_{x \underset{<}{\to} 1} 2+\frac{1}{x-1}=-\infty

Rappelons-nous ce que signifie en français la première de ces quatre
affirmations : au fur et à mesure que :math:`x` devient grand, les
nombres :math:`2+\frac{1}{x-1}` associées se rapprochent uniformément et
définitivement de :math:`2`. Une autre façon d’exprimer cela, plus
géométrique, est de dire que plus on considère des points du graphe de
la fonction :math:`f` dont les abscisses sont grandes, plus le graphe de
:math:`f` se rapproche uniformément et définitivement de la droite
d’équation :math:`y=2` :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:0.8571](\x,{2+1/(\x -1)});
    \draw[thick] plot[domain=1.3334:5](\x,{2+1/(\x -1)});
    \draw[blue,thick,dotted] plot[domain=-5:5](\x,{2)});
			

| Cette droite est ce qu’on appelle une asymptote (horizontale) de la
  fonction :math:`f`. Son sens est exactement celui encodé par la limite
  :math:`\lim\limits_{x \to +\infty} 2+\frac{1}{x-1}=2`.
| Remarquons que la limite
  :math:`\lim\limits_{x \to -\infty} 2+\frac{1}{x-1}=2` peut également
  être interprétée géométriquement avec une asymptote horizontale : plus
  on considère des points du graphe de la fonction :math:`f` dont les
  abscisses sont petites, plus le graphe de :math:`f` se rapproche
  uniformément et définitivement de la droite d’équation :math:`y=2`
  également.
|  
| Par contre, si on souhaite interpréter les deux affirmations
  :math:`\lim\limits_{x \underset{>}{\to} 1} 2+\frac{1}{x-1}=+\infty` et
  :math:`\lim\limits_{x \underset{<}{\to} 1} 2+\frac{1}{x-1}=-\infty` de
  façon plus géométrique, il faut recourir à la notion d’asymptote
  verticale. Pour cet exemple, on dira que la focntion a une asymptote
  verticale d’équation cartésienne :math:`x=1` :

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:0.8571](\x,{2+1/(\x -1)});
    \draw[thick] plot[domain=1.3334:5](\x,{2+1/(\x -1)});
    \draw[blue,thick,dotted](1,-5)--(1,5);
			

Plus on on considère des points du graphe de :math:`f` dont les
abscisses sont proches de :math:`1`, plus le graphe de :math:`f` se
rapproche uniformément et définitivement de cette droite. Le sens de
cette asymptote verticale est exactement celui des deux divergences
:math:`\lim\limits_{x \underset{>}{\to} 1} 2+\frac{1}{x-1}=+\infty` et
:math:`\lim\limits_{x \underset{<}{\to} 1} 2+\frac{1}{x-1}=-\infty`.

Les asymptotes horizontales sont donc juste une manière plus géométrique
d’exprimer des limites pour :math:`x` qui tend vers :math:`+\infty` ou
:math:`-\infty` de fonctions et les asymptotes verticales sont juste une
manière plus géométrique d’exprimer des divergences en un point de
fonctions. Donnons les définitions précises de ces deux nouvelles
notions.

|

**Définition 3.7.2.** Soit un intervalle :math:`I` non majoré. Soit :math:`f : I \to \mathbb{R}`.
  
  Si :math:`\lim\limits_{x \to +\infty} f(x)=L`, on dit que :math:`f` a
  une *asymptote horizontale (à droite)* d’équation cartésienne
  :math:`y=L` et on note :

  .. math:: {\mbox{AH}}_{d} \equiv y=L

**Définition 3.7.3.** Soit un intervalle :math:`I` non minoré. Soit :math:`f : I \to \mathbb{R}`.
 
  Si :math:`\lim\limits_{x \to +\infty} f(x)=L`, on dit que :math:`f` a
  une *asymptote horizontale (à gauche)* d’équation cartésienne
  :math:`y=L` et on note :

  .. math:: {\mbox{AH}}_{g} \equiv y=L

**Définition 3.7.4.** Soit un intervalle :math:`I` éventuellement privé d’un point :math:`c`. Soit :math:`f : I \to \mathbb{R}`.
 
  Si :math:`\lim\limits_{x \underset{>}{\to} c} f(x)=+\infty` ou
  :math:`\lim\limits_{x \underset{>}{\to} c} f(x)=-\infty`, on dit que
  :math:`f` a une *asymptote verticale (à droite)* d’équation
  cartésienne :math:`x=c` et on note :

  .. math:: {\mbox{AV}}_{d} \equiv x=c

**Définition 3.7.5.** Soit un intervalle :math:`I` éventuellement privé d’un point :math:`c`. Soit :math:`f : I \to \mathbb{R}`.
 
  Si :math:`\lim\limits_{x \underset{<}{\to} c} f(x)=+\infty` ou
  :math:`\lim\limits_{x \underset{<}{\to} c} f(x)=-\infty`, on dit que
  :math:`f` a une *asymptote verticale (à gauche)* d’équation
  cartésienne :math:`x=c` et on note :

  .. math:: {\mbox{AV}}_{g} \equiv x=c

|

**Remarque 3.7.6.** Il existe encore au moins un autre type d’asymptote : les asymptotes
obliques. Nous n’en parlerons pas dans ce cours.

Puisque les asymptotes ne sont qu’une réinterprétation géométrique de
certaines limites, il n’y a pas grand chose d’autre à dire à leur sujet.
Passons donc immédiatement aux exercices.

|

**Exercice 3.7.7.** Pour les fonctions dont les graphes sont donnés ci-dessous, lister
toutes les asymptotes horizontales et verticales et donner leurs
équations cartésiennes.

.. inginious:: asymp1_1
.. inginious:: asymp1_2
.. inginious:: asymp1_3
.. inginious:: asymp1_4


|

**Exercice 3.7.8.** Donner le graphe d’une fonction qui possède deux asymptotes horizontales
(différentes), deux asymptotes verticales dont une des deux a pour
équation cartésienne :math:`x=-2`. Donner les équations cartésiennes de
toutes les asympotes horizontales et verticales de la fonction choisie.

**Solution.**

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[domain=-5:-2.4472](\x,{1/((\x+2)*(\x+2))});
    \draw[thick] plot[domain=-1.5528:-1](\x,{1/((\x+2)*(\x+2))});
    \draw[thick] plot[domain=-1:2](\x,{1});
    \draw[thick] plot[domain=2:2.8571](\x,{2+1/(\x -3)});
    \draw[thick] plot[domain=3.3334:5](\x,{2+1/(\x -3)});
			

.. math:: {\mbox{AH}}_{d} \equiv y=2

.. math:: {\mbox{AH}}_{h} \equiv y=0

.. math:: \mbox{AV} \equiv x=-2

.. math:: \mbox{AV} \equiv x=3

|

**Exercice 3.7.9.** Pour les fonctions suivantes, déterminer les équations cartésiennes de
toutes les asymptotes horizontales et verticales.

.. inginious:: asymp2_1
.. inginious:: asymp2_2
.. inginious:: asymp2_3
.. inginious:: asymp2_4
.. inginious:: asymp2_5
.. inginious:: asymp2_6

|

3.8 Propriétés des limites de fonctions
---------------------------------------

| Dans cette dernière section de ce long chapitre sur les limites, nous
  allons apprendre à calculer des limites de fonctions de façon
  efficace, sans avoir recours à des graphes ou des tableaux de nombres.
  Pour ce faire, nous allons réfléchir à la façon dont se combinent les
  limites. Nous allons voir que pour calculer une limite, une stratégie
  extrêmement puissante est de décomposer la fonction dont on veut
  calculer la limite en terme de fonctions plus simples pour lesquelles
  le calcul des limites est immédiat.
| Comme pour chacune des cinq dernières sections de ce chapitre,
  commençons avec un exemple.

|

**Exemple 3.8.1.** À ce stade, nous savons déjà que la fonction inverse converge
vers :math:`0` pour :math:`x` qui tend vers :math:`+\infty` :

.. math:: \lim\limits_{x \to +\infty} \frac{1}{x}=0

De même, nous savons que la fonction constante de constante :math:`2`
converge vers :math:`2` :

.. math:: \lim\limits_{x \to +\infty} 2=2

Question : à partir de ces deux informations, pouvons-nous affirmer
quelque chose au sujet du comportement asymptotique (pour :math:`x` qui
tend vers :math:`+\infty`) de la fonction obtenue en additionnant ces
deux premières fonctions :

.. math::

   \begin{aligned}
   f : \mathbb{R}\backslash \{0\} \to \mathbb{R}\\
   x \mapsto \frac{1}{x}+2\end{aligned}

Bien entendu, calculer directement la limite pour :math:`x` qui tend
vers :math:`+\infty` de cette fonction :math:`f` n’est pas difficile :

.. math:: \lim\limits_{x \to +\infty} \frac{1}{x}+2=2

Mais aurions-nous pu trouver ce résultat sans même réfléchir au
comportement asymptotique de la fonction :math:`f` ? Pour répondre à
cette question, rappelons ce que signifient les deux affirmations :

.. math:: \lim\limits_{x \to +\infty} \frac{1}{x}=0

.. math:: \lim\limits_{x \to +\infty} 2=2

La première signifie que pour des nombres :math:`x` de plus en plus
grands, les nombres :math:`\frac{1}{x}` se rapprochent uniformément et
définitivement de :math:`0`. La deuxième signifie que pour des nombres
:math:`x` de plus en plus grands, les nombres :math:`2` se rapprochent
uniformément et définitivement de :math:`2`. On déduit directement de
ces deux informations que pour des nombres :math:`x` de plus en plus
grands, les nombres :math:`\frac{1}{x}+2` se rapprochent uniformément et
définitivement de :math:`0+2`. Autrement dit :

.. math:: \lim\limits_{x \to +\infty} \frac{1}{x}+2=\lim\limits_{x \to +\infty} \frac{1}{x} + \lim\limits_{x \to +\infty} 2 = 0+2=2

La limite pour :math:`x` qui tend vers :math:`+\infty` de la fonction
:math:`f` qui est définie comme la somme de la fonction inverse et de la
fonction constante de constante :math:`2` est égale à la somme des
limites pour :math:`x` qui tend vers :math:`+\infty` de ces deux
fonctions. On a pu décomposer le calcul de la limite pour :math:`x` qui
tend vers :math:`+\infty` de la fonction :math:`f` en une somme de
limites plus simples à calculer.

|

| L’idée que nous avons mise en œuvre dans l’exemple
  3.8.1, c’est-à-dire calculer la limite d’une fonction
  en décomposant celle-ci, est extrêmement utile et générale et permet
  de calculer des limites efficacement sans avoir à construire sans
  cesse des tableaux de signes ou des graphes de fonctions. Cette idée
  se base sur les propriétés des limites que nous allons lister dans
  cette section qui explicitent la manière dont se combinent les limites
  (et les divergences).
| Il est **très important** de faire l’effort de comprendre cette idée
  pour être à même de l’appliquer. Je vous déconseille **vivement**
  d’apprendre par cœur toutes les propositions que nous allons donner
  dans cette section. Appliquer ces dernières mécaniquement sera non
  seulement pénible mais surtout difficile et peu enrichissant.
| Pour cette raison, nous allons essayer d’expliquer le plus en détail
  la toute première. Cette première proposition de cette section
  s’intéresse à ce qu’il se passe lorsqu’on additionne deux fonctions
  qui chacune ont une limite en un point :math:`c \in \mathbb{R}`.

|

**Proposition 3.8.2.** Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c`.
  
  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  telles que :math:`\lim\limits_{x \to c} f(x) = L_1` et
  :math:`\lim\limits_{x \to c} g(x) = L_2`.
  Alors la fonction :math:`(f+g) : I \to \mathbb{R}` a une limite en
  :math:`c` et on a :

  .. math:: \lim\limits_{x \to c} (f+g)(x) = L_1 + L_2

| Nous ne démontrerons malheureusement pas cette proposition et il en
  sera de même pour toutes les autres propositions de cette section.
  Néanmoins, essayons de la comprendre : elle exprime en fait un
  résultat assez intuitif.
| Pour partir d’une situation concrète : supposons que je suis dans un
  train et que je me rapproche peu à peu de l’arrière du train de sorte
  que j’arrive au bout à 9h00 précise. Supposons également que le train
  lui-même se rapproche de la gare de Louvain-la-Neuve de sorte qu’il
  arrivera à destination à 9h00 précise. Pour un observateur sur le
  quai, au fur et à mesure que l’aiguille de l’horloge se rapproche de
  9h00 pile, de quelle position me rapprocherai-je ? Puisque je me
  rapproche du bout arrière du train et que le train se rapproche du
  quai de la gare, je me rapproche de la position de laquelle se
  rapproche le bout arrière du train pour un observateur sur le quai.
  Les deux mouvements s’additionnent et il en va donc de même pour les
  positions dont ces deux mouvements se rapprochent.
| La proposition ci-dessus porte sur la même idée mais de manière
  abstraitre. Essayons de comprendre sa généralité avec un exemple
  formel. Supposons que je possède deux fonctions
  :math:`f : \mathbb{R}\backslash \{1\} \to \mathbb{R}` et
  :math:`g : \mathbb{R}\backslash \{1\} \to \mathbb{R}` dont les graphes
  sont les suivants :

.. hlist::
   :columns: 2

   * .. tikz:: 

         \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

         \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
         \draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

         \foreach \x in {1}
         \draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

         \foreach \y in {1}
         \draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
      \draw[thick] plot[domain=-5:0.95](\x,{\x});
      \draw[thick] plot[domain=1.05:5](\x,{\x});
      \draw[thick, fill=white](1,1)circle(0.125);
            

   * .. tikz:: 

         \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

         \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
         \draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

         \foreach \x in {1}
         \draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

         \foreach \y in {1}
         \draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
      \draw[thick] plot[samples=50,domain=-5:0.95](\x,{2+cos(90*\x)*(1/1.2)*(1.2)^\x});
      \draw[thick] plot[samples=50,domain=1.05:5](\x,{2+cos(90*\x)*(1/1.2)*(1.2)^\x});
      \draw[thick, fill=white](1,2)circle(0.125);
      \draw[thick] plot[domain=-5:0.95](\x,{\x});
      \draw[thick] plot[domain=1.05:5](\x,{\x});
      \draw[thick, fill=white](1,1)circle(0.125);
			

Ces deux fonctions ont toutes les deux une limite en :math:`1` :

.. math:: \lim\limits_{x \to 1} f(x) = 1

.. math:: \lim\limits_{x \to 1} g(x) = 2

|

Que se passe-t-il si nous nous créons une nouvelle fonction en
additionnant :math:`f` et :math:`g` :
:math:`h : \mathbb{R}\backslash \{1\} \to \mathbb{R}`.

.. tikz:: 

      \draw[step=1cm,gray,very thin] (-5,-5) grid (5,5);

      \draw[very thick,->] (-5,0) -- (6,0) node[anchor=south west] {x};
		\draw[very thick,->] (0,-5) -- (0,6) node[anchor=south west] {y};

      \foreach \x in {1}
		\draw (\x cm,1pt) -- (\x cm,-1pt) node[anchor=north] {$\x$};

      \foreach \y in {1}
		\draw (1pt,\y cm) -- (-1pt,\y cm) node[anchor=east] {$\y$};
    \draw[thick] plot[samples=50,domain=-5:0.95](\x,{\x+2+cos(90*\x)*(1/1.2)*(1.2)^\x});
    \draw[thick] plot[samples=50,domain=1.05:3](\x,{\x+2+cos(90*\x)*(1/1.2)*(1.2)^\x});
    \draw[thick, fill=white](1,3)circle(0.175);

|		

| La fonction :math:`h` a également une limite en :math:`1` et cette
  limite est la somme des limites en :math:`1` des fonctions :math:`f`
  et :math:`g` : :math:`1+2=3`.
| Logique : puisque la fonction :math:`f` se rapproche uniformément et
  définitivement de :math:`1` à l’approche de :math:`1` et que la
  fonction :math:`g` se rapproche uniformément et définitivement de
  :math:`2` à l’approche de :math:`1`, la fonction :math:`h` qui est la
  somme de ces deux fonctions se rapproche uniformément et
  définitivement de :math:`1+2=3` à l’approche de :math:`1`. Cette
  remarque n’est évidemment pas propre à notre exemple : il en aurait
  été de même pour d’autres fonctions :math:`f` et :math:`g`. C’est ce
  qui est exactement exprimé par la proposition
  3.8.2.
|  
| La proposition 3.8.2 permet de calculer des
  limites de façon efficace en décomposant la fonction dont on veut
  calculer la limite en fonctions plus simples dont elle est la somme.
  Donnons immédiatement un exemple d’application de cette proposition.

|

**Exemple 3.8.3.** Supposons que l’on souhaite déterminer si la fonction suivante possède
une limite en :math:`-1`.

.. math::

   \begin{aligned}
   f : {\mathbb{R}}_{0} \to \mathbb{R}\\
   x \mapsto \sqrt[3]{x}+\frac{x+1}{x}\end{aligned}

On remarque que la fonction :math:`f` est la somme des trois fonctions :

.. math::

   \begin{aligned}
   g : \mathbb{R}\to \mathbb{R}\\
   x \mapsto \sqrt[3]{x}\end{aligned}

.. math::

   \begin{aligned}
   h : \mathbb{R}\to \mathbb{R}\\
   x \mapsto 1\end{aligned}

.. math::

   \begin{aligned}
   h : \mathbb{R}\to \mathbb{R}\\
   x \mapsto \frac{1}{x}\end{aligned}

De plus, on sait facilement calculer les limites en :math:`-1` de ces
trois fonctions :

.. math:: \lim\limits_{x \to -1} g(x) = -1

.. math:: \lim\limits_{x \to -1} h(x) = 1

.. math:: \lim\limits_{x \to -1} l(x) = -1

Par la proposition 3.8.2, :math:`f` a donc
nécessairement une limite en :math:`-1` et cette limite est égale à :

.. math:: \lim\limits_{x \to -1} f(x) = \lim\limits_{x \to -1} g(x)+\lim\limits_{x \to -1} h(x)+\lim\limits_{x \to -1} l(x)=-1

La proposition 3.8.2 décrit ce qu’il se passe
lorsqu’on additionne deux fonctions qui possèdent une limite en un
point. Il existe bien évidemment d’autres opérations sur les fonctions
et d’autres possibilités pour une fonction que d’avoir une limite en un
point (elle peut par exemple diverger). Dans les pages suivantes, nous
allons donner toutes les variantes possibles de la proposition
3.8.2. Insistons sur un point : **n’apprennez pas
toutes ces propositions par cœur !** Comprenez-les de sorte que vous
puissiez les retrouver par vous-mêmes.

|

**Proposition 3.8.4.** Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c`.

  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  telles que :math:`\lim\limits_{x \to c} f(x) = L_1` et
  :math:`\lim\limits_{x \to c} g(x) = L_2`.
  Alors la fonction :math:`(f-g) : I \to \mathbb{R}` a une limite en
  :math:`c` et on a :

  .. math:: \lim\limits_{x \to c} (f-g)(x) = L_1 - L_2

**Proposition 3.8.5.** Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c`.
 
  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  telles que :math:`\lim\limits_{x \to c} f(x) = L_1` et
  :math:`\lim\limits_{x \to c} g(x) = L_2`.
  Alors la fonction :math:`(f.g) : I \to \mathbb{R}` a une limite en
  :math:`c` et on a :

  .. math:: \lim\limits_{x \to c} (f.g)(x) = L_1 . L_2

**Proposition 3.8.6.** Soit :math:`I` un intervalle éventuellement privé d’un point
  :math:`c`.
  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  avec :math:`g(x) \neq 0` pour tout :math:`x \in I` telles que
  :math:`\lim\limits_{x \to c} f(x) = L_1` et
  :math:`\lim\limits_{x \to c} g(x) = L_2` avec :math:`L_2 \neq 0`.
  Alors la fonction :math:`\frac{f}{g} : I \to \mathbb{R}` a une limite
  en :math:`c` et on a :

  .. math:: \lim\limits_{x \to c} (\frac{f}{g})(x) = \frac{L_1}{L_2}

|

**Proposition 3.8.7.** Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c` et soit :math:`J` un intervalle éventuellement privé d’un point :math:`d`.

  Soient :math:`f : I \to \mathbb{R}` et :math:`g : J \to \mathbb{R}`
  telles que :math:`g(J) \subseteq I`,
  :math:`\lim\limits_{x \to c} f(x) = L` et
  :math:`\lim\limits_{x \to d} g(x) = c`.
  Alors la fonction :math:`(f \circ g) : J \to \mathbb{R}` a une limite
  en :math:`d` et on a :

  .. math:: \lim\limits_{x \to d} (f \circ g)(x) = L

Passons aux cas où la fonction :math:`g` diverge vers :math:`+\infty`.

**Proposition 3.8.8.**  Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c`.
 
  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  telles que :math:`\lim\limits_{x \to c} f(x) = L_1` et
  :math:`\lim\limits_{x \to c} g(x) = +\infty`.
  Alors la fonction :math:`(f+g) : I \to \mathbb{R}` diverge en
  :math:`c` et on a :

  .. math:: \lim\limits_{x \to c} (f+g)(x) = +\infty

**Proposition 3.8.9.** Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c`.
 
  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  telles que :math:`\lim\limits_{x \to c} f(x) = L_1` et
  :math:`\lim\limits_{x \to c} g(x) = +\infty`.
  Alors la fonction :math:`(f-g) : I \to \mathbb{R}` diverge en
  :math:`c` et on a :

  .. math:: \lim\limits_{x \to c} (f-g)(x) = -\infty

|

**Proposition 3.8.10.** Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c`.
 
  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  telles que :math:`\lim\limits_{x \to c} f(x) = L_1` avec
  :math:`L_1 \neq 0` et :math:`\lim\limits_{x \to c} g(x) = +\infty`.
  Alors la fonction :math:`(f.g) : I \to \mathbb{R}` diverge en
  :math:`c` et on a :

-  Si :math:`L_1 >0` :

   .. math:: \lim\limits_{x \to c} (f.g)(x) = \infty

-  Si :math:`L_1 <0` :

   .. math:: \lim\limits_{x \to c} (f.g)(x) = -\infty

**Proposition 3.8.11.** Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c`.
  
  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  avec :math:`g(x) \neq 0` pour tout :math:`x \in I` telles que
  :math:`\lim\limits_{x \to c} f(x) = L_1` et
  :math:`\lim\limits_{x \to c} g(x) = +\infty`.
  Alors la fonction :math:`\frac{f}{g} : I \to \mathbb{R}` a une limite
  en :math:`c` et on a :

  .. math:: \lim\limits_{x \to c} (\frac{f}{g})(x) = 0

**Proposition 3.8.12.** Soit :math:`I` un intervalle non majoré et soit :math:`J` un intervalle éventuellement privé d’un point :math:`d`.

  Soient :math:`f : I \to \mathbb{R}` et :math:`g : J \to \mathbb{R}`
  telles que :math:`g(J) \subseteq I`,
  :math:`\lim\limits_{x \to +\infty} f(x) = L` et
  :math:`\lim\limits_{x \to d} g(x) = +\infty`.
  Alors la fonction :math:`(f \circ g) : J \to \mathbb{R}` a une limite
  en :math:`d` et on a :

  .. math:: \lim\limits_{x \to d} (f \circ g)(x) = L

|

Les cas où la fonction :math:`g` diverge vers :math:`-\infty` sont très
similaires aux cinq précédents et nous ne les listerons pas ici. Passons
aux cas où la fonction :math:`f` diverge vers :math:`+\infty` mais où la
fonction :math:`g` converge.

**Proposition 3.8.13.** Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c`.

  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  telles que :math:`\lim\limits_{x \to c} f(x) = +\infty` et
  :math:`\lim\limits_{x \to c} g(x) = L_2`.
  Alors la fonction :math:`(f+g) : I \to \mathbb{R}` diverge en
  :math:`c` et on a :

  .. math:: \lim\limits_{x \to c} (f+g)(x) = +\infty

**Proposition 3.8.14.** Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c`.
 
  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  telles que :math:`\lim\limits_{x \to c} f(x) = +\infty` et
  :math:`\lim\limits_{x \to c} g(x) = L_2`.
  Alors la fonction :math:`(f-g) : I \to \mathbb{R}` diverge en
  :math:`c` et on a :

  .. math:: \lim\limits_{x \to c} (f-g)(x) = +\infty

**Proposition 3.8.15.** Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c`.
 
  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  telles que :math:`\lim\limits_{x \to c} f(x) = +\infty` avec
  :math:`L_1 \neq 0` et :math:`\lim\limits_{x \to c} g(x) = L_2`.
  Alors la fonction :math:`(f.g) : I \to \mathbb{R}` diverge en
  :math:`c` et on a :

-  Si :math:`L_2 >0` :

   .. math:: \lim\limits_{x \to c} (f.g)(x) = \infty

-  Si :math:`L_2 <0` :

   .. math:: \lim\limits_{x \to c} (f.g)(x) = -\infty

|

**Proposition 3.8.16.** Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c`.
 
  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  avec :math:`g(x) \neq 0` pour tout :math:`x \in I` telles que
  :math:`\lim\limits_{x \to c} f(x) = +\infty` et
  :math:`\lim\limits_{x \to c} g(x) = L_2`.
  Alors la fonction :math:`\frac{f}{g} : I \to \mathbb{R}` diverge en
  :math:`c` et on a :

-  Si :math:`L_2 >0` :

   .. math:: \lim\limits_{x \to c} (\frac{f}{g})(x) = +\infty

-  Si :math:`L_2 <0` :

   .. math:: \lim\limits_{x \to c} (\frac{f}{g})(x) = -\infty

**Proposition 3.8.17.** Soit :math:`I` un intervalle éventuellement privé d’un point :math:`c`
et soit :math:`J` un intervalle éventuellement privé d’un point
:math:`d`.

  Soient :math:`f : I \to \mathbb{R}` et :math:`g : J \to \mathbb{R}`
  telles que :math:`g(J) \subseteq I`,
  :math:`\lim\limits_{x \to +\infty} f(x) = +\infty` et
  :math:`\lim\limits_{x \to d} g(x) = c`.
  Alors la fonction :math:`(f \circ g) : J \to \mathbb{R}` diverge en
  :math:`d` et on a :

  .. math:: \lim\limits_{x \to d} (f \circ g)(x) = +\infty

À nouveau, les cas où la fonction :math:`f` diverge vers :math:`-\infty`
sont très similaires aux cinq précédents et nous ne les listerons pas
ici. Passons aux cas où la fonction :math:`f` diverge vers
:math:`+\infty` et où la fonction :math:`g` diverge vers
:math:`+\infty`.

**Proposition 3.8.18.** Soit :math:`I` un intervalle éventuellement privé d’un point
:math:`c`.
 
  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  telles que :math:`\lim\limits_{x \to c} f(x) = +\infty` et
  :math:`\lim\limits_{x \to c} g(x) = +\infty`.
  Alors la fonction :math:`(f+g) : I \to \mathbb{R}` diverge en
  :math:`c` et on a :

  .. math:: \lim\limits_{x \to c} (f+g)(x) = +\infty

|

**Proposition 3.8.19.**  Soit :math:`I` un intervalle éventuellement privé d’un point
:math:`c`.

  Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  telles que :math:`\lim\limits_{x \to c} f(x) = +\infty` avec
  :math:`L_1 \neq 0` et :math:`\lim\limits_{x \to c} g(x) = +\infty`.
  Alors la fonction :math:`(f.g) : I \to \mathbb{R}` diverge en
  :math:`c` et on a :

  .. math:: \lim\limits_{x \to c} (f.g)(x) = \infty

**Proposition 3.8.20.** Soit :math:`I` un intervalle non majoré et soit :math:`J` un
intervalle éventuellement privé d’un point :math:`d`.
 
  Soient :math:`f : I \to \mathbb{R}` et :math:`g : J \to \mathbb{R}`
  telles que :math:`g(J) \subseteq I`,
  :math:`\lim\limits_{x \to +\infty} f(x) = +\infty` et
  :math:`\lim\limits_{x \to d} g(x) = +\infty`.
  Alors la fonction :math:`(f \circ g) : J \to \mathbb{R}` diverge en
  :math:`d` et on a :

  .. math:: \lim\limits_{x \to d} (f \circ g)(x) = +\infty

Les cas où la fonction :math:`f` ou la fonction :math:`g` diverge vers
:math:`-\infty` plutôt que vers :math:`+\infty` sont très similaires aux
cinq derniers et nous ne les listerons pas ici. Tous les cas où on ne
considère pas une limite ou une divergence en un point mais pour
:math:`x` qui tend vers :math:`+\infty` ou vers :math:`-\infty` sont
semblables à ceux que nous avons déjà listés, nous ne les listerons donc
pas ici.

|

**Remarque 3.8.21.** Il peut sembler que certaines propositions sont manquantes. Par
exemples, *quid* de la différence de deux fonctions qui divergent vers
:math:`+\infty` en un point :math:`c` ?
Une personne peu rigoureuse pourrait écrire que :

.. math:: \lim\limits_{x \to c} (f - g)(x) = \lim\limits_{x \to c} f(x) - \lim\limits_{x \to d} g(x)=\infty-\infty=0

Outre le fait que cela n’a aucun sens, cela est absolument faux ! Je
vous **interdis** de noter de telles horreurs dans le cadre de ce
cours.

Ce type de situation est appelé par certaines personnes
indétermination . Une indétermination est en fait une situation où on
ne peut pas simplement appliquer une des propositions listées
ci-dessus pour décomposer une limite ou une divergence que l’on
cherche à calculer. Il faut dans ces cas-là ruser, simplifier
l’expression de la fonction considérée ou même être imaginatif !
Toutes sortes de choses peuvent arriver !

Illustrons cette dernière affirmation. Commençons par donner un
exemple de deux fonctions qui divergent vers :math:`+\infty` en un
point mais dont la différence ne converge pas vers :math:`0`, elle
diverge vers :math:`-\infty`. 
   
  Considérons les deux fonctions :

  .. math::

     \begin{aligned}
     f : {\mathbb{R}}_{0} \to \mathbb{R}\\
     x \mapsto \frac{1}{x^2}\end{aligned}

  .. math::

     \begin{aligned}
     g : {\mathbb{R}}_{0} \to \mathbb{R}\\
     x \mapsto \frac{1}{x^4}\end{aligned}

  On a :

  .. math:: \lim\limits_{x \to 0} \frac{1}{x^2} =+\infty

  .. math:: \lim\limits_{x \to 0} \frac{1}{x^4} =+\infty

  Pour tout :math:`x \in {\mathbb{R}}_{0}`, on a :

  .. math:: (f-g)(x) = \frac{1}{x^2}-\frac{1}{x^4}=\frac{x^2}{x^4}-\frac{1}{x^4}=\frac{x^2-1}{x^4}

  La fonction :math:`(f-g) : {\mathbb{R}}_{0} \to \mathbb{R}` peut être
  vue comme le produit des deux fonctions :

  .. math::

     \begin{aligned}
     h : {\mathbb{R}}_{0} \to \mathbb{R}\\
     x \mapsto x^2-1\end{aligned}

  .. math::

     \begin{aligned}
     l : {\mathbb{R}}_{0} \to \mathbb{R}\\
     x \mapsto \frac{1}{x^4}\end{aligned}

  On a :

  .. math:: \lim\limits_{x \to 0} x^2-1 =-1

  .. math:: \lim\limits_{x \to 0} \frac{1}{x^4} =+\infty

  Par la proposition 3.8.10, on en déduit que :

  .. math:: \lim\limits_{x \to 0} (f-g) (x) =-\infty

  À présent, donnons un exemple de deux fonctions qui divergent vers
  :math:`+\infty` en un point mais dont la différence diverge vers
  :math:`+\infty`. Considérons les deux fonctions :

  .. math::

     \begin{aligned}
     f : {\mathbb{R}}_{0} \to \mathbb{R}\\
     x \mapsto \frac{1}{x^4}\end{aligned}

  .. math::

     \begin{aligned}
     g : {\mathbb{R}}_{0} \to \mathbb{R}\\
     x \mapsto \frac{1}{x^2}\end{aligned}

  On a :

  .. math:: \lim\limits_{x \to 0} \frac{1}{x^4} =+\infty

  .. math:: \lim\limits_{x \to 0} \frac{1}{x^2} =+\infty

  Pour tout :math:`x \in {\mathbb{R}}_{0}`, on a :

  .. math:: (f-g)(x) = \frac{1}{x^4}-\frac{1}{x^2}=\frac{1}{x^4}-\frac{x^2}{x^4}=\frac{1-x^2}{x^4}

  La fonction :math:`(f-g) : {\mathbb{R}}_{0} \to \mathbb{R}` peut être
  vue comme le produit des deux fonctions :

  .. math::

     \begin{aligned}
     h : {\mathbb{R}}_{0} \to \mathbb{R}\\
     x \mapsto 1-x^2\end{aligned}

  .. math::

     \begin{aligned}
     l : {\mathbb{R}}_{0} \to \mathbb{R}\\
     x \mapsto \frac{1}{x^4}\end{aligned}

  On a :

  .. math:: \lim\limits_{x \to 0} 1-x^2 =1

  .. math:: \lim\limits_{x \to 0} \frac{1}{x^4} =+\infty

  Par la proposition 3.8.10, on en déduit que :

  .. math:: \lim\limits_{x \to 0} (f-g) (x) =+\infty

  Enfin, la différence de deux fonctions qui divergent vers
  :math:`+\infty` en un point peut malgré tout parfois converger (vers
  :math:`0` ou un autre nombre). Considérons par exemple les deux
  fonctions :

  .. math::

     \begin{aligned}
     f : {\mathbb{R}}_{0} \to \mathbb{R}\\
     x \mapsto \frac{x^2+x^4}{x^4}\end{aligned}

  .. math::

     \begin{aligned}
     g : {\mathbb{R}}_{0} \to \mathbb{R}\\
     x \mapsto \frac{1}{x^2}\end{aligned}

  On a :

  .. math:: \lim\limits_{x \to 0} \frac{x^2+x^4}{x^4} =+\infty

  .. math:: \lim\limits_{x \to 0} \frac{1}{x^2} =+\infty

  Pour tout :math:`x \in {\mathbb{R}}_{0}`, on a :

  .. math:: (f-g)(x) = \frac{x^2+x^4}{x^4}-\frac{1}{x^2}=\frac{x^2+x^4}{x^4}-\frac{x^2}{x^4}=\frac{x^4}{x^4}=1

  On en déduit :

  .. math:: \lim\limits_{x \to 0} (f-g) (x) =\lim\limits_{x \to 0} 1=1

  Comme on peut le voir avec ces trois exemples, lorsqu’on est face à
  une indétermination, il n’y a pas d’autre choix que de se mettre à
  réfléchir. Il n’y a pas de loi générale.


| Avant de passer aux exercices, donnons une règle de calcul que
  certains apprécient énormément : la règle des plus grands exposants.
  Elle permet de calculer facilement une limite pour :math:`x` qui tend
  vers :math:`+\infty` (ou vers :math:`-\infty`) dans le cas d’une
  fonction rationnelle (quotient de deux polynômes).

|

**Théorème 3.8.22.** (Théorème de la règle des plus hautes puissances)

| Soit :math:`I` un intervalle non majoré.
| Soient :math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}`
  avec :math:`g(x) \neq 0` pour tout :math:`x \in I` telles que pour
  tout :math:`x \in I` :

  .. math:: f(x) = a_n x^n + a_{n-1} x^{n-1} + ... + a_2 x^2 + a_1 x + a_0

  .. math:: f(x) = b_m x^m + b_{m-1} x^{m-1} + ... + b_2 x^2 + b_1 x + b_0

  pour un certain :math:`n \in \mathbb{N}`, un certain
  :math:`m \in \mathbb{N}` et
  :math:`a_n , a_{n-1} , ... , a_2 , a_1 , a_0 \in \mathbb{R}` avec
  :math:`a_n \neq 0` et
  :math:`b_m , b_{m-1} , ... , b_2 , b_1 , b_0 \in \mathbb{R}` avec
  :math:`b_m \neq 0`. Alors :

  -  Si :math:`\lim\limits_{x \to +\infty} \frac{a_n x^n}{b_m x^m} = +\infty`,
      on a :

      .. math:: \lim\limits_{x \to +\infty} \frac{f(x)}{g(x)} = +\infty

  -  Si :math:`\lim\limits_{x \to +\infty} \frac{a_n x^n}{b_m x^m} = -\infty`,
      on a :

      .. math:: \lim\limits_{x \to +\infty} \frac{f(x)}{g(x)} = -\infty

  -  Si :math:`\lim\limits_{x \to +\infty} \frac{a_n x^n}{b_m x^m} = L`
      pour un certain :math:`L \in \mathbb{R}`, on a :

.. math:: \lim\limits_{x \to +\infty} \frac{f(x)}{g(x)} = L

*Démonstration* Pour tout :math:`x \in I` avec :math:`x \neq 0`, on a :

.. math:: \frac{a_n x^n + a_{n-1} x^{n-1} + ... + a_2 x^2 + a_1 x + a_0}{b_m x^m + b_{m-1} x^{m-1} + ... + b_2 x^2 + b_1 x + b_0} = \frac{a_n x^n}{b_m x^m} \frac{1 + \frac{a_{n-1} x^{n-1}}{a_n x^n} + ... + \frac{a_2 x^2}{a_n x^n} + \frac{a_1 x}{a_n x^n} + \frac{a_0}{a_n x^n}}{1 + \frac{b_{m-1} x^{m-1}}{b_m x^m} + ... + \frac{b_2 x^2}{b_m x^m} + \frac{b_1 x}{b_m x^m} + \frac{b_0}{b_m x^m}}

Par les propriétés des limites, on a :

.. math:: \lim\limits_{x \to +\infty} 1 + \frac{a_{n-1}}{a_n x^n} x^{n-1} + ... + \frac{a_2 x^2}{a_n x^n} + \frac{a_1 x}{a_n x^n} + \frac{a_0}{a_n x^n} ={}

.. math:: \lim\limits_{x \to +\infty} 1 + \lim\limits_{x \to +\infty} \frac{a_{n-1}}{a_n x} + ... + \lim\limits_{x \to +\infty} \frac{a_2}{a_n x^{n-2}} + \lim\limits_{x \to +\infty} \frac{a_1}{a_n x^{n-1}} + \lim\limits_{x \to +\infty} \frac{a_0}{a_n x^n} = 1+0+...+0+0+0=1

De même :

.. math:: \lim\limits_{x \to +\infty} 1 + \frac{b_{m-1}}{b_n x^m} x^{m-1} + ... + \frac{b_2 x^2}{b_m x^m} + \frac{b_1 x}{b_m x^m} + \frac{b_0}{b_m x^m} ={}

.. math:: \lim\limits_{x \to +\infty} 1 + \lim\limits_{x \to +\infty} \frac{b_{m-1}}{b_m x} + ... + \lim\limits_{x \to +\infty} \frac{b_2}{b_m x^{m-2}} + \lim\limits_{x \to +\infty} \frac{b_1}{b_m x^{m-1}} + \lim\limits_{x \to +\infty} \frac{b_0}{b_m x^m} = 1+0+...+0+0+0=1

Par les propriétés des limites, on a donc :

.. math:: \lim\limits_{x \to +\infty}\frac{1 + \frac{a_{n-1} x^{n-1}}{a_n x^n} + ... + \frac{a_2 x^2}{a_n x^n} + \frac{a_1 x}{a_n x^n} + \frac{a_0}{a_n x^n}}{1 + \frac{b_{m-1} x^{m-1}}{b_m x^m} + ... + \frac{b_2 x^2}{b_m x^m} + \frac{b_1 x}{b_m x^m} + \frac{b_0}{b_m x^m}} = \frac{1}{1}=1

Dès lors :

-  Si
   :math:`\lim\limits_{x \to +\infty} \frac{a_n x^n}{b_m x^m} = +\infty`,
   par les propriétés des limites et des divergences, on a :

   .. math:: \lim\limits_{x \to +\infty} \frac{f(x)}{g(x)} = +\infty

-  Si
   :math:`\lim\limits_{x \to +\infty} \frac{a_n x^n}{b_m x^m} = -\infty`,
   par les propriétés des limites et des divergences, on a :

   .. math:: \lim\limits_{x \to +\infty} \frac{f(x)}{g(x)} = -\infty

-  Si :math:`\lim\limits_{x \to +\infty} \frac{a_n x^n}{b_m x^m} = L`
   pour un certain :math:`L \in \mathbb{R}`, par les propriétés des
   limites, on a :

   .. math:: \lim\limits_{x \to +\infty} \frac{f(x)}{g(x)} = L.1=L

|

**Remarque 3.8.23.** Le théorème est également valable lorsqu’on considère une limite pour
:math:`x` qui tend vers :math:`-\infty`.

**Exemple 3.8.24.** On souhaite déterminer la limite suivante :

.. math:: \lim\limits_{x \to +\infty}  \frac{1-x^2-x^3}{3x^3+2x+7}

Le théorème de la règle des plus hautes puissances nous dit que si la
limite ci-dessous existe, alors la limite que nous recherchons existe
aussi et est égale à celle-ci :

.. math:: \lim\limits_{x \to +\infty}  \frac{-x^3}{3x^3}

Or :

.. math:: \lim\limits_{x \to +\infty}  \frac{-x^3}{3x^3} = \lim\limits_{x \to +\infty}  \frac{-1}{3}=\frac{-1}{3}

Conclusion, par le théorème de la règle des plus hautes puissances, on
déduit que :

.. math:: \lim\limits_{x \to +\infty}  \frac{1-x^2-x^3}{3x^3+2x+7}=\frac{-1}{3}

|  

| Et maintenant, des exercices. Beaucoup d’exercices !

**Exercice 3.8.25.** Soit :math:`I` un intervalle éventuellement privé d’un point
:math:`c`. Soient :math:`f : I \to \mathbb{R}` et
:math:`g : I \to \mathbb{R}` telles que
:math:`\lim\limits_{x \to c} f(x) = +\infty` et
:math:`\lim\limits_{x \to c} g(x) = -\infty`.

Que peut-on dire au sujet du comportement de la fonction
:math:`(f.g) : I \to \mathbb{R}` au voisinage de :math:`c` ?
Converge-t-elle ? Diverge-t-elle ? Expliquer.

**Solution.** Puisque :math:`\lim\limits_{x \to c} f(x) = +\infty`, pour des nombres
:math:`x` de plus en plus proches de :math:`c`, les nombres :math:`f(x)`
deviennent uniformément et définitivement arbitrairement grands. Puisque
:math:`\lim\limits_{x \to c} g(x) = -\infty`, pour des nombres :math:`x`
de plus en plus proches de :math:`c`, les nombres :math:`g(x)`
deviennent uniformément et définitivement arbitrairement petits. Dès
lors, pour des nombres :math:`x` de plus en plus proches de :math:`c`,
les nombres :math:`f(x).g(x)` deviennent uniformément et définitivement
arbitrairement petits (le produit de nombres de plus en plus grands par
des nombres petits est de plus en plus petit).

|

**Exercice 3.8.26.** Soit :math:`I` un intervalle non minoré. Soient
:math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}` avec
:math:`g(x) \neq 0` pour tout :math:`x \in I` telles que
:math:`\lim\limits_{x \to -\infty} f(x) = L` pour un certain
:math:`L \in \mathbb{R}` et
:math:`\lim\limits_{x \to -\infty} g(x) = -\infty`.

Que peut-on dire au sujet du comportement de la fonction
:math:`(\frac{f}{g}) : I \to \mathbb{R}` pour :math:`x` qui tend vers
:math:`- \infty` ? Converge-t-elle ? Diverge-t-elle ? Expliquer.

**Solution.** Puisque :math:`\lim\limits_{x \to -\infty} f(x) = L`, pour des nombres
:math:`x` de plus en plus petits, les nombres :math:`f(x)` se
rapprochent uniformément et définitivement de :math:`L`. Puisque
:math:`\lim\limits_{x \to -\infty} g(x) = -\infty`, pour des nombres
:math:`x` de plus en plus petits, les nombres :math:`g(x)` deviennent
uniformément et définitivement arbitrairement petits. Dès lors, pour des
nombres :math:`x` de plus en plus petits, les nombres
:math:`\frac{f(x)}{g(x)}` se rapprochent uniformément et définitivement
de :math:`0` (le quotient de nombres de plus en plus proche d’un nombre
:math:`L` divisés par des nombres de plus en plus petits est de plus en
plus proche de :math:`0`).

|

**Exercice 3.8.27.** Soit :math:`I` un intervalle non majoré. Soient
:math:`f : I \to \mathbb{R}` et :math:`g : I \to \mathbb{R}` avec
:math:`g(x) \neq 0` pour tout :math:`x \in I` telles que
:math:`\lim\limits_{x \to +\infty} f(x) = -\infty` et
:math:`\lim\limits_{x \to +\infty} g(x) = \infty`.

Que peut-on dire au sujet du comportement de la fonction
:math:`(f-g) : I \to \mathbb{R}` pour :math:`x` qui tend vers
:math:`+\infty` ? Converge-t-elle ? Diverge-t-elle ? Expliquer.

**Solution.** Puisque :math:`\lim\limits_{x \to +\infty} f(x) = -\infty`, pour des
nombres :math:`x` de plus en plus grands, les nombres :math:`f(x)`
deviennent uniformément et définitivement arbitrairement petits. Puisque
:math:`\lim\limits_{x \to +\infty} g(x) = \infty`, pour des nombres
:math:`x` de plus en plus grands, les nombres :math:`g(x)` deviennent
uniformément et définitivement arbitrairement grands. Dès lors, pour des
nombres :math:`x` de plus en plus petits, les nombres :math:`f(x)-g(x)`
deviennent uniformément et définitivement arbitrairement petits (des
nombres de plus en plus petits auquels on enlève des nombres de plus en
plus grands donnent de plus en plus petits).

|

**Exercice 3.8.28.** En utilisant les propriétés des limites et des divergences, déterminer
les limites ou les divergences suivantes.

.. inginious:: limite9_1
.. inginious:: limite9_2
.. inginious:: limite9_3
.. inginious:: limite9_4
.. inginious:: limite9_5
.. inginious:: limite9_6
.. inginious:: limite9_7
.. inginious:: limite9_8
.. inginious:: limite9_9
.. inginious:: limite9_10

|

4 Annexe
========

| Cette section facultative contient une démonstration du fait que la
  somme de deux fonctions continues est toujours une fonction continue.
|   
| Pour démontrer que la somme de deux fonctions continues est continue,
  nous avons besoin d’un lemme *extrêmement* connu : l’inégalité
  triangulaire. C’est un des résultats de base les plus importants en
  analyse mathématique.

**Lemme 4.0.1.** Soient deux nombres réels :math:`x,y \in \mathbb{R}`.
On a toujours :

.. math:: |x+y| \le |x|+|y|

**Démonstration** Si :math:`x` et :math:`y` sont deux nombres positifs, les valeurs
absolues sont inutiles et l’inégalité devient :

.. math:: x+y \le x+y

Ce qui est évidemment vrai. Il suffit de vérifier les autres cas, ceux
où :math:`x` et :math:`y` ne sont pas tous les deux positifs.

-  Si :math:`x` est strictement négatif et :math:`y` aussi, alors
   :math:`x+y` aussi. L’inégalité devient alors :

   .. math:: -(x+y) \le -x-y

   Ce qui est aussi évidemment vrai.

-  Si :math:`x` est strcitement négatif mais :math:`y` est positif,
   l’inégalité devient :

   .. math:: |x+y| \le -x+y

   Il y a deux possibilités :

   -  Soit :math:`x` est moins grand négativement que :math:`y` est
      grand positivement, plus précisément :math:`x+y > 0` (ce qui est
      équivalent à dire que :math:`y>-x`), alors on peut faire
      disparaître la dernière valeur absolue et l’inégalité devient :

      .. math:: x+y \le -x+y

      Autrement dit :

      .. math:: 2x \le 0

      Ce qui est vrai puisque justement :math:`x` est strictement
      négatif.

   -  Soit :math:`x` est plus grand négativement que :math:`y` est grand
      positivement, plus précisément :math:`x+y < 0` (ce qui est
      équivalent à dire que :math:`y<-x`), alors pour faire disparaître
      la dernière valeur absolue on doit multiplier son contenu par
      :math:`-1` :

      .. math:: -(x+y) \le -x+y

      Autrement dit :

      .. math:: -x-y \le -x+y

      C’est-à-dire :

      .. math:: 0 \le 2y

      Ce qui est vrai puisque justement :math:`y` est positif.

-  Si :math:`x` est positif mais :math:`y` est strictement négatif, il
   s’agit du même cas que le cas précédent avec les rôles de :math:`x`
   et :math:`y` inversés. Donc ça fonctionne aussi.

Tous les cas ont été testés, donc on a bien toujours (quelque soit le
cas dans lequel on se trouve) :

.. math:: |x+y| \le |x|+|y|

À présent, nous pouvons démontrer que si on additionne deux fonctions
définies sur un même intervalle dont on sait qu’elles sont continues en
un point :math:`c` de cet intervalle, leur somme est continue en ce
point :math:`c` :

**Proposition 4.0.2** Soit :math:`I` un intervalle. Soit :math:`f:I \to \mathbb{R}` et
:math:`g: I \to \mathbb{R}` deux fonctions continues en
:math:`c \in I`.

Alors la fonction :math:`(f+g) : I \to \mathbb{R}` est continue en
:math:`c`.

*Démonstration* Nous devons démontrer que pour tout :math:`\epsilon>0`, on peut
trouver :math:`\delta >0` tel que pour tous les :math:`x \in I` qui
sont à une distance au plus :math:`\delta` de :math:`c`, c’est-à-dire
tel que :math:`|x-c| < \delta`, on est certain qu’on a
:math:`|(f(x)+g(x))-(f(c)+g(c))|<\epsilon` (c’est ce que signifie que
:math:`f+g` est continue en :math:`c`).

Fixons un :math:`\epsilon` strictement plus grand que :math:`0`
quelconque (pour montrer que ça marche pour tous les :math:`\epsilon`,
il suffit de montrer que ça marche pour un :math:`\epsilon`
quelconque/générique) et montrons que nous pouvons trouver un tel
:math:`\delta` strcitement plus grand que :math:`0` pour cet
:math:`\epsilon`. Pour ce faire, utilisons ce que nous savons :

-  Nous savons que la fonction :math:`f` est continue en :math:`c` : en
   particulier, si on applique la définition pour la moitié du
   :math:`\epsilon` que nous nous sommes fixés, cela nous dit qu’il
   existe un :math:`{\delta}_f`, un :math:`\delta` propre à la fonction
   :math:`f`, tel que pour tous les :math:`x \in I` tel que
   :math:`|x-c|<{\delta}_f`, on est certain qu’on a
   :math:`|f(x)-f(c)| < \frac{\epsilon}{2}`.

-  Nous savons que la fonction :math:`g` est continue en :math:`c` : en
   particulier, pour le :math:`\epsilon` que nous nous sommes fixés,
   cela nous dit qu’il existe un :math:`{\delta}_g`, un :math:`\delta`
   propre à la fonction :math:`g`, tel que pour tous les :math:`x \in I`
   tel que :math:`|x-c|<{\delta}_g`, on est certain qu’on a
   :math:`|g(x)-g(c)| < \frac{\epsilon}{2}`.

| Pour le delta que nous voulons, il suffit alors de prendre le minimum
  de :math:`{\delta}_f` et :math:`{\delta}_g` :
  :math:`\delta = \min({\delta}_f;{\delta}_g)` (le plus petit des deux).
  En effet, on a alors que pour tout :math:`x \in I` tel que
  :math:`|x-c|<\delta`, puisque :math:`\delta` est le minimum de
  :math:`{\delta}_f` et :math:`{\delta}_g`, on a aussi que
  :math:`|x-c|<{\delta}_f` et :math:`|x-c|<{\delta}_g`, et donc on est
  certain que :math:`|f(x)-f(c)| < \frac{\epsilon}{2}` et
  :math:`|g(x)-g(c)| < \frac{\epsilon}{2}` à la fois.
| Dès lors, par l’inégalité triangulaire, on a pour tout :math:`x \in I`
  tel que :math:`|x-c|<\delta` :

  .. math::

     \begin{aligned}
         |(f(x)+g(x))-(f(c)+g(c))| &= |(f(x)-f(c))+(g(x)-g(c))| \\
         &\le |(f(x)-f(c))|+|(g(x)-g(c))| \\
         &<\frac{\epsilon}{2}+\frac{\epsilon}{2}\\
         &<\epsilon
         \end{aligned}

  Ce qui conclut la démonstration.

.. [1]
   Remarque : pour la plupart des fonctions de référence, la
   démonstration n’est pas très compliquée. N’hésitez pas à essayer de
   faire vous-même la preuve par exemple pour une fonction constante ou
   pour la fonction identité.

.. [2]
   La démonstration de ce théorème est en fait assez compliquée et
   nécessite de bien comprendre les propriétés fondamentales des nombres
   réels. Heureusement, son énoncé est très intuitif.

.. [3]
   La démonstration de ce théorème est aussi assez compliquée.
