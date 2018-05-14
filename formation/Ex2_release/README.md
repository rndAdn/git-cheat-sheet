
# État de départ (local)

```
*   ff978fc (HEAD -> master, origin/master) Merge branch 'release/1.2'
|\  
| * 40d27cd (origin/release/1.2, release/1.2) [1.2.0] add GUI.java
| * 5931851 (tag: 1.1.1, origin/release/1.1, release/1.1) [1.1.1] HOTFIX update CLI.java
* | 042b11b [1.3.0] update Web.java
* |   b537c24 merge 1.1 feature
|\ \  
| |/  
| * 074472b (tag: 1.1) [1.1.0] update CLI.java
* | 16ff4e1 [1.3.0] Add Web.java
|/  
* 9dcca0b [1.1.0] Add CLI.java
* 9f149c3 (tag: 1.0, origin/release/1.0, release/1.0) init repo
```


![start](start.png)

# TODO

## Faire une feature sur la version 1.2.0 (release/1.2)

* Créer une branche de 'feature' à partir de la release 1.2 (release/1.2)
* Ajouter un fichier 'feature_1.2.java'
* Commit, merge et push les changements

!!! Les changements dans la version 1.2 doivent être présents dans la 1.3 (master) !!!


!!!! Attention votre repo local n'est pas forcément à jour  !!!!



# État d'arrivé (local)

```
*   20f3c15 (HEAD -> master, origin/master) Merge feature from 'release/1.2'
|\  
| * 0615672 (origin/release/1.2, release/1.2) [1.2.0] update GUI.java
* | d95984d [1.3.0] update Web.java
* |   ff978fc Merge branch 'release/1.2'
|\ \  
| |/  
| * 40d27cd [1.2.0] add GUI.java
| * 5931851 (tag: 1.1.1, origin/release/1.1, release/1.1) [1.1.1] HOTFIX update CLI.java
* | 042b11b [1.3.0] update Web.java
* |   b537c24 merge 1.1 feature
|\ \  
| |/  
| * 074472b (tag: 1.1) [1.1.0] update CLI.java
* | 16ff4e1 [1.3.0] Add Web.java
|/  
* 9dcca0b [1.1.0] Add CLI.java
* 9f149c3 (tag: 1.0, origin/release/1.0, release/1.0) init repo

```



# Correction

#### création de la branche de feature
```
git checkout release/1.2
git checkout -b feature/ex2
```


#### dev de la feature
```
touch ex2.java
git add ex2.java
git commit -m "[1.2.0] add ex2.java"
```



#### Récupération des derniers changements sur release/1.2
```
git checkout release/1.2
git pull --rebase origin release/1.2
```

#### On ajoute les changement de release/1.2 dans notre branch de feature
```
git checkout feature/ex2
git rebase release/1.2
```


#### On intègre notre feature dans la branch  release/1.2

```
git checkout release/1.2
git merge feature/ex2
```

#### On push notre travail

```
git push origin release/1.2
```

#### Récupération des derniers changements sur master
```
git checkout master
git pull --rebase origin master
```


#### On intègre notre feature dans la branch  release/1.2

```
git merge release/1.2
```

#### On push notre travail

```
git push origin master
```
