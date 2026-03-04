## Description

Ce TP pratique vous permet de maîtriser les techniques d'optimisation des performances dans les applications Java utilisant JPA/Hibernate, en vous concentrant sur le **cache de second niveau** et la résolution du **problème N+1**.

##  Objectifs du TP

-  Comprendre et activer le cache de second niveau dans Hibernate
-  Mesurer les performances avant et après l'activation du cache
-  Identifier et résoudre les problèmes de requêtes N+1
-  Utiliser JOIN FETCH et les entity graphs pour optimiser le chargement des relations
-  Configurer EhCache comme provider de cache
-  Comprendre l'impact des différentes optimisations sur les performances

##  Prérequis

- Java 11 ou supérieur
- Maven 
- JPA/Hibernate


 ## Concepts Clés
       Problème N+1
Le problème N+1 se produit lorsque :
Une requête récupère N entités parentes
Pour chaque entité, une requête supplémentaire est exécutée pour charger les relations
Résultat : 1 + N requêtes SQL
      Solutions :
Utiliser JOIN FETCH dans les requêtes JPQL
Utiliser @EntityGraph
Configurer le fetch strategy approprié

<img width="876" height="695" alt="image" src="https://github.com/user-attachments/assets/92c077a1-53d9-424e-ba2a-e044a4e3bd02" />
<img width="1140" height="854" alt="image" src="https://github.com/user-attachments/assets/6ae36a3d-2790-4ddf-b1cb-71823551989d" />
<img width="1211" height="861" alt="image" src="https://github.com/user-attachments/assets/f0350844-a89e-4c2f-bd65-5e018c7fcd66" />
<img width="1119" height="730" alt="image" src="https://github.com/user-attachments/assets/31d14dac-adcb-4148-9800-69901c057b6e" />
<img width="1185" height="697" alt="image" src="https://github.com/user-attachments/assets/ddee5981-95b9-4197-a1c1-3023c57a53bc" />
<img width="1248" height="681" alt="image" src="https://github.com/user-attachments/assets/c014c089-ca79-4dcb-bb48-be934f2c1ee7" />
<img width="1244" height="687" alt="image" src="https://github.com/user-attachments/assets/b67d15de-fca4-477b-a584-428b3c004766" />
<img width="1209" height="696" alt="image" src="https://github.com/user-attachments/assets/5d696b90-15df-4396-877e-7c17a0fd7825" />

> Test 1 : Problème N+1
<img width="1498" height="750" alt="image" src="https://github.com/user-attachments/assets/0d1e4c65-f2db-48c7-8699-0a11adc70eca" />
<img width="1157" height="531" alt="image" src="https://github.com/user-attachments/assets/308fa7b9-83ca-4ef8-be0d-c29c076ca9c0" />
<img width="1390" height="527" alt="image" src="https://github.com/user-attachments/assets/adbfca22-a88e-4233-a1a1-12b813232575" />
<img width="1428" height="531" alt="image" src="https://github.com/user-attachments/assets/a877b465-88fe-417a-a1cb-c9bc93298d69" />
<img width="1352" height="534" alt="image" src="https://github.com/user-attachments/assets/05e50ffa-29e0-41b1-b7f9-13fd144aafbf" />
<img width="1240" height="540" alt="image" src="https://github.com/user-attachments/assets/5ac4f9e8-4ea5-4214-bc8c-4389cdfa07e3" />
<img width="1200" height="527" alt="image" src="https://github.com/user-attachments/assets/00df60af-4626-4271-9aab-4a6f5b2ae2f1" />
<img width="1300" height="528" alt="image" src="https://github.com/user-attachments/assets/51d6de0c-b03a-4797-bf4c-04e51d3bd968" />
<img width="1394" height="524" alt="image" src="https://github.com/user-attachments/assets/2b6375f8-15e8-4a4f-b80d-665448a3f2f1" />
<img width="1283" height="526" alt="image" src="https://github.com/user-attachments/assets/bd76e568-f907-4885-be74-8a60a741ae64" />
<img width="1244" height="526" alt="image" src="https://github.com/user-attachments/assets/f4342690-ef52-4e97-8557-8793ddf982cd" />
<img width="1362" height="785" alt="image" src="https://github.com/user-attachments/assets/90ea1a62-d100-40c8-aea1-e03522c45b97" />
<img width="1623" height="824" alt="image" src="https://github.com/user-attachments/assets/ce827046-6396-4af1-bd92-6f4c17a79d79" />

