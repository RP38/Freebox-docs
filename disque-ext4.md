# Les disques ext4 sous Freebox OS

La Freebox pop est [capable de gérer les systèmes ext4 et xfs](https://assistance.free.fr/articles/89).
Si vous souhaitez utiliser une partition ext4/xfs déja existante, il vous sera impossible de l'utiliser sans modifier les permissions sur celle-ci.

En effet, après verification, il semble que par défaut la freebox pop est paramétrée pour utiliser un utilisateur sous l'id ```4242``` et le gid ```4242```
et non pas un utilisateur standard sous l'id ```1000``` et le gid ```1000``` (je n'ai trouvé aucune référence pour modifier cela par l'interface web, et il semble que l'accès au terminal ne soit plus possible sur cette box).

Il convient par conséquent de modifier les permissions des répertoires et fichiers afin de pouvoir lire et écrire.

La norme Linux décourage l'utilisation de permissions 777. Aussi je vous recommande à utiliser chown pour changer le propriétaire des répertoires/fichiers, ainsi que chgrp pour changer le groupe.
