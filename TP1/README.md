# IPSec

Dans un premier temps nous allons mettre en place un tunnel IPSec s'appuyant sur des
clés statiques et reposant sur ***L2TP***. Pour cela nous allons utiliser la commande ip du
packetage ***iproute2***. Dans cette première partie nous n'allons pas utiliser le protocole
***IKE*** et donc simplement mettre en place un tunnel reposant toujours sur les mêmes clés.
Ce n'est donc pas la solution recommandée pour mettre en place des VPNs persistants
mais plutot pour dépanner sur une courte période de temps.




Le but va être d'établir un tunnel IPSec en mode transport entre deux machines situées
chacune derrière une passerelle. Pour cela vous pouvez soit utiliser une architecture
virtualisée comme vu l'année dernière avec M. Bonnefoi, soit travailler avec des machines
virtuelles Virtualbox. Il vous faudra au minimum trois machines : 2 pour les machines
d'extrémité qui vont mettre en place le tunnel et 1 pour la passerelle. Il est néanmoins
recommandé de mettre en place 2 passerelles.



Pour la gestion d'IPSec on utilisera la commande ***ip xfrm*** et plus précisément ***ip xfrm state*** qui va permettre de définir les SA et ip xfrm policy qui permet de dinir les
SP.