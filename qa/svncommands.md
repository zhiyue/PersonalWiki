## Some commands of SVN [Back](./qa.md)

#### 1. Locate file `*.js` or `*.css`

```bash
svn ls -R <repo_svn_url>/trunk/ | grep .js

# locate with a whole path
# Linux
svn ls -R <repo_svn_url> | egrep "*.js$|*.css$" | xargs -n1 -i echo <repo_svn_url>/trunk/{} | awk "{print $1$2}"
# Mac OS
svn ls -R <repo_svn_url> | grep -e .js$ -e .css$ | xargs -n1 -i echo <repo_svn_url>/trunk/{} | awk "{print $1$2}"
```

#### 2. Cat file

```bash
svn cat <repo_svn_url>
```

#### 3. Statistic Code Line for GitHub like JavaScript

```bash
svn ls -R <repo_svn_url>/trunk/ | egrep "*.js$|*.jsx$" | xargs -n1 -i echo <repo_svn_url>/trunk/{} | awk "{print $1$2}" | xargs svn cat | grep -v ^$ | wc -l
```

#### 4. Compiling problems of Subversion

Problem: **/usr/include/apr-1.0/apr.h:358:1: error: unknown type name 'off64_t'**
Solution: 
    - sudo vi /usr/local/apr/include/apr-1/apr.h in line 358
    - add line typedef long off64_t; before typedef off64_t apr_off_t