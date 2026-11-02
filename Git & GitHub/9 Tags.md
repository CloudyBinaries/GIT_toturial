
احنا لما بنيجي نعمل ال Commit و و بنقول عليها Version فهو لمجرد التسهيل مش اكتر انما 
احنا مجرد بتعمل تعديلات و سطور الكود مش اكتر 
يعني مش Version من ال Project فعلا 

لغااااااااية ما بتيجي عند Commit معين بيحقق شروط ايا كان ايه هي تقدر تقول عليه هو دا فعلا Version جديد 

من خلال امر دا بعد م اعمل ال Commit اللي هتبقي هي دي ال Version الجديدة  : 

```bash
git tag -a v2.0 -m "the second version of the project"
```


و بشوف ال Version فعلا من خلال امر : 

```bash 
git show v2.0 --- the name of the version 
```


![[Pasted image 20261030081757.png]]

و زي ما هو باين في الصورة 

هو هنا حاطط هي Tag ل Version كام 
, و مين اللي عمل ال Tagging دا و اللي بيبقي اسمه ال ==🟠Tagger== 