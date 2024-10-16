# Introduction

**Welcome to Git Tutor!**

In this repository, there are branches that will guide you through features & commands existed in git and how it can be applied in a project.

First and foremost, you are unable to push changes directly to this repository. Therefore, it is recommend that you start by forking this repository into your profile.

![fork-home](https://github.com/user-attachments/assets/298e4f44-d937-4632-a72b-7cae5200b686)

![fork-form](https://github.com/user-attachments/assets/fe84bf58-1305-497d-b9d0-20f515a5d549)

1. Set the owner & repository name. The owner default should be your profile.
2. Fill the description. It's optional so you can change it, fill it with blank or let it as it is.
3. Uncheck "Copy the `main` branch only". You will need the other branches.

Once you have created your repository in github, you can now clone the repository into your local machine. First, go to a directory where you want to put your local repository, open your preferred CLI in that directory and run this command:

```console
git clone https://github.com/<your-profile>/blmw-git-tutor.git
```

💡 Tips: You can copy the URL of your remote repository in this menu:

<img width="674" alt="git-clone-url" src="https://github.com/user-attachments/assets/38798851-edb9-4ab1-82bf-eeba67843d2c">

## Making Changes

Create an empty text file with a name `test.txt` inside your local repository. To record this change, you need to stage it and commit it. To do that, you can run this command:

```console
git add test.txt
git commit -m "Add test.txt"
```

Finally, you can add this record to your remote repository by pushing it with this command:

```console
git push
```

💡 Tips: If you have a lot of files to be staged, you can run this command to stage all files within that directory:

```console
git add .
```
