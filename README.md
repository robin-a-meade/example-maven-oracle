An example maven project illustrating how to use [Oracle's maven repo](https://maven.oracle.com).

# To try it:

If you don't already have a [free Oracle
Account](http://www.oracle.com/us/corporate/contact/help/index.html), create
one.

Accept the Terms and Conditions of Oracle's Maven Repo by going to
https://maven.oracle.com

Make a copy of the sample config files for editing:

```
cp -r config-sample config
```
   
Edit `config/settings.xml` to fill in your Oracle Account username (email
address) and password
- if you want to encrypt your password, you need to create a master password,
  put it in settings-security.xml, and then encrypt your Oracle Account
  password.  See links in the *See also* section below for details.
- otherwise, just enter your plain-text password in `setting.xml` and delete
  `settings-security.xml`.

```
mvn --settings=./config/settings.xml -Dsettings.security=./config/settings-security.xml dependency:resolve
```

Above command will *resolve* the dependencies that are declared in `pom.xml`.
The first time this is called, it will download the Oracle JDBC driver to your local repository.
Subsequent calls will just verify that the JDBC driver exists in you local respository.


# Notes

For this example, I put `settings.xml` and `settings-security.xml` files in a `config` subdirectory just to make it a self-contained example.

Typically you'd have these files in your `~/.m2` directory. In that case, the maven command would be simplified to:

```
mvn dependency:resolve
```

# See also

- [example-gradle-oracle](https://github.com/robin-a-meade/example-gradle-oracle)  
  <tt>github.com/robin-a-meade/example-gradle-oracle</tt>
  an example of how to use the Oracle Maven Repo with gradle
- [Get Oracle JDBC drivers and UCP from Oracle Maven Repository (without IDEs)](https://blogs.oracle.com/dev2dev/entry/how_to_get_oracle_jdbc)  
  `blogs.oracle.com/dev2dev/entry/how_to_get_oracle_jdbc`
- [Get Oracle JDBC drivers from the Oracle Maven Repository - NetBeans, Eclipse & Intellij](https://maven.apache.org/guides/mini/guide-encryption.html)  
  `blogs.oracle.com/dev2dev/entry/oracle_maven_repository_instructions_for`
- [Configuring the Oracle Maven Repository](http://docs.oracle.com/middleware/1213/core/MAVEN/config_maven_repo.htm#MAVEN9010)  
  `docs.oracle.com/middleware/1213/core/MAVEN/config_maven_repo.htm`
- [Password Encryption](https://maven.apache.org/guides/mini/guide-encryption.html)  
  `maven.apache.org/guides/mini/guide-encryption.html`

<!---
- []()
  **
-->

