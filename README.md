# GIT LEARNING


## Basics

**სახელის შეცვლა git -ის მეშვეობით**
```git
git mv old.txt new.txt
```

**ოპერაციული სისტემიდან შეცვლილი ფაილების სწორად აღსაქმელად**
```git
git add -A
```
---
## Branch

**ჩამოთვლისი ლოკალურ და რემოუთ ტოტებს**
```git
git branch -a
```

**ტოტის შესაქმნელად**
```git
git branch newbranch
```


**ტოტის შესაცვლელად**
```git
git checkout newbranch
```

axla mainc qeni konfliqti
**ტოტისთვის სახელის შესაცვლელად**
```git
git branch -m old_branch_name new_branch_name
```

**ტოტის წასაშლელად**
```git
git branch -d old_branch_name
```
---

## Merge

იმისთვის რომ მარტივი იყოს დასამახსოვრებლად, სიტყვა merge -ს ერთერთი მნიშვნელობა არის __შთანთქმა__ ან __ჩაყლაპვა__. შესაბამისად შეგვიძლია წარმოვიდგინოთ, როგორ __ყლაპავს__ მიმდინარე ტოტი, მითითებულს


**გადავერთოთ იმ ტოტზე რომელიშიც გვინდა გავაერთიანოთ სხვა ტოტი**
```git
git checkout master
git merege other_branch 
```

`fast-forward` - (default param) როდესაც master-ზე არ მომხდარა ცვლილებები და ისე ერთიანდება, თითქოს არც ყოფილა განტოტვა.

`--no-ff` - ისე ერთიანდება, თითქოს __ყოფილა__ განტოტვა.

**კონფლიქტების გადაწყვეტა**
```git
git mergetool
```


---
## Log 


**დროის ლიმიტი**
```git
git log --since="3 days ago" --oneline
```

**კონკრეტული ფაილის ისტორიის სანახავად**
```git
git log -- filename --oneline
```

---
## Show 
დეტალური ინფოს სანახავად

```git
git show somehash
```

---
## Alias

გლობალური ალიასები ინახება ამ მისამართზე
```bash
cd ~/.gitconfig
```

**გლობალური ალიასის შესაქმნელად**
```git
git config --global alias.somealias "somename --param1 --param2 --param3"
```
---
## Diff
**განსხვავების სანახავად 2 ტოტს შორის**
```git
git diff branch1 branch2
```

```git
git difftool branch1 branch2
```


