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

```console
A partir du paquet coreutils
User@localhost:~$ dpkg -S $(which -a ls)
```
![image](https://user-images.githubusercontent.com/97438358/192245961-a5bce332-3098-455c-972d-09704c042cd5.png) <br> <br>
![image](https://user-images.githubusercontent.com/97438358/192246571-33001383-3ebf-4241-8b1d-880da12733d6.png) <br> <br>
![image](https://user-images.githubusercontent.com/97438358/192247219-4ad123a0-2e6e-4257-8beb-a669f9fed6ce.png)

**Exercice 3.**  

```console
User@localhost:~$ sudo apt list hollywoo | grep "installed" && echo "INSTALLE" || echo "NON INSTALLE"
```
![image](https://user-images.githubusercontent.com/97438358/192953851-b445d50e-2ea2-4301-be86-a8ee5d59a68d.png)

**Exercice 4.**  

```console
User@localhost:~$ dpkg -L coreutils
```
```console
User@localhost:~$ dpkg -L coreutils | whereis [
[ est identique à la commande test, qui verifie le type d'un fichier et compare des valeurs.
```

**Exercice 5.**  
```console
Lynx : moteur de recherche
Emacs : éditeur de texte
```
**Exercice 6.**  
1.
```console
User@localhost:~$ sudo add-apt-repository ppa:linuxuprising/java
User@localhost:~$ sudo apt update
User@localhost:~$ sudo apt install oracle-java17-installer
```

```console
Il contient le chemin de notre depot créé PPA.
``` 
**Exercice 7.**  

1.
```console
User@localhost:~$ git clone https://gitlab.com/jallbrit/cbonsai
```

2.
```console
User@localhost:~$ git clone https://gitlab.com/jallbrit/cbonsai
```

3.
```console
User@localhost:~$ sudo apt install checkinstall
```

4.
```console
User@localhost:~$ sudo checkinstall bonsai
User@localhost:~$ sudo cbonsai
```

**Exercice 8.**  
**Création d’un paquet Debian avec dpkg-deb**  
1.
```console
User@localhost:~/script$ mkdir origine-commande
User@localhost:~/script/origine-commande$ mkdir DEBIAN
```
2.
```
User@localhost:~/script/origine-commande$ touch control
User@localhost:~/script/origine-commande$ nano control
Package: origine-commande
Version: 0.1
Maintainer: Foo Bar
Architecture: all
Description: Cherche l'origine d'une commande
Section: utils
Priority: optional
```

3.
```console
User@localhost:~/script$ dpkg-deb --build origine-commande
dpkg-deb: building package 'origine-commande' in 'origine-commande.deb'.
```

**Création du dépôt personnel avec reprepro**  
1.
```console
User@localhost:~$ mkdir repo-cpe
```
2.
```console
User@localhost:~/repo-cpe$ mkdir conf
User@localhost:~/repo-cpe$ mkdir packages
```
3.
```console
User@localhost:~/repo-cpe/conf$ touch distributions
User@localhost:~/repo-cpe/conf$ nano distributions
Origin:  Un nom, une URL, ou tout texte expliquant la provenance du dépôt
Label: repo-cpe
Codename: cosmic
Architectures: i386 amd64
Components: universe
Description: Une description du dépôt
```
4.
```console
User@localhost:~/repo-cpe$ reprepro -b . export
```
5.
```console
User@localhost:~/repo-cpe$ cp /home/User/script/origine-commande.deb /packages
User@localhost:~/repo-cpe/packages$ reprepro -b . includedeb cosmic origine-commande.deb
```
6.
```console
User@localhost:~/etc/apt/sources.list.d$  sudo touch repo-cpe.list
User@localhost:~/etc/apt/sources.list.d$  sudo nano repo-cpe.list
```
<img width="250" alt="image" src="https://user-images.githubusercontent.com/97438358/194759353-18efcd9d-f68d-4207-85fb-c65c9254fbdc.png">  

```console
on écrit dans le nano de repo-cpe.list, la ligne ci-dessus.
```

7.
```console
User@localhost:~/etc/apt/sources.list.d$ cd 
User@localhost:~$ sudo apt update
```
**Signature du dépôt avec GPG**  
1.
```console
User@localhost:~/repo-cpe$ gpg --gen-key
```
2.
```console
User@localhost:~/repo-cpe/conf$ nano distributions
Origin:  Un nom, une URL, ou tout texte expliquant la provenance du dépôt
Label: repo-cpe
Codename: cosmic
Architectures: i386 amd64
Components: universe
Description: Une description du dépôt
SignWith: yes
```
3.
```console
User@localhost:~/repo-cpe$ reprepro --ask-passphrase -b . export
```
4.
```console
User@localhost:~/repo-cpe$ gpg --export -a "auteur" > public.key
```
5.
```console
User@localhost:~/repo-cpe$ sudo apt-key add public.key
```
