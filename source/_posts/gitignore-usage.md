---
title: .gitignore usage
description: No description
date: 2022-07-23 08:23:48
tags:
  - git
categories:
  - [git]
  - [guide]
---

.gitignore file let one config what files should not be included in the git repository. In the following is the way to write git commit.

- .gitignore files will be included in the git repository
- you can have .gitignore files anywhere in the project, not only in the root directory
- if a file is already tracked, it will not be ignored. Use git rm --cached to remove it from the staging area
- each line indicates a ignore pattern, empty lines and lines starting with # (comments) are ignored. Patterns in later lines will override earlier ones if they have a conflict. Patterns will be matched recursively for all the files and folders under the .gitignore directory
- patterns
  - ```filename```: ignore all files or folders with the name *filename*
  - ```filename/```: ignore folders with the name *filename*
  - ```!filename```: do not ignore files or folders with the name *filename*

    An application of this is to ignore files but exclude folders

    ```git
    filename
    !filename/
    ```

- wildcards
  - ```*```: matches multiple characters
  - ```**```: matches multiple characters and subfolders
  - ```?```: matches a single character
  - ```[xxx]```: matches a single character in the set xxx

## Reference

- <https://blog.csdn.net/nyist_zxp/article/details/119887324>
