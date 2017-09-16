# GitFlow Practice
1. initial commit
    create a sample project which is based on 0.1
2. 於 pom.xml 加入 `<scm>` 並改為下一個版本的 SNAPSHOT (ex: 1.0-SNAPSHOT)
    * 設定 `<connection>` 與 `<developerConnection>`
3. 開始開發 bala bala bala
4. 切換至 release 分支
    `git checkout -b release-1.0`
5. 使用 [Maven Release Plugin](http://maven.apache.org/maven-release/maven-release-plugin/examples/prepare-release.html)
    1. `mvn release:prepare -DreleaseVersion=1.0 -DdevelopmentVersion=2.0-SNAPSHOT`
    2. `mvn release:clean`
        * 用於清除 .releaseBackup & release.properties
6. 合併回 master 與 develop 分支
    1. `git checkout master` & `git merge release-1.0 --no-ff -m "merge release 1.0"`
    2. `git checkout develop` & `git merge release-1.0 --no-ff -m "merge release 1.0"`

---
### Reference
* [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/)
    * [Git flow 分支策略](http://git-tutorial.readthedocs.io/zh/latest/branchingmodel.html)
