# GIT LEARNING
- [Link to course](https://www.udemy.com/course/git-complete/)
- [Visual reference](https://lurklurk.org/gitpix/gitpix.html)
- [Shortcuts List](https://kapeli.com/cheat_sheets/Oh-My-Zsh_Git.docset/Contents/Resources/Documents/index)
- Videos
  - [Git For Ages 4 And Up](https://www.youtube.com/watch?v=1ffBJ4sVUb4)
  - [Git with Scott Chacon of GitHub](https://youtu.be/ZDR433b0HJY?si=bA9NX6ViD01hFpgV)

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
## Fetch [doc](https://git-scm.com/docs/git-fetch)
![Fetch image](https://www.edureka.co/community/?qa=blob&qa_blobid=5756095483457844058)

მოაქვს მეტა მონაცემები remote repo-დან
```git
git fetch origin master --all
```

## Merge [doc](https://git-scm.com/docs/git-merge)

იმისთვის რომ მარტივი იყოს დასამახსოვრებლად, სიტყვა merge -ს ერთერთი მნიშვნელობა არის __შთანთქმა__ ან __ჩაყლაპვა__. შესაბამისად შეგვიძლია წარმოვიდგინოთ, როგორ __ყლაპავს__ მიმდინარე ტოტი, მითითებულს


**გადავერთოთ იმ ტოტზე რომელიშიც გვინდა გავაერთიანოთ სხვა ტოტი**
```git
git checkout master
git merege other_branch 
```

`--fast-forward` - (default param) როდესაც master-ზე არ მომხდარა ცვლილებები და ისე ერთიანდება, თითქოს არც ყოფილა განტოტვა.

![](https://res.cloudinary.com/practicaldev/image/fetch/s--np1tGOur--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://i.imgur.com/hNZADrt.gif)


`--no-ff` - ისე ერთიანდება, თითქოს __ყოფილა__ განტოტვა.

**კონფლიქტების გადაწყვეტა**
```git
git mergetool
```
---
## Rebase
**ცვლის ტოტის საწყისს**

![Rebase gif](https://res.cloudinary.com/practicaldev/image/fetch/s--5J2KO7OU--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rf2gl1srlyiksxvbws3z.gif)

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

![](https://cdn.hackernoon.com/hn-images/1*IxDdJ5CygvSWdD8MCNpZNg.gif)


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
git tag -a v1.0.0
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
