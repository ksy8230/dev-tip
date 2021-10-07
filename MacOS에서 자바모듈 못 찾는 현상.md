# MacOS에서 자바모듈 못 찾는 현상

## 현상

스프링부트 어플리케이션을 실행(mvn spring-boot:run)하려니 뜬 에러

> Unable to make protected final java.lang.Class java.lang.ClassLoader.defineClass(java.lang.String,byte[],int,int,java.security.ProtectionDomain) throws java.lang.ClassFormatError accessible: module java.base does not "opens java.lang" to unnamed module

## 해결

pom.xml 파일에서

```
<build>
    <finalName>project</finalName>
    <plugins>
        <plugin>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-maven-plugin</artifactId>
            <configuration>
                <jvmArguments>--add-opens java.base/java.lang=ALL-UNNAMED</jvmArguments>
            </configuration>
        </plugin>
    </plugins>
</build>

```
