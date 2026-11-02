
![[Pasted image 20261030103546.png]]

ال Git بي store ال Data من خلال انه يجمع ال Data دي كلها تحت ال Commit object و اللي بيبقي تحتها ال parent اللي قبل ال Commit دا و ال Tree و اللي شايله ال SHA-1 hash لل blobs 

-----
## The Master Branch :

![[Pasted image 20261030110150.png]]

مجموعة ال Commits اللي بتشاور علي بعضها دي بيبقي اسمها Branch 

, و اول branch بيبقي اسمها ال ==🟡MASTER== 

, و برة ال Branches و ال Commits بيبقي في Pointer من برة بيشاور علي ال Branch , و اخر Commit في ال Branch دا by default--- [ و علي حسب طبعا لاني اقدر اوجهه علي اي Commit غير اخر واحد ] 

---
## Creating new branch :

![[Pasted image 20261030110238.png]]

طب لو انا عملت Create g ل Branch جديد 
ال Branch دا هلاقيه بيشاور علي ال Commit اللي بيشاور عليه حاليا ال Head 

, و لو انا عملت تعديل علي ال Commit دا هيبقي ال initial commit  او ال Parent اللي هيبدأ من عندها أي Commit جديدة [ في ال Branch الجديد طبعا ]

----
## The first commit in the new branch :

![[Pasted image 20261030110111.png]]

==🟢ال Master دا واقف علي اخر Commit كان عليها==

-------

لو انا عاوز ==🔴اعمل Branch== جديد : 

```bash
git branch branch_name                Create branch
```

لو عاوز ==🔴اشوف ايه ال branches== اللي عندي : 

```bash 
git branch                            Show Branches
```


لما الامر دا بيتنفذ بيبان النتيجة زي كدا : 

![[Pasted image 20261030112156.png]]

- الأخضر دا معناه ال [ Current branch ] يعني اي Commit او تعديل هيبقي في ال Branch دا 
- النجمة دي معناها ال HEAD واقف علي ايه.

![[Pasted image 20261030112405.png]]

و النتيجة دي معناها ان ال Master , Testing [ 2 branches ] واقفين علي نفس ال Commit و اللي عليه ال Head طبعا 


انقل ل Branch تاني : 

```bash 
git switch testing                      Switch Branches
```

, و بعد ما عملنا ال Switch
اي تعديل هيبقي في ال Testing branch. 


, و الامر اللي بيعرفنا بشكل غير مباشر احنا علي انهي branch : 

```bash
git status

git log
```



