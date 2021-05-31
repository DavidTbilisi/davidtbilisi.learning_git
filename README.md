# GIT LEARNING
[Link to course](https://www.udemy.com/course/git-complete/)

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

## Commit 

git add and commit with short message
```git
git commit -am "commit messsage"
```

```git
git commit --amend
```
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
## Rebase
**ცვლის ტოტის საწყისს**
```git
git checkout otherbranch
git rebase master
```

```git
git rebase --abort
```

```git
git rebase --continue
```

```git
git pull --rebase origin master
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


## Stash
სიტყვა ნიშნავს დამალვას, დაფარულ საგანძურს

**დროებით დამალვა (კომენტარებით)**
```git
git stash save "comment message"
```

**დროებით დამალვა (კომენტარებით)**
`-u` for untrecked
```git
git stash -u save "comment message"
```
**დამალულის სიის ჩვენება**

```git
git stash list
```
**კონკრეტული საგანძურის ნახვა**
```git
git stash show@{n}
```
**საგანძურის დაბეუნება**
```git
git stash apply stash@{1}
```

```git
git stash drop stash@{1}
```

**apply & drop last stash**
```git
git stash pop
```

```git
git stash branch new_branch_name
```

**ყველა საგანძურის წაშლა**
```git
git stash clear
```
---
## Tags

```git
git tag tagname
```

```git
git tag --list
```

```git
git show tagname
```


```git
git show --delete tagname
```

**release** 
- Major release number
- Minor release number
- Maintenance release number (bugfixes only)

```git
git tag -a v-1.0.0
```

**ტეგის მინიჭება კონკრეტული ქომითისთვის**
```git
git tag -a tagname sha_of_commit
```

**ტეგის გადატანა სხვა ქომითისთვის**
```git
git tag -a tagname -f sha_of_commit
```

**კონკრეტული ტეგის გადატანა GitHub-ზე**

რაც თავის მხრივ ქმნის zip ფაილის გადმოწერის საშუალებას.
```git
git push origin tagname
```


**ტეგების გადატანა GitHub-ზე**

```git
git push origin master --tags
```

**ტეგების წაშლა GitHub-დან**

> push nothing to this tag name

რჩება ლოკალურად მაგრამ იშლება GitHub-დან
```git
git push origin :tagname
```
