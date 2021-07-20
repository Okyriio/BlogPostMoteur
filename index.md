## Moteur Physique


BlogpostGPR4400

Ce projet de jeu vient à l'origine dans le cadre du dernier module de la première année de ma formation à la SAE Institute.

Introduction :

Pour ce dernier module de l'année nous avons eu comme défi de créer un moteur physique simple mais fonctionnel. Contrairement aux autres modules, il y a eu beaucoup de difficultés, ce module comportant beaucoup de maths et de physique, nous étions tous perplexe tout le long de ce défi.

Les Vector2 :

La base de tout notre moteur qui est en 2D se base sur les vecteurs. Nous avons donc créer des vecteurs utilisables avec tout les operators possible afin de nous faciliter la tache plus tard.
![image](https://user-images.githubusercontent.com/71374090/126316217-78395316-cb3b-4b71-8f8f-21e001421bfc.png)

Les Circles :

Ensuite nous avions du créer des cercles, qui sont crées principalement à partir de Vector2f (merci la section précédente) qui seront nos objets de collisions pour ce moteur.
Nous avons aussi créer des fonctions qui permettent de calculer si oui ou non ces cercles sont en collisions (intersect) les unes avec les autres.

![image](https://user-images.githubusercontent.com/71374090/126316778-ad6b54a2-65db-46e4-84d9-15798302168f.png)
La vérification des collisons ici : 
![image](https://user-images.githubusercontent.com/71374090/126316845-523dd257-bfcb-4d5f-951c-b059ad6f85bc.png)

Les collisions :

Suite à ça nous pouvons déterminer si les cercles se touchent ou non. Nous créons donc un cercle : 
![image](https://user-images.githubusercontent.com/71374090/126317356-e5803428-6d03-49fa-8f2c-cbce28924fd5.png)

Et dans le cas d'une intersection nous devons la résoudre, vient alors notre fonction "ResolveIntersect" qui s'occupe de simuler les directions après la collision qui donne cette effet de boule qui se touche avec un sentiment d'impact :

![image](https://user-images.githubusercontent.com/71374090/126317681-5d7bf236-04b5-4093-a54d-4eecfdc0df6f.png)

Ce calcul nous a imposé un autre problèmes, les cercles restaient collées entre-elle au lieu de rebondir, mais grâce à notre fonction "RelocateCenter" qui fait en sorte que une vois en collision les cercles ne restent pas collées les une aux autres et redéfini la position du centre du cercle assez loin du deuxième cercle.

![image](https://user-images.githubusercontent.com/71374090/126318040-f1c56ef0-d6bc-4f15-b1c9-e714038d748d.png)

Ce qui nous donne finalement un résultat plutot agréable. 

![boulephys](https://user-images.githubusercontent.com/71374090/126319096-6affb5a2-876e-434e-862e-72565fd8d16b.gif)

Difficultés :

Mélanger math, physique, et C++ étaient très difficile pour ma part, comprendre la théorie elle-même était assez simple, mais implémenter par la suite était une tâche difficile. Comprendre comment le language interprète nos lignes de codes de physique et comment ce qu'on écrivait se répercutait sur la fonctionnement de notre moteur était subtil. Mais tout cela m'a permit d'avoir une plus grand vue d'ensemble du C++ et m'a apporté une compréhension du language que je n'avais pas jusqu'ici, malgré le fait que je me considère toujours un énorme débutant. Fixer la physique de nos cercles nous a pris plus ou moins 3 semaines (sans le grid et les polygons dont je parlerais au prochain paragraphe. Nous avions aussi eu une immense quantité de script auquel certains d'entre nous n'avaient pas encore eu affaire.

Déceptions :

Malgré les difficultés, j'ai deux grosses déceptions, la première est que nous avons pas réussis à implémenter d'autre formes que des cercles (pour l'instant) donc pas de polygons dans mon moteur graphique actuel. La deuxième déception est que j'étais supposé implémenter un grid (une grille) afin de diviser l'écran par 10 et de fluidifier le processus (un peu comme un QuadTree). En divsant l'écran et en effectuant les intersections des cercles seulement présentes dans la même sous-division aurait permis à la simulation de ne pas ralentir dans le cas ou beaucoup de cercles étaient instantiés dans le programme. Malheureusement c'est un échec.

Conclusions :

En conclusion, ce module et ce projet (que j'appel un "défi") m'as beaucoup appris, comme la persévérance, les vecteurs ( que je connais plutôt bien désormais), les collisions etc. J'ai pas spécialement hâte de continuer ce moteur, ou de créer des outils pour un autre moteur, mais malgré tout ça je suis excité à l'idée d'en apprendre toujours plus. Comme c'est le cas depuis le début, rien de plus satisfaisant qu'un code qui fonctionne finalement.
