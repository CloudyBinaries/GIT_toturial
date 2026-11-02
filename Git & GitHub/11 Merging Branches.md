
اللي كنا بنعمله في ال Creating Branches اننا كنا مثلا عاوزين نلعب في حاجة في ال Code من غير ما يبقي في تأثير حقيقي ال Master و اللي غالبا هيبقي Production 

طب لو  انا اشتغلت علي Feature جديدة و عاوز ادخلها علي ال Master 

ساعتها احنا بنتكلم عن حاجة اسمها ال Branches merging : و هي اننا ندمج ال Branches سوا او بمعني اصح ان هتمد التعديلات اللي حصلت في ال MASTER و اللي بقت دلوقتي في ال testing و [ هخلي ال Master هو ال Commit اللي عليه ال HEAD في ال Testing --- حتي بيستميها في ال Output ال Fast-Forward ] -- و الشرح دا بشكل مؤقت 

![[Pasted image 20261031060341.png]]

و عشان اعمل كده 
بعمل الاول Switch ل Branch اللي عاوز اعمل فيه ال Merge  
و اكتب فيه امر ال Merge مع اسم ال Branch اللي عاوز اعمل معاه ال Merge 

```bash
git merge testing            ---   I am in [ swithced to ] master branch
```

------
## Merging into Divergent History
### Note :
### بفرض ان ال commits اللي هنعتمد عليها هي اخر Commit في كل Branch

![[Pasted image 20261031064132.png]]

الفكرة اننا لحد هنا كانا بنشرح ايه اللي بيحص ساعة لما بنكون بنوقف شغل في ال Master و بالتالي اخر Commit في ال Master , و اللي هي بتبقي اصلا ال Testing بتبقي بنت عليها ال Testing ال Commits او Versions الجديدة -- و انا اقصد هنا ان لو حبينا نعمل ال Merge هلاقي بس انه هيشوف ايه اللي جد في ال Testing و مش موجود في ال Master و هضيفه بس الجديد 

==🟡طب ايه اللي بيحصل ساعة لما يبقي في Versions و Commits جديدة عملناها في ال Master و حبيبنا نعمل Merging مع ال Testing --- و اللي بالمناسبه انه هنا ممكن الاقي حاجة زي انه عملت File جديد مش موجود في ال Testing اصلا او حالات اكتر من كده كمان== 

==🔴, و بالتالي مبقاش في مسار Linear ما بين ال Master , Testing زي قبل كده== 

![[Pasted image 20261031064328.png]]

![[Pasted image 20261031064403.png]]

![[Pasted image 20261031064428.png]]

![[Pasted image 20261031064823.png]]

و بعد ال Merging الوضع بقي عامل كدا : 

![[Pasted image 20261031064917.png]]


![[Pasted image 20261031062538.png]]


==🔴ساعتها هنلاقي ان GIT بتعمل Commit جديدة تماما و ال Commit دي بتشاور علي ال Testing , Master --- مش زي اللي فات كانت مجرد انها بتحرك ال HEAD بتاعت ال Master اخليه علي خر Commit في ال Testing== , و دا كله اسمه : [ Three Way Merge ] 


و بعد دا انا اقدر امسح ال Testing عادي جدا بأمر : 

```bash 
git branch -d testing
```

![[Pasted image 20261031065046.png]]


==🔵و احيانا في Case زي دي بيحصل Conflict لاننا عدلنا ال في نفس ال File من الاتنين Branches== 
==🔵و Git هنا بتقولي ان ال Lines دي موجوده في ال Master كدا و في ال Testing كدا و بتخيرك تعتمد انهي واحد فيهم.==

![[Pasted image 20261031065306.png]]
![[Pasted image 20261031065211.png]]

-----


لو عاوز اشوف ايه ال Branches اللي اتعملها Merge في ال Master : 

```bash 
git branch --merged
```

![[Pasted image 20261031063838.png]]

------
## Merge Rebase : 

في امر حاجة اسمها ال Rebase في Git اسمها Rebase و هي زي ال Merge بالظبط بس الزياده هنا انه بيجيلي الموضوع Linear تاني و كانك معملتش Branching قبل كدا --- [ مش هتبقي 3 Way Merge زي قبل كدا ]. 

يعني الموضوع مبيبقاش زي ما شوفنا لما كنت بنشوف ال Logs معمولها 

```bash 
git log --online --graph --concrate 
```

![[Pasted image 20261031065046.png]]


-----

