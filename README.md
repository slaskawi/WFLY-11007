= Run the Docker container:

`docker run -p 9443:8443 -v $PWD/keystores:/opt/jboss/keycloak/standalone/configuration/keystores -v $PWD/standalone-ha.xml:/opt/jboss/keycloak/standalone/configuration/standalone-ha.xml --entrypoint "/opt/jboss/keycloak/bin/standalone.sh" jboss/keycloak:master -c standalone-ha.xml -Djavax.net.debug=ssl:handshake:verbose --debug -b 0.0.0.0`

= Run curl against it:

`curl -vk https://172.17.0.3:8443/auth`
