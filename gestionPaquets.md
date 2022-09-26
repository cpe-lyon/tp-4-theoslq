**TP Gestion de Paquets**

**Exercice 1. Commandes de base**

1. 
```console
User@localhost:~$ sudo apt update
User@localhost:~$ sudo apt upgrade
```

2. 
```console
User@localhost:~$ alias maj='sudo apt update; sudo apt upgrade'
Il faut enregistrer l'allias dans le fichier bashrc pour qu'il ne soit pas perdu.
``` 

3.
```console
5 derniers paquets installés dpkg :
installed linux-headers-5.15.0-33:all 5.15.0-33.34
installed linux-headers-5.15.0-33-generic:amd64 5.15.0-33.34
installed linux-image-5.15.0-33-generic:amd64 5.15.0-33.34
installed linux-modules-5.15.0-33-generic:amd64 5.15.0-33.34
installed linux-modules-extra-5.15.0-33-generic:amd64 5.15.0-33.34
```

4.
```console
5 derniers paquets installés apt :
zlib1g:amd64 (1:1.2.11.dfsg-2ubuntu9, 1:1.2.11.dfsg-2ubuntu9.1)
gcc-12-base:amd64 (12-20220319-1ubuntu1, 12.1.0-2ubuntu1~22.04)
intel-microcode:amd64 (3.20220510.0ubuntu0.22.04.1, 3.20220809.0ubuntu0.22.04.1)
libstdc++6:amd64 (12-20220319-1ubuntu1, 12.1.0-2ubuntu1~22.04)
libgcc-s1:amd64 (12-20220319-1ubuntu1, 12.1.0-2ubuntu1~22.04)
```

5.
```console
User@localhost:~$ dpkg --list --installed | wc -l
dpkg : 622 
User@localhost:~$ apt list --installed | wc -l
apt : 615
```

6.
```console
User@localhost:~$ apt list  | wc -l
Il y a 68953 paquets disponibles en téléchargements dépot ubuntu.
```

7.
```console
Glances
User@localhost:~$ sudo apt install glances
```
![image](https://user-images.githubusercontent.com/97438358/192219794-6b0bd039-58e2-4fa4-81c4-9132b783582d.png)
```console
Tldr
User@localhost:~$ sudo apt install tldr
```
```console
Hollywood
User@localhost:~$ sudo apt install hollywood
```
![image](https://user-images.githubusercontent.com/97438358/192220275-5ac2eb42-9a9f-4a72-8f34-9b0d8ad8d567.png)

8.
```console
Sudoku
User@localhost:~$ sudo apt install sudoku
```
![image](https://user-images.githubusercontent.com/97438358/192221480-800b7450-8dc9-4801-aeae-9ac334cee475.png)

**Exercice 2.**
 
 