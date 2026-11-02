
اللي فات دا كله احنا كننا بتتكلم عن اننا نشتغل علي ال Local Repo و علي مستوي الجهاز بتاعنا بس 

طب ازاي نتعامل بقي مع ناس تاني في ال Project دا و علي Servers و Central Repo و repos و Version بتاعت ناس تانية. 

-----

![[Pasted image 20261031235938.png]]

في الصورة باين ان في Remote Repo فيه Versions و Commit و كل محتوياته , و انا عشان اسحبه عندي 
مش بعمل Download لأ , أنا بعمل حاجة اسمها Clone 
طب ايه الفرق ما بينهم : 

ال Download [ بتسحب نسخة من الProject او الملفات او ايا كان ايه هو  و بيتقطع الصلة بينك و بين ال Source اللي خدت منه الحاجة دي  ] 
اما ال Clone [ هو هنا بيسهل عمليه ال Tracking بينك و بين ال Remote Repo , و بيأثر في ال Status عندي -- و لما بتيجي تعمل ال Clone لاول مرة بيبقي عندك نسخة طبق الاصل من ال Repo و فيها نفس كل حاجة من ال Hashes , SHA-1 , Objects و كل حاجة حرفيا ] و مش شرط يبقي Live connection عشان تبدأ تشتغل علي ال Repo دا عندك 

و بعد كده انت بتعمل علي ال local Repo التعديلات اللي انت عاوزها و تشتغل زي ما انت عاوز -- و بعدك دخ ممكن تعمل : 
- ال Push علي ال Remote Repo بال UP Stream عشان تبعت التعديلات بتاعتك علي ال Repo
- او انك تعمل Pull او Fetch عشان تشوف التعديلات اللي تمت علي ال Repo دا من فترة لل تانية و بعدها تقرر انت هتعمل. 
و ممكن تعمل Connection علي اكتر من Remote مش شرط واحد بس و ممكن تعمل برضو زي ما تقلنا باختصار ال [ Push / Pull / Fetch ]


, و للتعامل مع ال Remotes لازم يبقي عندنا ال Hosting Service و اللي هي [ GitHub - GitLab ]

بس اللي جاي هيبقي في شوية منه اننا في Simulation اننا في عندنا Remote Repo بس دا كله هيبقي Local 

----

Cloning : 

```bash
git clone <address_of_repo--either Urls - File directory - IPs>
```

![[Pasted image 20261101014431.png]]

Specifying the name of clone : 

```bash 
git clone <address> name 
```

![[Pasted image 20261101014554.png]]

انا لو دخلت علي ال gitRemote و اللي خدناه بال cloning من جوا ال gitRemote الاصلي و كتبنا : 

```bash
git remote
```

![[Pasted image 20261101014943.png]]

هيجيبلك ال Origin و دا معناه ان ال Repo اللي عندي local دا متاخد من Remote repo 
و ال Origin دا ال Short name او بمعني اصح دا ال Alias name 
بس لو عاوز اعرف تفاصيل اكتر عنه اللي هو مثلا متاخد منين و كدا : 

```bash 
git remote -v 
```

![[Pasted image 20261101015259.png]]

, و هنا جايب ان ال Remote دا اقدر اعمل عليه حاجتين : [ Fetch - Push ] -- بس في العموم مش كل ال Remotes هتصرح او هتدعم كل ال Actions دي و علي حسب الصلاحيات طبعا 

--------

لو انا جيت و شوفت ال logs هلاقي : 

![[Pasted image 20261101015703.png]]

و دا جايب كل ال Commits اللي اتعملت كانت معموله علي ال gitRemote , و لو كنت عملت اكتر من commit هلاقيها ظاهرة هنا -- و دا بيظهر فيه انه مش مجرد زي ماقلت عملت download لا دا انا فيه جزء من ال tracking بتاعت ال Actions اللي حصلت علي ال Remote Repo 

----

![[Pasted image 20261101132805.png]]

بشوف ال Branches اللي عندي من خلال امر : 

```bash
git branch 

or 

git branch -r         ---> branches in remote
```

هنا قالي اني عندي branch واحد و اللي هو ال Master 
و ال HEAD بيشاور علي ال Master. 

-----

# Keeping up to date with remote : 

