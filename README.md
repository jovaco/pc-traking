# bug-traking
Exemple d'application web Java avec une architecture simple et adaptable au mobile en JPA + CDI + Transactional + JSF + Primeface.

# Work in progress...

Avec Tomcat et intelidji :
add conf --- dans bin/catalin.bat
:okHome

  <pre><code>
  echo stup JASS environment...
  set JAVA_OPTS=%JAVA_OPTS% -Djava.security.auth.login.config=%CATALINA_HOME%/conf/jaas.config
  echo JAVA_OPTS %JAVA_OPTS%
  </pre></code>

aussi ne pas oublier de a jouter jass.conf dans le dossier de config de Tomcat:
  <pre><code>
  TrakingLogin {
      org.pc.traking.model.jass.TrakingLoginModule required debug=true;
  };
  </pre></code>

apres cela dois correcpendre au contenu du Context.xml: (voir le ficher .MD)
 <?xml version=1.0" encoding="UTF-8"?>
 <Context antiJARLocking="true" path="/e-authentication">
  <Realm appName="TrakingLogin" className="org.apache.catalina.realm.JAASRealm"
         roleClassNames="org.pc.traking.model.jass.RolePrincipal" userClassNames="org.pc.traking.model.jass.UserPrincipal"/>
 </Context>

config intelidji (force deploy et context path)
* case a cocher 'Deploy applications configured in Tomcat instance'
* Dans le section deploiment mettre le Application context a : /e-authentication 
