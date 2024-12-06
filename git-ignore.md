# `.gitignore` Cheat Sheet

---

## What is `.gitignore`?

A `.gitignore` file specifies intentionally untracked files that Git should ignore. This helps prevent sensitive, temporary, or unnecessary files from being committed to the repository.

---

## Basic Syntax

- **Comment lines**: Use `#` at the start of the line.  
    Example:

    ```shell
    # This is a comment
    ```

- **Blank lines**: Ignored and used for readability.

### Ignore Patterns

1. **Exact match**:  
    To ignore a specific file:  

    ```shell
    file.txt
    ```

2. **Wildcard (`*`)**:  
    Matches zero or more characters.  

    ```shell
    *.log   # Ignore all .log files
    temp*   # Ignore files starting with "temp"
    ```

3. **Directories**:  

    To ignore a directory and its contents, add a trailing `/`.  

    ```shell
    /cache/ # Ignore "cache" directory
    ```

4. **Negation (`!`)**:  
    To unignore files or directories.  

    ```shell
    !important.log
    ```

5. **Patterns with paths**:  
    Specify relative paths for more precise ignores.  

    ```shell
    /config/settings.json  # Ignore only in the root
    **/debug.log           # Ignore in all subdirectories
    ```

---

## Clearing Git Ignore Cache

### Why Clear the Git Ignore Cache?

If you modify the `.gitignore` file to ignore files that are already tracked by Git, those files will remain in the repository until you remove them from tracking.

### Steps to Clear the Cache

1. **Remove the files from tracking (without deleting them):**

   ```bash
   git rm -r --cached .
   ```

2. **Add the modified `.gitignore` to the staging area:**

   ```bash
   git add .gitignore
   ```

3. **Commit the changes:**

   ```bash
   git commit -m "Updated .gitignore and cleared cache"
   ```

Now Git will respect the `.gitignore` rules and stop tracking the ignored files.

---

## Examples of Common Patterns

### Operating System Files

- macOS:  

    ```shell
    .DS_Store
    .AppleDouble
    .LSOverride
    ```

- Windows:  

    ```shell
    Thumbs.db
    ehthumbs.db
    Desktop.ini
    ```

- Linux:

    ```shell
    *~
    .nfs*
    ```

---

### Programming Languages

#### Python

```shell
*.pyc
*.pyo
__pycache__/
.env
.venv/
```

#### Node.js

```shell
node_modules/
npm-debug.log*
yarn-debug.log*
yarn-error.log*
.env
```

#### Java

```shell
*.class
*.jar
*.war
*.ear
*.iml
```shell

#### C/C++

```shell
*.o
*.out
*.so
*.a
*.d
```

#### Ruby

```shell
*.gem
.log
tmp/
```

#### Go

```shell
*.exe
*.test
*.out
```

#### Rust

```shell
*.rs.bk
target/
Cargo.lock
```

---

### Frameworks and Tools

#### Git

```shell
.git/
```

#### IDEs

- VSCode:  

    ```shell
    .vscode/
    ```

- IntelliJ IDEA:  

    ```shell
    .idea/
    *.iml
    ```

- Eclipse:  
  
    ```shell
    .classpath
    .project
    .settings/
    bin/
    ```

#### Logs and Temporary Files

```shell
*.log
*.tmp
*.swp
*.bak
*.old
*.~lock.*
```

---

### Ignoring Files in Specific Directories

- Ignore all `.log` files in the `/logs` directory:  

    ```shell
    logs/*.log
    ```

- Ignore everything in the `/temp` directory except `.keep`:  

    ```shell
    temp/
    !temp/.keep
    ```

---

## Useful Tips

1. **Check ignored files**:  
    View which files are being ignored:  

    ```shell
    git status --ignored
    ```

2. **Exclude `.gitignore` itself**:  
    Add this to `.gitignore`:  

    ```shell
    .gitignore
    ```

3. **Use global `.gitignore`**:  
    Configure a global ignore file for your user:  

    ```shell
    git config --global core.excludesfile ~/.gitignore_global
    ```

    Example content of `~/.gitignore_global`:  

    ```shell
    *.bak
    *.swp
    ```
