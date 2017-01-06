An example maven project illustrating how to use [Oracle's maven repo](https://maven.oracle.com).

To try it,

1. If you don't already have a [free Oracle
   Account](http://www.oracle.com/us/corporate/contact/help/index.html), create
   one.
1. Accept the Terms and Conditions of Oracle's Maven Repo by going to
   https://maven.oracle.com
1. Make a copy of the sample config files for editing:
   `cp -r config-sample to config`
1. Edit `config/settings.xml` to fill in your Oracle Account username (email
   address) and password
  1. if you want to encrypt your password, you need to create a master
     password, put it in settings-security.xml, and then encrypt your Oracle
     Account password.  See
     [this](https://blogs.oracle.com/dev2dev/entry/how_to_get_oracle_jdbc) and
     [this](https://maven.apache.org/guides/mini/guide-encryption.html) for
     details.
  1. otherwise, just enter your plain-text password in `setting.xml` and delete
     `settings-security.xml`.
1. `mvn dependency:resolve` will download the Oracle JDBC driver to your local repository.


See also: [example-gradle-oracle](https://github.com/robin-a-meade/example-gradle-oracle)
