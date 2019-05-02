## Pour se connecter en LDC (dans le terminal)

Ou -u = utilisateur (root), -p = demande de password , musicdbquantum = la BDD presente dans mysql (a creer) , < = l'endroit ou je vais diriger mon script, musicdb.sql = contient les instructions a fournir a ma bdd selectionée

`mysql -u root -p musicdbquantum < musicdb.sql` 

update une table 

`UPDATE matable SET macolonne = mavaleur`

//creation d'une nouvelle contrainte
- j'ajoute une nouvelle colonne dediée a la clef etrangere dans ma table a la cardinalité 1,1 une album = 1 et 1 seul chanteur
- cette colonne doit etre : indexée & avoir exactement le meme type que l'id de la clef a lier
- attention prevoir une valeur par defaut existante dans la colonne ou autoriser du null si je souhaite appliquer ma contrainte sur la clef
