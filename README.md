# TP7 : Collections

### Objectifs
Manipuler le différentes collections de l'api java

### Prérequis
- Cloner le projet sur votre poste dans le repertoire de votre choix
- Ouvrir le projet :
  - Sur l'écran d'accueil d'IntelliJ, cliquer sur **Open**
  - Sélectionner le dossier **tpX-xxx** qui a été copié depuis github puis cliqué sur **OK**.
  - Le projet s'ouvre
  - Allez vérifier que le SDK est bien sélectionné dans **File > Project Structure** onglet **Project**

### Utilisation de GIT

- Créer une nouvelle branche **prenomNom**
- Faire **1 commit** par exercice (sauf exercice 0)
- Ouvrir **une seule** *pull request* sur github et **ne pas** la fermer/merger !!



> Si vous ne l'avez pas encore fait, pensez a créer une nouvelle branche **prenomNom**



### Exercice 1

- Créer une classe **Nuancier**  dans le package **net.lecnam.ussi47.tp7.nuancier**

- Ajouter une propriété **couleurs** de type *List* ne pouvant contenir que des *String* (ne pas l'initialiser)

- Ajouter un getteur pour cette propriété

- Dans un constructeur sans paramètre

  - Initialisez cette Liste en lui affectant un objet *ArrayList*
  - Ajouter des chaines à la liste qui correspondent aux couleurs :  **noir**, **rouge**, **vert**, **marron**, **blanc**
  - Si possible, ajouter une 2ème fois le **rouge**
  - Ajouter la couleur **cyan** à la première position sans retoucher au début de votre code.
  
- Dans **Execute**, compléter la méthode **exercice1()** pour : 

  - Afficher le nombre d'éléments dans la liste

  - Parcourez la liste pour afficher son contenue **de 3 manières différentes ** (vous pouvez séparer chaque parcours grâce à ```System.out.println("----------------");```)

    - avec un *for*
    - avec un *foreach*
    - avec un *iterator*

    Vérifiez que la couleur *cyan* est bien en première position

  - Trier la liste et parcourez là 1 fois avec la solution de votre choix
  
- Executer la méthode **exercice1()** dans le main()

> Pensez à faire votre 1er commit !!  

### Exercice 2

- Dans **Nuancier** créer une méthode ```public Set<String> getCouleursTreeSet()```
- Cette méthode doit retoruner un TreeSet créé à partir de **couleurs** (ça tient en 1 ligne !)

- Dans **Execute**, compléter la méthode **exercice2()** pour : 
  - Afficher le contenu du treeSet, que remarquez vous ? (ajouter un commentaire dans votre code pour expliquer...)
- Executer la méthode **exercice2()** dans le main()

> Pensez à faire un commit !!  

### Exercice 3

- Dans **Nuancier**, 
  - créer un attribut **couleursMap** : ```private Map<Character, String> couleursMap```
  - Créer une méthode privée ```private void initializeMap()``` qui va initialiser l'attribut couleursMap avec une HashMap dont la valeur est la couleur et la clé est la 1ère lettre de la couleur. Pour celà :
    - Commencer par initialiser l'attribut *couleursMap* avec un objet Hashmap. 
    - Ensuite, parcourez le treeSet et à chaque itération, ajouter une couleur avec comme clé la 1ère lettre de la couleur.
  - Appeler la méthode *initializeMap()* à la fin de votre constructeur afin que la hashmap soit crée immédiatement après l'affectation des couleurs dans la liste.
  - créer une méthode ``public String getCouleurFromCode(char initiale)`` qui doit renvoyer la bonne couleur selon la lettre demandée
- Dans **Execute**, compléter la méthode **exercice3()** pour : 
  - Appeler **getCouleurFromCode ** et afficher la couleur qui correspond à r
- Executer la méthode **exercice3()** dans le main()

> Pensez à faire un commit !!  

### Exercice 4

- Les classes précédentes ne seront plus utilisées, vous pouvez commenter les appels aux méthodes exercice1(), exercice2(), exercice3()
- Créer une classe **Film** dans le package **net.lecnam.ussi47.tp7.film**
  - Un film a un titre, un realisateur et une année de sortie (de type java.time.Year)
  - Créer les getter (pas de setter)
  - Créer un constructeur ```public Film(String titre, String realisateur,  int annee)``` et convertir dans ce contructeur anneeSortie en *Year* (https://docs.oracle.com/en/java/javase/19/docs/api/java.base/java/time/Year.html#of(int))
  - Redefinir la méthode ```public String toString()``` afin d'afficher une chaine de la forme **titre, realisateur, aaaa**
  - Faire en sorte que **Film** soit **Comparable** sur l'année de sortie, pour cela, Film doit implémenter **Comparable<Film>** et vous devez alors créer une méthode **compareTo(Film f)** qui va comparer la date de sortie du film de l'objet courrant avec celle de l'objet **f**
  - Dans **Execute**, compléter la méthode **exercice4()**  : 
      - Créer plusieurs film avec de années différentes (pour vous aider : https://www.themoviedb.org/movie/top-rated)
      - Ajouter ces films dans une collection nativement triée
      - Afficher le contenu de la collection et vérifier que c'est bien triée par année ascendante
      - Créer une **ArrayList** a partir de votre collection
      - Trouver dans la classe **Collections** une méthode pour inverser l'ordre d'une liste et appliquer là sur votre arrayList
      - Afficher le contenu de votre **ArrayList**
- Executer la méthode **exercice4()** dans le main()

> Pensez à faire un commit !!  

### Exercice 5

- Créer une classe **FilmService** dans le package **net.lecnam.ussi47.tp7.film** 
- Dans cette classe :
  - Déclarer  un attribut ```private static Set<Film> filmSet;```
  - Créer une méthode ```private void importFilm()  throws IOException```  et écrivez le code pour lire le fichier *films.csv* disponible à la racine du projet et importer le contenu dans *filmSet*. Utilisez les classes du package java.nio.file vues au cours précédent. Cette méthode doit convertir chaque ligne et créer un objet Film à partir des données extraites. Vous pouvez utiliser des méthodes de découpage (**split(String)** par exemple).
  - Créer une méthode ```printFilms()``` qui affiche les caractéristiques de tous les films
  - Créer un constructeur ```public FilmService() throws IOException```qui initialise **filmSet** et importe les films dans **filmSet**.
- Dans **Execute**, compléter la méthode **exercice5()**  : 
  - Créer un objet FilmService, les films doivent se charger
  - Afficher les films

> Pensez à faire un commit !!  


### Exercice 6

- Dans la classe **FilmService**:
 - créer une méthode ```public void searchFilm(String search) ``` qui affiche une liste de film dont le titre contient la chaine passée en paramètre.
- Dans **Execute**, compléter la méthode **exercice5()**  :
  - Faite une recherche sur la chaine *man*, plusieurs films doivent s'afficher

> Pensez à faire un commit !!

### Exercice 7 

- On veut indexer les films par année pour les afficher plus rapidement 
- Dans la classe **Film**
  - Modifier la méthode ```compareTo(Film film)``` afin qu'elle compare sur l'année puis sur les titres.
- Ajouter un attribut ``private static Map<Year, Set<Film>> indexParAnnee;`` 
  - Allouer une HashMap à cet attribut dans le constructeur
  - Dans la boucle de la méthode **importFilms()** ajouter le film a la map (ce n'est pas si simple, si l'année est déjà dans une clé, il faut récupérer le sous ensemble de film et ajouter le film. Sinon, il faut ajouter la clé et un nouveau sous ensemble de films)
- Créer une méthode ``public void searchFilmByAnnee(int search) `` elle affiche les films de l'année indiquée en paramètre
- Dans **Execute**, compléter la méthode **exercice6()**  : 
  - Faite une recherche sur 1985, 39 films doivent s'afficher

> Pensez à faire un commit et un push !!





