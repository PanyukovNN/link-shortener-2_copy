FROM amazoncorretto:17.0.7-alpine

#ARG TAG
#
#COPY ./link-shortener-2-$TAG.jar ./link-shortener.jar
COPY ./link-shortener.jar ./link-shortener.jar

ENV TZ=Europe/Moscow

EXPOSE 8080

CMD ["java", "-jar", "./link-shortener.jar"]