> Test 2 :JOIN FETCH
<img width="1596" height="815" alt="image" src="https://github.com/user-attachments/assets/88aaa6b9-f5e0-4493-9007-c353f25c1d10" />
<img width="1132" height="725" alt="image" src="https://github.com/user-attachments/assets/ca0a8ee3-ad84-4f1f-b851-361139c57608" />
<img width="1102" height="522" alt="image" src="https://github.com/user-attachments/assets/01356525-d9b2-40b5-99bb-6fcc06b8d9e6" />
<img width="1175" height="589" alt="image" src="https://github.com/user-attachments/assets/3197ec5c-f0b1-445f-b977-5444b2828a1a" />
<img width="1211" height="529" alt="image" src="https://github.com/user-attachments/assets/adc11837-1871-45e0-996f-0d8e3a744a50" />
<img width="1216" height="593" alt="image" src="https://github.com/user-attachments/assets/8f891562-c3b0-4bb0-9568-ec11799c0ddb" />
<img width="1094" height="525" alt="image" src="https://github.com/user-attachments/assets/be434c51-e435-4a6b-b84d-c82b2eb53c28" />
<img width="1210" height="590" alt="image" src="https://github.com/user-attachments/assets/9eaf8a93-e17e-47cc-ad88-bddb485c3213" />
<img width="1245" height="689" alt="image" src="https://github.com/user-attachments/assets/ad49db36-9db1-4ce4-a499-30ed72f16ddc" />
<img width="1380" height="763" alt="image" src="https://github.com/user-attachments/assets/b2b98408-7dea-4cc3-8341-1fe8f42f57c9" />

> Test 3 : Entity graphs
<img width="1548" height="875" alt="image" src="https://github.com/user-attachments/assets/9be64148-7af8-4b0a-a23d-2a79e7c9f3e3" />
<img width="1362" height="595" alt="image" src="https://github.com/user-attachments/assets/a495a341-eb17-48a6-9d55-671bc6d6a915" />
<img width="1130" height="795" alt="image" src="https://github.com/user-attachments/assets/aedcf4ff-0f8e-4d7d-8a37-4d3dfc16ce30" />
<img width="1181" height="878" alt="image" src="https://github.com/user-attachments/assets/3006c5ab-5a04-40ca-bcb7-6bbc1ab03a28" />
<img width="1192" height="880" alt="image" src="https://github.com/user-attachments/assets/c5b878e8-c847-4bc1-8812-afa085ae9967" />
<img width="1445" height="882" alt="image" src="https://github.com/user-attachments/assets/892ff3c2-37ba-43e3-979c-1c1fbcafbfe7" />
<img width="1084" height="293" alt="image" src="https://github.com/user-attachments/assets/70e57598-d8a0-4a4a-938a-22bda826ca23" />

> Test 4 : Avec cache
<img width="1247" height="687" alt="image" src="https://github.com/user-attachments/assets/42aa667e-9d9b-4c9c-8b8d-2b7852d49713" />
<img width="677" height="691" alt="image" src="https://github.com/user-attachments/assets/93b04ef7-6bc4-4e5a-ae8f-a520570518d1" />
<img width="1459" height="820" alt="image" src="https://github.com/user-attachments/assets/97df13c3-1e0c-4ac5-9ca6-c24f250f65f7" />
<img width="1063" height="596" alt="image" src="https://github.com/user-attachments/assets/b840e322-0e03-4823-8266-25d669c7b0ee" />
<img width="1504" height="712" alt="image" src="https://github.com/user-attachments/assets/3f699686-0789-4ecc-a011-534e109388e8" />
<img width="1366" height="425" alt="image" src="https://github.com/user-attachments/assets/ac0f3926-567c-4efd-b208-f1670e139184" />

> Test 5 : Comparaison des performances
> Sans cache :
<img width="1464" height="888" alt="image" src="https://github.com/user-attachments/assets/ed76ef35-728b-4a52-9b3e-82932a0b6571" />
<img width="1370" height="857" alt="image" src="https://github.com/user-attachments/assets/2744a23a-72b0-48d2-9666-f642728c05af" />

> Avec cache :
<img width="1459" height="851" alt="image" src="https://github.com/user-attachments/assets/1714d9f5-f596-4cc9-93f2-82c62da116ad" />
<img width="1436" height="842" alt="image" src="https://github.com/user-attachments/assets/a4404890-2437-4e79-812c-c4f8f6972573" />
<img width="1452" height="700" alt="image" src="https://github.com/user-attachments/assets/b69ebe04-cda1-4585-bf2b-adce446f3635" />

























