# Introduction à la Bioinformatique - Session 2

---

### Exercice 1 : Impact des mutations ponctuelles sur les séquences ADN et protéique

Cet exercice vous aidera à comprendre comment les mutations ponctuelles (substitutions, insertions et délétions) modifient les séquences génétiques et perturbent leur traduction en protéines.


#### A. Considérez la séquence suivante (brin codant), à quoi correspond le brin d'ADN complémentaire (brin matrice) ?

```
ATG CGG GAA CTT TAA
```
   
Rappel :
* L'adénine (**A**) s’apparie à la thymine (**T**).
* La thymine (**T**) à l'adénine (**A**).
* La guanine (**G**) à la cytosine (**C**).
* La cytosine (**C**) à la guanine (**G**).

<details> <summary>Solution</summary>

Brin matrice : `TAC GCC CTT GAA ATT`

</details>

#### B. À quoi correspond un ARN transcrit à partir de cette séquence ?

Rappel : L'ARN est transcrit à partir du brin matrice, mais il est identique au brin codant à l’exception de la thymine (**T**) qui est remplacée par l'uracile (**U**).

<details> <summary>Solution</summary>

Transcription : `AUG CGG GAA CUU UAA`

</details>

#### C. À quelle séquence d'acides aminés correspond cette séquence une fois traduite ?

Référez-vous au tableau ci-dessous pour trouver la correspondance entre codons ARN et acides aminés (il ne vous sera pas demandé de mémoriser ce tableau).

<img src="https://github.com/user-attachments/assets/8e82fa1b-6542-4617-992b-a2bda738d691" width=50% height=50%>\

<details> <summary>Solution</summary>

Séquence d’acides aminés : `Met (Méthionine) - Arg (Arginine) - Glu (Acide glutamique) - Leu (Leucine) - Stop`

</details>

1. **Insertion d'une base** :
- Imaginez qu'une insertion d’une base (A) survienne après le premier codon `ATG`.

```
ATG *A* CGG GAA CTT TAA
```
   
#### D. Traduisez cette nouvelle séquence en acides aminés. Comment la séquence traduite est-elle affectée ?

<details> <summary>Solution</summary>

Avec l'insertion, la séquence devient `ATG ACG GGA ACT TTA A`, ce qui, une fois transcrit en ARN, correspond à la séquence d'acides aminés suivant : `Met (Méthionine) - Thr (Thréonine) - Gly (Glycine) - Thr (Thréonine) - Leu (Leucine)`

L'insertion crée un décalage du cadre de lecture qui pourrait entraîner une perte de fonctionnalité de la protéine.

</details>

#### E. Comment appelle-t-on une mutation qui affecte la séquence protéique de cette manière ?

<details> <summary>Solution</summary>

L'insertion cause ici une mutation **faux-sens** car elle n'interrompt pas la séquence, mais entraîne une succession de codons qui codent pour des acides aminés différents.

</details>

2. **Substitution d'un nuclétoide** :
- Imaginez maintenant qu'une substitution d'nuclétoide (A → G) ait lieu dans le codon `TAA`.
- La séquence devient alors :
   
```
ATG CGG GAA CTT TGA
```

#### F. Traduisez cette nouvelle séquence en acides aminés. Comment la séquence traduite est-elle affectée ?

<details> <summary>Solution</summary>

Avec la substitution, la séquence devient `ATG CGG GAA CTT TGA`, ce qui, une fois transcrit en ARN, correspond à la séquence d'acides aminés suivant : `Met (Méthionine) - Arg (Arginine) - Glu (Acide glutamique) - Leu (Leucine) - Stop`.

Le résultat est similaire à la séquence originale, car le codon de terminaison (TAA) est remplacé par un autre codon stop (TGA), ne modifiant pas la fin de la protéine.

</details>

#### G. Comment appelle-t-on une mutation qui affecte la séquence protéique de cette manière ?

<details> <summary>Solution</summary>

L'insertion cause ici une mutation **silencieuse** car elle ne change pas la séquence d'acides aminés produite.

</details>

---

### Exercice 2 : Aligner 2 séquences ADN

Après avoir utilisé l'outil BLAST pour identifier une séquence ADN inconnue et la base de données NCBI pour télécharger une séquence ADN d'intérêt, nous allons maintenant voir comment comparer deux séquences avec l'outil BLAST.

1. Téléchargez les fichiers “BRCA1.fna”, "BRCA2.fna" et "HOXA10.fna".
   
2. Accédez au site BLAST : https://blast.ncbi.nlm.nih.gov/Blast.cgi

3. Assurez-vous que l'option **Align two or more sequences** soit bien cochée.

<img width="1419" alt="Screenshot 2024-10-19 at 15 02 28" src="https://github.com/user-attachments/assets/5568bb01-06ed-472d-ae22-ef5792a0de70">

<br></br>

4. Comparez les gènes BRCA1 et BRCA2. Pour ce faire, copiez/collez l'intégralité des séquences OU sélectionnez l'option **upload file** pour directement les téléverser.

<img width="1427" alt="Screenshot 2024-10-19 at 14 58 28" src="https://github.com/user-attachments/assets/38be81d6-445c-4e80-a514-7d424b6631e7">

5. Cliquez sur le bouton **BLAST** en bas de la page.

<img width="111" alt="Screenshot 2024-10-19 at 15 07 07" src="https://github.com/user-attachments/assets/89ff0454-bc6e-4626-887b-35fc155c2f2a">

6. Explorez les résultats.

#### A. Question sur les résultats

7. Comparaison de BRCA1 et HOXA10

#### B. Quel est le résultat obtenu ?

<details> <summary>Solution</summary>
  
La page de résultat indique qu'aucun résultat significatif n'a pu être determiné, ce qui signifie que les séquences sont trop différentes. Cela veut dire que BRCA1 et HOXA10 sont des gènes dont les fonctions et de structures sont très différentes.

</details>

#### C. Comment peut-on interpréter ce résultat sur la similarité fonctionelle et structurelle de BRCA1 et HOXA10 ?

<details> <summary>Solution</summary>
   
L'absence d'alignement significatif suggère que BRCA1 et HOXA10 ne partagent pas de similarités de séquence importantes et qu'ils ont ainsi problablement des fonctions très différentes.

</details>

8. Répétez le processus mais en changeant l'option d'alignement pour **More dissimilar sequences**, la deuxième option.

<img width="906" alt="Screenshot 2024-10-19 at 15 30 09" src="https://github.com/user-attachments/assets/a789ef76-eebb-45e7-ab54-2db88bc829a8">



#### C. ...

<details> <summary>Indice</summary>
...
</details>

<details> <summary>Solution</summary>
  
```bash
...
```

#### A. Que peut signifier l'ajout ou la perte de bases dans un gène en termes de fonction protéique ?

<details> <summary>Solution</summary> Les insertions ou délétions d'un nombre de bases qui ne sont pas des multiples de trois provoquent des décalages du cadre de lecture (frameshifts), ce qui peut mener à des protéines tronquées ou mal repliées, voire non fonctionnelles. </details>

</details>

#### B. Pourquoi un décalage du cadre de lecture est-il souvent plus problématique qu'une mutation ponctuelle ?

<details> <summary>Solution</summary> Un frameshift modifie toute la séquence d'acides aminés en aval de l'indel, tandis qu'une mutation ponctuelle ne change qu'un seul acide aminé, rendant les frameshifts potentiellement bien plus délétères. </details>

---

