# Exercice 1:
## 1
fh201952=> CREATE TABLE IF NOT EXISTS Livre(
liv_num SERIAL PRIMARY KEY NOT NULL,
liv_titre VARCHAR(50) NOT NULL,
liv_datePubli DATE);

CREATE TABLE
fh201952=> CREATE TABLE IF NOT EXISTS Auteur(
aut_id  SERIAL PRIMARY KEY NOT NULL,
aut_nom VARCHAR(50) NOT NULL,
 aut_prenom VARCHAR (50) NOT NULL);

CREATE TABLE IF NOT EXISTS Couverture(
liv_num INTEGER NOT NULL, FOREIGN KEY (liv_num) REFERENCES Livre(liv_num),
vis_fichier VARCHAR(50) PRIMARY KEY);

CREATE TABLE IF NOT EXISTS CouvAut(
vis_fichier VARCHAR(50),
    aut_id INT,
    PRIMARY KEY (vis_fichier, aut_id),
    FOREIGN KEY (vis_fichier) REFERENCES Couverture(vis_fichier),
    FOREIGN KEY (aut_id) REFERENCES Auteur(aut_id));
CREATE TABLE
