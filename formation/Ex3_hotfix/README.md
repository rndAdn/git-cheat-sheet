
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

## Faire un Hotfix sur la version 1.1.1 (release/1.1) (ISO PROD)


* Créer une branche de 'hotfix' à partir de la release 1.1.1 (release/1.1)
* Modifier un fichier 'CLI.java'
* Commit, merge et push les changements

!!! Les changements dans la version 1.1 doivent être présents dans la 1.2 (release/1.2) et 1.3 (master) !!!

!!! Ne pas oublier le tag 1.1.2 sur la branche release/1.1 !!!

!!!! Attention votre repo local n'est pas forcément à jour  !!!!



# État d'arrivé (local)

```
*   81c1ad9 (HEAD -> master, origin/master) merge release 1.2 with hotfix 1.1.2
|\  
| *   3f94a45 (origin/release/1.2, release/1.2) merge hotfix 1.1.2 to release/1.2
| |\  
| | * 94872eb (tag: 1.1.2, origin/release/1.1, release/1.1) [1.1.2] HOTFIX  CLI.java
* | | d95984d [1.3.0] update Web.java
* | |   ff978fc Merge branch 'release/1.2'
|\ \ \  
| |/ /  
| * | 40d27cd [1.2.0] add GUI.java
| |/  
| * 5931851 (tag: 1.1.1) [1.1.1] HOTFIX update CLI.java
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

git checkout release/1.1
git checkout -b hotfixCLI1.1.2
```


#### dev du hotfix
```
git add --all
git commit -m "[1.1.2] HOTFIX  CLI.java"
```

#### Récupération des derniers changements sur release/1.1
```
git checkout release/1.1
git pull --rebase origin release/1.1
```


#### On ajoute les changement du hotfix dans notre branch de release/1.1
```
git checkout release/1.1
git merge hotfixCLI1.1.2
```


#### On push notre travail et on crée un nouveau tag

```
git push origin release/1.1
git tag -a "1.1.2"
git push --tags
```

#### Récupération des derniers changements sur release/1.2
```
git checkout release/1.2
git pull --rebase origin release/1.2
```


#### On intègre notre feature dans la branch  release/1.2

```
git merge release/1.1
git push origin release/1.2
```

#### Récupération des derniers changements sur master(1.3)
```
git checkout master
git pull --rebase origin master
```


#### On intègre notre feature dans la branch master(1.3)

```
git merge release/1.2
git push origin master
```
