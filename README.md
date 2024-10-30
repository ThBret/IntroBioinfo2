# Introduction à la Bioinformatique - Session 2

---

### Exercice 1 : Aligner 2 séquences ADN

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

#### B. ...


Pour un exercice qui se concentre exclusivement sur les effets des insertions et des délétions sans utiliser d'alignement ou de BLAST, voici une suggestion. Cet exercice va explorer comment les indels influencent la séquence ADN et la traduction en protéine, en particulier via les décalages du cadre de lecture.

---

### Exercice 3 : Impact des Insertions et Délétions sur la Traduction des Séquences ADN

Cet exercice vous aidera à comprendre comment les insertions et délétions modifient la séquence de bases d'un gène et perturbent la traduction en protéine.

#### Étapes

1. **Considérons la séquence suivante (exemple simplifié d’un fragment de gène)** :
   
   ```
   ATG GCA CTT GAA TGA
   ```
   
   Cette séquence se traduit en acides aminés en utilisant le code génétique. Traduisez-la pour obtenir la chaîne d'acides aminés correspondante.

   <details> <summary>Solution</summary>
   - Traduction : `ATG GCA CTT GAA TGA`
   - Codons d’acides aminés : Met - Ala - Leu - Glu - Stop
   </details>

2. **Insertion d'une base** :
   - Imaginez qu'une insertion d’une base (A) survienne après le premier codon `ATG`.
   - La nouvelle séquence devient :
   
     ```
     ATG *A* GCA CTT GAA TGA
     ```
   
   **Question :** Traduisez cette nouvelle séquence en acides aminés. Que se passe-t-il pour la séquence traduite ?

   <details> <summary>Solution</summary>
   Avec l'insertion, la séquence devient `ATG AGC ACT TGA ATG A`. La traduction change et pourrait entraîner une perte de fonctionnalité de la protéine à cause d’un décalage du cadre de lecture (frameshift).
   </details>

3. **Délétion d'une base** :
   - Imaginez maintenant qu'une délétion d’une base (C) ait lieu dans le codon `GCA`.
   - La séquence devient alors :
   
     ```
     ATG GAC TTG AAT GA
     ```
   
   **Question :** Traduisez cette séquence en acides aminés et décrivez l’impact sur la chaîne protéique.

   <details> <summary>Solution</summary>
   - La séquence devient `ATG GAC TTG AAT GA`, provoquant aussi un décalage du cadre de lecture.
   - Le résultat traduit est `Met - Asp - Leu - Asn`, avec potentiellement une protéine inactive ou tronquée.
   </details>

4. **Étude de plusieurs mutations** :
   - Insérez 3 bases supplémentaires après le premier codon `ATG` (exemple : ajout de `CGT`).
   - La nouvelle séquence devient :
   
     ```
     ATG *CGT* GCA CTT GAA TGA
     ```
   
   **Question :** Traduisez cette séquence et comparez-la avec les traductions précédentes. Est-ce que cette insertion provoque un frameshift ?

   <details> <summary>Solution</summary>
   - Traduction avec insertion de 3 bases : `Met - Arg - Ala - Leu - Glu - Stop`.
   - En ajoutant un multiple de trois bases, le cadre de lecture reste inchangé, permettant une traduction plus cohérente sans frameshift.
   </details>

---

#### Conclusion

- **Question finale :** Que se passe-t-il lorsqu’une insertion ou délétion n’est pas un multiple de trois par rapport à la protéine finale ?
   <details> <summary>Solution</summary>
   Les insertions ou délétions qui ne sont pas des multiples de trois provoquent un frameshift, entraînant une traduction complètement différente et une probabilité élevée de générer une protéine non fonctionnelle.
   </details>

---

Cet exercice permet aux étudiants de voir directement comment les indels affectent le cadre de lecture et la traduction d’une protéine, mettant en lumière les conséquences fonctionnelles de ces mutations.
