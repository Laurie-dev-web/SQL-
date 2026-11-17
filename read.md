**Pour le Brief SQL - Intro et premières requêtes**

Je n'avais pas enregistrer mon travail quelques part, mais il est bien effectuer sur supabase.

Ma seul ligne de code enregistrer est un bout de l'exercice : MySQL 03 - Manipulation des données.

`select "birthDay" wizard where "birthDay" between "1975" and "1985";`

Il y a mon MCD fait sur excalidraw: je n'est pas capter encore la cardinalité donc je n'est pas reussit a le faire je sais juste que il y a un N/0 quelques part.

[Supabase](https://supabase.com/dashboard/project/kuycbfuartnvywqbttgd)

![image](MCD.png)

**MySQL 04.2 - Les bases de la modélisation : MLD**

Pour bien commencer j'ai du mieux comprendre le MCD (cardinalité)

1. Que ferais-tu dans ce cas ? Côté wizard ou côté pet ? -> je choisis l'une des deux tables pour y mettre ma clé étrangère.

2. Realisation du schéma MDL ![image](MDL.png)

**MySQL 04.3 - Les bases de la modélisation : MPD**

1. on créer les tables pour les entitées.

```
CREATE TABLE potion (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(40) NOT NULL,
);
CREATE TABLE ingredient(
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(40) NOT NULL,
);
```

2.  on créer la table pour la clé étrangère

```
CREATE TABLE etagere (
    ingredient_id INT NOT NULL,
    potion_id INT NOT NULL,

    CONSTRAINT fk_etagere,
        FOREIGN KEY (potion_id),
        REFERENCES potion(id),

    CONSTRAINT fk_etagere2,
        FOREIGN KEY (ingredient_id),
        REFERENCES ingredient(id),
);
```

PS: a partir de cette exercices j'ai mieux compris la cardinalité. Le liens de potion et de ingrediens sont tout deux (0,N) : la potion est utilisé a l'ingrédients 0 a N de fois et les ingrédients sont utilisé 0 a N de fois.
