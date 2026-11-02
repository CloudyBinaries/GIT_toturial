
كان في مشكلة بتحصل ان ال Push ساعتات في ال branch مش راضي يتعمل 
و ان ال tracking ساعة لما اكتب ال git status مش موجود يعني مش بيجيب الجملة بتاعت ال 

```
$ git status
On branch test
Your branch is up to date with 'origin/test'.
```

كان بيجيبلي بس : 

```bash 
$ git status
On branch test
nothing to commit, working tree clean
```

و كانت المشكلة كلها اني في اول commit علي ال branch دا نسيت حاجة مهمة جدا : 

اضيف ال `-u` في اول push و دا اللي سبب خلل في ال tracking 

, و دا اختصار ل : 

```bash 
--up-stream 

[ complete command ] : git push -u origin test
```

