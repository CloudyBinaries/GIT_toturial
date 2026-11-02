
#### ==🔴Deleting Git== :
لو انا حبيت امسح ال ==🔴Repo== : 

```bash 
rm -rf .git/
```

---

#### ==🟢Un-tracking / un-modify / un-staging== : 

- لو انا عملت ADD لل File او [ Indexing ] : 

![[Pasted image 20261030071000.png]]

, عاوز ارجع في Add دي فا خليته [ Tracked ]
, و عاوز ارجعه ل  [ Untracked ] : 

```bash 
git rm --cached file.txt   --- I can add more than 1 file 
```

![[Pasted image 20261030071208.png]]


- لو انا بقي عمل modification لل file [ indexing ]
, و عاوز ارجع لحالة ال File نسخته قبل ما تتعدل [ الحركة دي بتشيل التعديلات و تخليه علي النسخة الحالة اللي في ال staging area ]  :

![[Pasted image 20261030072032.png]]

```bash 
git restore file.txt   --- I can add more than 1 file 
```


- دلوقتي لو انا اصلا عملت ال Staging خلاص و فاضل ال Commit 
  بس انا غلط و عاوز ارجع في الحركة بتاعت ال Staging دي بس من غير ما يرجع التعديل دا في ال Working tree تاني زي اللي فاتت 
  انا هنا بخلي ال [ Staging area = Repo ] 
  يعني بعد ما تكون كدا : 

![[Pasted image 20261030072705.png]]

بستخدم : 

```bash 
git restore --staged file.txt   --- I can add more than 1 file 
```
  

-------

#### ==🟡Changing Commit Message== : 

```bash 
git commit --amed  
```

, و بعديها لو  انت مضبط انه يفتحلح حته ان ال Comment يتفتح علي ال Text Editor زي ال Vscode , Vim هيفتحهولك هناك

-------

#### ==🔵HEAD Reset== : 

![[Pasted image 20261030073821.png]]

الاول ال HEAD عبارة عن ال Pointer شايل ال SHA-1 بتاعت اخر Commit تعملت By default الا انا حبيت اغير في ال Commit او ال Version  اللي هيشاور عليها و ==🟢كمان بيشاور علي ال Branch بس دي نقطة هنتطرق ليها بعدين==.


- ال HEAD عبارة عن ملف فيه ال SHA-1 hash لل HEAD commit : 

![[Pasted image 20261030075223.png]]


-  ==🔴بس خلينا نعرف ان التغيير في ال Head دي حاجة خطيرة و ممكن تأثر علي ال Live Production و انها كمان بشكل مباشر في ال Version اللي انت شايفه حاليا في ال Working Tree لان اللي اللي ال HEAD بيشاور عليه هو اللي موجود حاليا في ال Working Tree==
==🔴فيجب التعامل مع الأمر دا بحظر== 
لو انا عاوز اعدل ال Reset لل Head : 

```bash 
git reset HEAD~1   ---> [ HEAD~(index of how far is the previous version that I want to Point to) ]
```

==🟡بس ال Best practice هو اني اعمل معملش ال HEAD Reset علطول== 
==🟡انا بخليه يرجع ال Index و اشوف ال DIFF بين ال Working Tree , Staging Area== 

لو انا عاوز اعدل في ال Working Tree بشكل مباشر : 

```bash 
git reset --hard HEAD~1  -- الرقم دا هو عدد الخطوات اللي هرجعها
```



- نلاحظ انه قبل التعديل لقينا انه  عدد ال Commits مظبوط زي ما احنا عملنا : 

![[Pasted image 20261030075023.png]]

بس بعد التعديل لقينا انهو اللي بالمناسبه اسمه Fast Forward : 

![[Pasted image 20261030075619.png]]

هنلاقي انه 3 Commits بس 
هل معني كده انه مسح اخر commit و لا ايه ؟ 

لا هي دي طبيعه ال Data Structure اللي بتعتمد عليها ال GIT و اللي هي ال Linked List 
انه مخلي ال Pointer اللي بيشاول علي ال Tail بتاعت ال Linked list و اللي بتبان عندك في ال Logs بشاور علي ال Commit اللي انت حددته  ---  الفكرة هنا ال commit الاخير متمسحش و ال Objects بتاعته لسه موجوده في ال Repo عادي 

االفكرة ان احنا مشوفتهاش لانه اللي احنا عملناه دا في حد ذاتع operation بس مش Object 
يعني احنا مش هنشوفه بال log العادي 
لا احنا هنشوفه بال reflog يعني ال log  بتاع ال References  اللي ال SHA و التغير فيها 
و لو عاوز اشوف ال commit القديم دا من تاني هلاقيه هنا : 

```bash 
git reflog
```

![[Pasted image 20261030080056.png]]

لو انا من هنا لقيت اني ندمت و عاوز ارجع لل Commit اللي كنت عليها في الاول خالص  : 

```bash 
git reset --hard HEAD@{1}

---> [ HEAD@{index of how far is the previous version that I want to Point to} ]
```

------

### Extra : 

![[Pasted image 20261030080748.png]]

![[Pasted image 20261030080907.png]]

