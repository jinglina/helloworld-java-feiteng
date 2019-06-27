FROM fabric8/java-alpine-openjdk8-jdk:1.5.6.1

# USER root
# ARG ZIP_FILE
ADD ./target/service-0.0.1-SNAPSHOT.jar /dir/images
# RUN chown -R jboss:root /deployments/incloudos
ENV JAVA_APP_DIR=/dir/images

# USER jboss
WORKDIR /dir
ENTRYPOINT ["java"]
CMD ["-jar", "service-0.0.1-SNAPSHOT.jar"]