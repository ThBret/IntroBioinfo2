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

---

#### B. À quoi correspond un ARN transcrit à partir de cette séquence ?

Rappel : L'ARN est transcrit à partir du brin matrice, mais il est identique au brin codant à l’exception de la thymine (**T**) qui est remplacée par l'uracile (**U**).

<details> <summary>Solution</summary>

Transcription : `AUG CGG GAA CUU UAA`

</details>

---

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

---
   
#### D. Traduisez cette nouvelle séquence en acides aminés. Comment la séquence traduite est-elle affectée ?

<details> <summary>Solution</summary>

Avec l'insertion, la séquence devient `ATG ACG GGA ACT TTA A`, ce qui, une fois transcrit en ARN, correspond à la séquence d'acides aminés suivant : `Met (Méthionine) - Thr (Thréonine) - Gly (Glycine) - Thr (Thréonine) - Leu (Leucine)`

L'insertion crée un décalage du cadre de lecture qui pourrait entraîner une perte de fonctionnalité de la protéine.

</details>

---

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

---

#### F. Traduisez cette nouvelle séquence en acides aminés. Comment la séquence traduite est-elle affectée ?

<details> <summary>Solution</summary>

Avec la substitution, la séquence devient `ATG CGG GAA CTT TGA`, ce qui, une fois transcrit en ARN, correspond à la séquence d'acides aminés suivant : `Met (Méthionine) - Arg (Arginine) - Glu (Acide glutamique) - Leu (Leucine) - Stop`.

Le résultat est similaire à la séquence originale, car le codon de terminaison (TAA) est remplacé par un autre codon stop (TGA), ne modifiant pas la fin de la protéine.

</details>

---

#### G. Comment appelle-t-on une mutation qui affecte la séquence protéique de cette manière ?

<details> <summary>Solution</summary>

L'insertion cause ici une mutation **silencieuse** car elle ne change pas la séquence d'acides aminés produite.

</details>

---

<br></br>

### Exercice 2 : Alignement de séquences et distances de Hamming et Levenshtein

Cet exercice vous aidera à comprendre comment les distances de Hamming et de Levenshtein mesurent les différences entre deux séquences génétiques.

#### A. Considérez les deux séquences d'ADN suivantes. Calculez la distance de Hamming entre les deux séquences.

```
Séquence 1 : ATG CGG GAA CTT TAA
Séquence 2 : ATG CGA GGA CTT TGA
```

Rappel : La distance de Hamming est le nombre de positions où les nucléotides sont différents entre deux séquences de même longueur (elle est uniquement utilisée lorsque les séquences sont de la même longueur).

<details><summary>Solution</summary>
   
Distance de Hamming : 3
Différences aux positions : 5 (G ↔ A), 8 (A ↔ G), et 14 (A ↔ G)

</details>

---

#### B. Supposons que la séquence 2 soit modifiée de la manière suivante, en ajoutant une base A après le premier codon ATG. Calculez la distance de Levenshtein entre les séquences.

Rappel : La distance de Levenshtein entre deux séquences est le nombre minimal d'opérations nécessaires pour transformer une séquence en une autre. Les opérations autorisées sont les insertions, les délétions et les substitutions. Contrairement à la distance de Hamming, la distance de Levenshtein peut être utilisée pour des séquences de longueurs différentes.

```
Séquence 1 :            ATG   CGG GAA CTT TAA
Séquence 2 (modifiée) : ATG A CGA GGA CTT TGA
```

<details><summary>Solution</summary>
   
**Distance de Levenshtein** : 4
Explication : Une insertion (A) après le premier codon ATG, et trois substitutions aux positions restantes.

</details>

---

#### C. Supposons que les séquences ci-dessus correspondent à des gènes codant pour des protéines. Une mutation par insertion est-elle plus susceptible de modifier la fonction de la protéine qu'une substitution ponctuelle ?

