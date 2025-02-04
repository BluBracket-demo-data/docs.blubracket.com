---
title: "Configuring ignore rules per repo"
description: "How to Set Ignore Rules Ignore Rules For All Users of A Repository"
lead: "How to Set Ignore Rules Ignore Rules For All Users of A Repository"
date: 2022-01-12T02:48:57+00:00
draft: false
weight: 200
toc: false
resources:
  - src: ignore.jpg
---

In some cases a repo administrator may want to ignore specific secret types, secret values, or paths for all commits by any contributor to that repo. This can be achieved by creating an ignore.yaml file. This file is then placed into the root directory of the repository, within a `.blubracket` directory at the repo root.

When a match of the ignore file is made, an alert will not be created (but an event will still be generated).

Example below is a repository called Test1, which has a `.blubracket` directory and within the folder is the `ignore.yaml` file.

![ignore](ignore.jpg)

#### Sample .blubracket/ignore.yaml

```yaml
# Ignore by file path
- paths:
    - "**/*_test.go"
    - cli/cmd/default-sensitive-words-config.yaml
    - cli/cmd/data/*

# Ignore by secret value
# Equivalent to 'secret_value == my_password OR secret_value == my_token'
- secret_values:
    - my_password
    - my_token

# Ignore by secret type
# Equivalent to 'secret_type == password_assignment OR secret_type == secret_assignment'
- secret_types: password_assignment
```
