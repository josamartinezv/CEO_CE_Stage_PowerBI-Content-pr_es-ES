<properties pageTitle="Comandos de Git para crear un nuevo artículo o actualizar uno existente" description="Steps for working with the Power BI technical content GitHub repositories." metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/09/2015" ms.author="mblythe" />

# Comandos de Git para crear un nuevo artículo o actualizar uno existente


## Standard process (working from master)
Follow the steps in this article to create a local working branch on your computer so that you can create a new article for the technical documentation section of powerbi.microsoft.com or update an existing article.

![](./media/git-commands-for-master/githubcommands1.png)

1. Start Git Bash (or the command-line tool you use for Git).

 <bpt id="p1">**</bpt>Note:<ept id="p1">**</ept> If you are working in the public repository, change powerbi-content-pr to powerbi-content in all the commands.

2. Change to powerbi-content-pr:

        cd powerbi-content-pr
3. Check out the master branch:

        git checkout master

4. Create a fresh local working branch derived from the master branch:

        git pull upstream master:<working branch>


5. Move into the new working branch:

        git checkout <working branch>

6. Let your fork know you created the local working branch:

        git push origin <working branch>

7. Cree el nuevo artículo o modifique uno que ya exista. Use Windows Explorer to open and create new markdown files, and use Atom (http://atom.io) as your markdown editor. Una vez que haya creado o modificado el artículo y las imágenes, avance al siguiente paso.

8. Add and commit the changes you made:

        git add .
        git commit –m "<comment>"
        
   Or, to add only the specific files you modified:

        git add <file path>
        git commit –m "<comment>"

9. Update your local working branch with changes from upstream:

        git pull upstream master

10. Push the changes to your fork on GitHub:

        git push origin <working branch>

12. When you are ready to submit your content to the upstream master branch for staging, validation, and/or publishing, in the GitHub UI, create a pull request from your fork to the master branch.

13. The pull request acceptor reviews your pull request, provides feedback, and/or accepts your pull request. 

14. Verify your published article or changes at

 http://powerbi.microsoft.com/documentation/articles/<bpt id="p1">*</bpt>name-of-your-article-without-the-MD-extension<ept id="p1">*</ept>

**Notas:**

- At this time, technical articles are published once daily around 10 AM Pacific Standard Time (PST), Monday-Friday. Remember, your pull request has to be accepted before changes are included in the next scheduled publishing run.
- If you are an employee working in the private repository, all pull requests are subject to validation rules that need to be addressed before the pull request can be accepted. 
- In the private repo, the changes you submit are automatically staged, and a staging link is written to the pull request. Please review your staged content and sign off in the pull request comments to indicate the changes are ready to be pushed live. If you don't want the pull request to be accepted - if you are just staging the changes - add that note to the pull request.

## Working with release branches

When you are working with a release branch, the best way to create a local working branch from the release branch is to use this command syntax:

    git checkout upstream/<upstream branch name> -b <local working branch name>

This creates the local branch directly from the upstream branch, avoiding any local merging.

