#Jenkins Docker image
基于官方镜像，修改java版本为oracle-java-7u80-b15，另外添加了ant maven
ANT_VERSION 1.9.6
ANT_HOME /usr/share/ant
MAVEN_VERSION 3.3.3
MAVEN_HOME /usr/share/maven
JAVA_VERSION 7u80-b15
JAVA_HOME /usr/java/default


 https://github.com/jenkinsci/docker

（以下粘贴自jenkins官方）

# 用法

```
docker run -p 8080:8080 -p 50000:50000 jenkins
```

This will store the workspace in /var/jenkins_home. All Jenkins data lives in there - including plugins and configuration.
You will probably want to make that a persistent volume (recommended):

```
docker run -p 8080:8080 -p 50000:50000 -v /your/home:/var/jenkins_home jenkins
```

This will store the jenkins data in `/your/home` on the host.
Ensure that `/your/home` is accessible by the jenkins user in container (jenkins user - uid 1000) or use `-u some_other_user` parameter with `docker run`.


You can also use a volume container:

```
docker run --name myjenkins -p 8080:8080 -p 50000:50000 -v /var/jenkins_home jenkins
```

Then myjenkins container has the volume (please do read about docker volume handling to find out more).

详细说明请移步https://github.com/jenkinsci/docker/blob/master/README.md
