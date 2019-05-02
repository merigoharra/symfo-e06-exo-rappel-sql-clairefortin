# SQL

## Contexte

Vous avez 4 tables existantes (`concert_hall`, `singer`, `album`, `song`) dont la mise en relation n'a pas été complètement réalisée.

Dans notre postulat de départ, nous pourrons considérer :

- Qu'un chanteur peut avoir réalisé plusieurs albums.
- Qu'une salle de concert peux accueillir plusieurs chanteurs en même temps à une date précise.
- Qu'un chanteur peut chanter plusieurs fois dans une même salle de concert.
- Qu'un album est associé à un seul chanteur.
- Qu'un album peux contenir plusieurs chansons.

Pour l'import des données, utiliser le script [`musicdb.sql`](https://raw.githubusercontent.com/O-clock-Alumni/fiches-recap/master/symfony/themes/ressources/musicdb.sql?token=AAN6C2JNNGWWTDFGW4I6KYK42KQI4). Si possible utiliser la ligne de commande pour importer le script.

=> **Consigner chaque requête d'exercice dans un script** (fichier .sql par exemple).

## Jointures & contraintes

1. Rajouter les jointures manquantes à nos tables.

> Note: la jointure entre album et song est déjà présente dans le schéma.
 
2. Faire en sorte qu'il ne puisse pas y avoir deux chanteurs identiques.
3. Rajouter un champ contenant le **nombre** de musiciens présents pour un chanteur et pour un concert (aucun musicien est possible).

Si vous souhaitez aller plus loin dans l'exercice, se rendre sur cette [partie optionnelle](BONUS.md) 

<details>
  <summary>Syntaxe SQL</summary>
  
  Lecture d'une table
  
 ```
 SELECT col1,col2
 FROM table1
 
 ```
 
 Créer une table
  
 ```
 CREATE TABLE `singer` (
  `my_id` int AUTO_INCREMENT UNSIGNED NOT NULL,
  `col1` varchar(50), // type et valeur par defaut a adapter
  `col2` int,
   PRIMARY KEY(my_id)
);
 ```
 
 Rajouter une colonne
  
 ```
ALTER TABLE table1
 ADD col3 type_donnees
 ```
 
 Rajouter contrainte de clef étrangère
  
 ```
 ALTER TABLE `table1`
  ADD CONSTRAINT `table1_FK_table2` FOREIGN KEY (`table2_id`) REFERENCES `table2` (`id`);
 ```

> Note : Une colonne dédiée à la clef étrangère dans la table doit avoir été créée au préalable pour appliquer la contrainte ex : table1 contient une colonne table2_id. 

> Attention: la colonne dédiée à la clef étrangère à créér doit avoir **exactement** les mêmes contraintes de structure que celle de l'id à laquelle elle fait référence (meme type, longueur, unsigned /signed ...)

</details>

