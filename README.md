# process-server-externaldb

This repo provides an little example about how to create a Timer process using Quartz on OpenShift with
a external database, this example provides db2 and oracle examples to be deployed as a jdbc module
by the s2i process.

The application template that will be used as example can be found here:

https://github.com/jboss-openshift/application-templates/blob/master/processserver/processserver64-externaldb-s2i.json


To install this example on OpenShift, you can just use the following commands and adjust the parameters
according your environment:


Hibernate Dialects:
The only observation regarding the dialects is when using oracle, we need to use the following:

```java
org.jbpm.persistence.jpa.hibernate.DisabledFollowOnLockOracle10gDialect
```


Note that, if you have a maven mirror available, is recommended to use it, it can signifcantly speed up the s2i builds.
The parameter is MAVEN_MIRROR_URL

For DB2, in addition to the example above, you might want to set the KIE_SERVER_PERSISTENCE_SCHEMA env.


For any question, or issues, feel free to open an issue.