<details><summary>Solution</summary>
Les substitutions ponctuelles modifient généralement un seul acide aminé, ce qui peut affecter la fonction de la protéine ou être silencieux. Cependant, une insertion provoque un décalage du cadre de lecture, altérant potentiellement tous les acides aminés en aval, ce qui est plus susceptible de rendre la protéine non fonctionnelle.

</details>

---

<br></br>

### Exercice 3 : Aligner 2 séquences ADN

Après avoir utilisé l'outil BLAST pour identifier une séquence ADN inconnue et la base de données NCBI pour télécharger une séquence ADN d'intérêt, nous allons maintenant voir comment comparer deux séquences avec l'outil BLAST.

1. Téléchargez les fichiers “brca1.fna”, "brca2.fna", "hoxa2.fna" "hoxa10.fna".
   
2. Accédez au site BLAST : https://blast.ncbi.nlm.nih.gov/Blast.cgi

3. Assurez-vous que l'option **Align two or more sequences** soit bien cochée.

<img width="1419" alt="Screenshot 2024-10-19 at 15 02 28" src="https://github.com/user-attachments/assets/5568bb01-06ed-472d-ae22-ef5792a0de70">

4. Alignez les gènes _BRCA1_ et _BRCA2_. Pour ce faire, copiez/collez l'intégralité des séquences OU sélectionnez l'option **upload file** pour directement les téléverser.

<img width="1427" alt="Screenshot 2024-10-19 at 14 58 28" src="https://github.com/user-attachments/assets/38be81d6-445c-4e80-a514-7d424b6631e7">

5. Cliquez sur le bouton **BLAST** en bas de la page.

<img width="111" alt="Screenshot 2024-10-19 at 15 07 07" src="https://github.com/user-attachments/assets/89ff0454-bc6e-4626-887b-35fc155c2f2a">

6. Prenez un moment pour explorer la page des résultats.

#### A. Quelle est la longueur de l'alignement ? Score ?

<details> <summary>Solution</summary>
  
L'alignement est composé de 170 381 caractères, ce qui est plus long que 

</details>

7. Alignez maintenant les gènes _HOXA2_ et _HOXA10_

---

#### B. Quel est le résultat obtenu ?

<details> <summary>Solution</summary>
  
La page de résultat indique qu'aucun résultat significatif n'a pu être déterminé, ce qui signifie que les séquences sont trop différentes l'une de l'autre.

</details>

8. Jusqu'à là, nous avons seulement utilisé l'algorithme par défaut (*megablast*), qui sert à comparer des séquences très similaires. Essayez maintenant de comparer les gènes _HOXA2_ et _HOXA10_ avec l'algorithme *blastn*.

<img width="766" alt="Screenshot 2024-11-03 at 13 17 28" src="https://github.com/user-attachments/assets/311a3348-bd4e-487a-a03f-b650bfe26792">

---

#### C. Quel est le résultat maintenant obtenu ?

<details> <summary>Solution</summary>
  
Cette fois-ci, on obtient bien un alignement des deux séquences, ce qui indique que bien qu'elles correspondent à deux gènes d'une même famille, ces gènes sont loin d'être identiques au niveau de leur séquence.

</details>


9. Essayez d'aligner les gènes _BRCA1_ et _HOXA10_ avec l'algorithme d'alignement de votre choix.

---

#### D. Quel est le résultat obtenu ici ?

<details> <summary>Solution</summary>
  
Quel que soit l'algorithme d'alignement choisi, il sera impossible de former un alignement entre ces deux séquences.

</details>

---

#### E. Comment peut-on interpréter ce résultat sur la similarité fonctionnelle et évolutive de BRCA1 et HOXA10 ?

<details> <summary>Solution</summary>

L'absence d'alignement possible est le résultat de la différence trop grande des deux séquences. Cela indique que les gènes _BRCA1_ et _HOXA10_ ont probablement des fonctions très distinctes et des rapports évolutifs éloignés.

</details>
