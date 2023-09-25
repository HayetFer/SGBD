# Exercice 1:
## 1
fh201952=> CREATE TABLE IF NOT EXISTS Livre(


liv_num INT PRIMARY KEY NOT NULL,


liv_titre VARCHAR(50) NOT NULL,


liv_datePubli DATE);




CREATE TABLE
fh201952=> CREATE TABLE IF NOT EXISTS Auteur(

aut_id  SERIAL PRIMARY KEY NOT NULL,

aut_nom VARCHAR(50) NOT NULL,

 aut_prenom VARCHAR (50) NOT NULL);
 
CREATE TABLE IF NOT EXISTS Couverture(
liv_num INTEGER NOT NULL, FOREIGN KEY (liv_num) REFERENCES Livre(liv_num),
couv_taille INTEGER;
vis_fichier VARCHAR(50) PRIMARY KEY);
);

CREATE TABLE IF NOT EXISTS CouvAut(
vis_fichier VARCHAR(50),
    aut_id INT,
    PRIMARY KEY (vis_fichier, aut_id),
    FOREIGN KEY (vis_fichier) REFERENCES Couverture(vis_fichier),
    FOREIGN KEY (aut_id) REFERENCES Auteur(aut_id));
CREATE TABLE

# 2
--Requete de récup des livres 
INSERT INTO livre SELECT liv_num, liv_titre, NULL FROM lmsf;

--Requete de récup des Auteurs
INSERT INTO AUTEUR (aut_nom, aut_prenom) SELECT DISTINCT aut_nom, aut_prenom FROM lmsf UNION SELECT DISTINCT aut_nom2, aut_prenom2 FROM lmsf WHERE aut_prenom2 IS NOT NULL;

--Requete de récup des Couvertures
INSERT INTO couverture SELECT DISTINCT liv_num, couv_fichier FROM lmsf UNION SELECT distinct liv_num, couv_url2 FROM lmsf WHERE couv_url2 IS NOT NULL;

--Requete des CouvAut
INSERT into couvAut SELECT couv_fichier, aut_id FROM lmsf AS L INNER JOIN auteur AS A ON (L.aut_nom = A.aut_nom AND L.aut_prenom = A.aut_prenom) OR (L.aut_nom2 = A.aut_nom AND L.aut_prenom2 = A.aut_prenom) ;

INSERT into couvAut SELECT couv_url2, aut_id FROM lmsf AS L INNER JOIN auteur AS A ON (L.aut_nom = A.aut_nom AND L.aut_prenom = A.aut_prenom) OR (L.aut_nom2 = A.aut_nom AND L.aut_prenom2 = A.aut_prenom) WHERE couv_url2 IS NOT NULL 


