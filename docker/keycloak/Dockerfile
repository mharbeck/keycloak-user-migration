FROM jboss/keycloak:15.0.0

USER root

COPY . /project
RUN cd /project && ./mvnw clean package

FROM jboss/keycloak:15.0.0
USER root
COPY --from=0 /project/target/*.jar /opt/jboss/keycloak/standalone/deployments/app.jar
USER 1000