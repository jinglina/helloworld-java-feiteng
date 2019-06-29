FROM 10.7.12.250/feiteng/arm64v8/openjdk:8-jdk

# USER root
# ARG ZIP_FILE
RUN mkdir /images
ADD ./target/service-0.0.1-SNAPSHOT.jar /images
# RUN chown -R jboss:root /deployments/incloudos
# ENV JAVA_APP_DIR=/images

# USER jboss

# ENTRYPOINT ["java"]
CMD ["java", "-jar", "/images/service-0.0.1-SNAPSHOT.jar"]
WORKDIR /images
