---
title: "Configuring local ignore rules"
description: ""
lead: ""
date: 2022-01-12T02:48:57+00:00
draft: false
weight: 200
toc: false
resources:
  - src: alert.png
---

In some cases a developer may want the BluBracket CLI Tool to ignore specific secret types or entire files. This can be achieved by creating a `.blubracket-ignore` file. This file is then placed into the root directory of the repository.

The format of the `.blubracket-ignore` file is similar to a `.gitignore` file.

Empty lines and lines beginning with `#` will be ignored

To ignore all secrets in a file a glob pattern is recognized. For example `**/tests` will ignore any secrets found in all files within any directory or sub-directory named “tests”.

To ignore a specific secret type, say passwords, you would add the following line: `secret_type:password.*`, where `password.*` is a perl compatible regular expression.

```yaml
**/tests/**
secret_type:password.*
```
