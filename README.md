# MyFirstHadoopProject

Les champs du fichier log à traiter sont séparés par des tabulations et ont la forme suivante:
* date   temps	magasin   produit   coût	paiement

Activité
Le but de cette activite est de déterminer le total des ventes par magasin pour cela on développe :
* un Mapper afin d'extraire les couples (magasin,coût) 
* Un Reducer pour calculer le total des ventes pour chaque magasin  


# Test

##Tester en local 

1. Créer un répertoire input sous le répertoire ressources de notre projet sous lequel on a importé le fichier texte purchases.txt

2. Dans l'onglet Arguments de la fenetre Run configuration spécifier les arguments (le fichier log et le repertoire du résultat) à utiliser lors de l'execution     

3. Aprés l'execution du programme le resultat sera stocké dans le fichier part-r-00000 sous le répertoire du résultat



##Tester sur HDFS 

1. Exporter le jar du projet JAVA 

2. Créer un répertoire pour stocker le fichier des données : hadoop fs -mkdir /input

3. Mettre le fichier en entrée sous le répertoire crée sur HDFS : hadoop fs –put [fichier des données] /input

hadoop fs -put purchases.txt input/

4. Executer la commande suivante: hadoop jar [jar du projet] [Nom du point d'entrée main dans le jar] [fichier des données] [répertoire du résultat]
hadoop jar File.jarislaib.mds.myapplication.TotalSales input output

5. Visualiser le résulat dans le ficher part-r-00000 sous le répertoire du résultat
hadoop fs -cat output/part-r-00000
