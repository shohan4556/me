+++
date = "2019-02-04T00:00:00"
draft = false
tags = ["ওপেন সোর্স", "গিটহাব"]
title = "How To Setup Git with Google Drive, Dropbox, Onedrive"
math = false
summary = """
Install google drive, dropbox on your local PC and enable sync
"""

[header]
image = "headers/c2.jpg"
caption = "Image credit: Me !"

+++

* **step - 01 :** Install google drive, dropbox on your local PC and enable sync. 
* **step - 02 :** install and configure git on your PC.
* **step - 03 :** create a folder on google-drive and open `git-bash` there
* **step - 04 :** write git command `git init --bare`
* **step - 05 :** Initialize a git repo outside of google-drive
* **step - 06:** now connect google drive repo with your the repo that you just created outside of google drive.
 `git remote add origin "/C/Users/JoeUser/Google Drive/git/project1.git"` (note if the url does not have any space then remove double quote)
to check if the remote added `git remote -v`
* **step - 07 :** If remote added without any error then push your local changes `git push -u origin master`
And you done. now you can make changes and push your local changes to google-drive repo. 
If you want to clone that repo then simply `git clone "/C/Users/JoeUser/Google Drive/git/project1.git"`

[video tutorial] (https://www.youtube.com/watch?v=T2aJP5MOxug)


Follow me on 
[Githab](https://github.com/shohan4556/)|
[Twitter](https://twitter.com/shohan4556/)|
[Facebook](https://facebook.com/shohan4556/)|
[Quora](https://www.quora.com/profile/Shohanur-Rahaman)

***© copyright reserved by the Author.***