عشان اشوف بقي ال updates و التعديلات اللي اتعملت من ساعة اخر مرة عملت فيه pull او حتي Clone او  حتي Fetch نفسها لو هي امر مرة يعني فعندي طريقتين : 

الاولي اني اعمل Fetch : 

```bash
git fetch <remote_name- in this case it is origin>

---> git fetch origin
```

![[Pasted image 20261101133822.png]]

, و مع اني مع نفسي عملت 3 Commits في ال Remote repo و كل مرة كنت عمل فيها fetch كان بيجيبلي علي ال updates اتعملت بعد اخر fetch اللي انا عملتها حتي لو ال updates دي معملتش ليها merge 
يعني 
دي ال commits اللي عندي في ال remote repo : 

![[Pasted image 20261101135851.png]]

, و كنت بعد كل commit in remote بحاول اشوف ال updates من خلال ال fetch in local 
كنت ببقي متخيل اني هلاقي اني ال fetch هجيب ال updates من اول ال commit اللي انا عليها في ال local لغاية اخر حاجة اتعملت في ال remote [ و انا معمتلتش merge ليهم برضو ]
بس بلاقي انه بيجيب بال updates بس اللي حصلت و الجديدة عن ال fetch اللي قبله بس مش في العموم 

و طبعا ال : 

```bash 
git status 
```

==🟡بتجيب انا بعيد قد ايه عن ال Remote Repo== 
==🟡بس النتايج بتاعتها بتكون ادق بالنسبالي لو عملتها بعد ال fetch علطول== 

![[Pasted image 20261101140637.png]]

, و بعد دا طبعا انت لو عاوز تزود التعديلات عندك علي ال Local بتعمل بقي merge للتعديلات دي : 

```bash 
git merge 
```

![[Pasted image 20261101140937.png]]

### طب لو انا اللي عدلت علي ال Local Repo 

![[Pasted image 20261101141226.png]]

![[Pasted image 20261101141301.png]]

![[Pasted image 20261101141341.png]]

, و حتي في ال log : 

![[Pasted image 20261101141537.png]]

-----

# Dealing with branches in remote : 

احنا عندنا الكلام اللي قولناه فوق ممكن ميبقاش دا اللي المفروض يحصل في بيئة الشغل مع developers 
ليه ؟ 
لأن مش الطبيعي اني اعمل ال Push , Pull علي ال Master branch و ممكن يأثر علي باقي ال Developers اللي معايا و يبوظ حاجة في ال live production بشكل مباشر , 
فالحل هنا اني انا ابقي عندي ال Master branch عادي جدا بس و عامل من branch لل feature اللي انا شغال عليها 

في التطبيق العملي لما عملت ال Feature branch 
و عدلت و عملت ال commit ,  و شوفت بعد كده ال Status عشان اشوف انا من ايه بالنسبه لل Remote Repo -- لقيت : 

![[Pasted image 20261101155939.png]]

المفروض اني لما اعمل ال Status ال Git بيشوف الفرق بين ال , Local branch [ master ] و ال Remote branch ال Master برضو -- او بشكل عام انا بشوف الفرق بين ال local و ما يقابله في نفس ال branch علي ال remote 
المرادي مفيش حاجة بتقابل ال Feature Branch في ال Remote -- اللي موجود هناك هو ال master بس -- و مش شرط بس في حالة اني عاوز اعمل Status -- لو حبييت اعمل Push او Pull هيبقي منين لفين -- و حتي بلاحظ دا هنا : 

![[Pasted image 20261101160628.png]]


فانا بخليه يعمل ال create لل feature branch علي ال Remote Repo من خلال اني اكتب اسم ال Feature : 

```bash
git push -u origin feature   ----> -u is so important for tracking [ 1st push only ]

git push origin feature   -----> in the rest of pushes
```


![[Pasted image 20261102014209.png]]

حاليا هنلاقي في ال status انه عمل بقي جزء ال tracking من تاني : 

![[Pasted image 20261102014249.png]]



==🔴لو انا عاوز اعمل Push علي ال Remote و اخليه زي عندي [ انا عملت reset for head و خليته في ال version اللي قبليها ] في ال Version القديمة لأن ال Git مش بتقبل في الوضع العادي :== 

```bash
git push --force-with-lease origin main
```

