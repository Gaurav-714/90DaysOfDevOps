# `day-38-yaml.md`

## File: `person.yaml`

```yaml
name: Gaurav Nagose
role: DevOps Engineer (Learning)
experience_years: 1
learning: true

tools:
  - Docker
  - Kubernetes
  - Git
  - GitHub Actions
  - Terraform

hobbies: [coding, gaming, sports]
```

---

## File: `server.yaml`

```yaml
server:
  name: production-server
  ip: 192.168.1.10
  port: 8080

database:
  host: localhost
  name: myapp_db
  credentials:
    user: admin
    password: secret@123

startup_script_pipe: |
  #!/bin/bash
  echo "Starting server..."
  docker-compose up -d
  echo "Server started"

startup_script_fold: >
  This is a long startup message that will be folded into
  a single line when parsed by YAML.
```

---

## Task Notes

### Task 2: Two ways to write lists

* Block style:

```yaml
tools:
  - Docker
  - Kubernetes
```

* Inline style:

```yaml
hobbies: [coding, gaming]
```

---

### Task 3: Tabs vs Spaces

* YAML **breaks if tabs are used**
* Error example (yamllint):

```
found character '\t' that cannot start any token
```

---

### Task 4: `|` vs `>`

* Use `|` when:

  * Writing scripts
  * Preserving formatting (newlines matter)

* Use `>` when:

  * Writing long text
  * You want it as a single line

---

### Task 5: Validation Errors

If indentation is broken:

```yaml
tools:
- docker
  - kubernetes
```

Error:

```
mapping values are not allowed here
```

---

### Task 6: Difference

#### Correct:

```yaml
tools:
  - docker
  - kubernetes
```

#### Broken:

```yaml
tools:
- docker
  - kubernetes
```

Problem:

* Inconsistent indentation
* First item is not properly nested under `tools`

---

## How I Verified

```bash
cat person.yaml
cat server.yaml

yamllint person.yaml
yamllint server.yaml
```

---


## What I Learned

1. YAML is **indentation-sensitive** — spaces (not tabs) define structure.
2. Lists can be written in **two ways**:

   * Block style using `-`
   * Inline style using `[item1, item2]`
3. Multi-line strings:

   * `|` → preserves formatting (good for scripts)
   * `>` → folds into a single line (good for long text)
