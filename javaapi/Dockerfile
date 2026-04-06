FROM amazoncorretto:8 AS builder
WORKDIR /emartapp
COPY ./ ./javaapi
RUN yum update && yum install maven -y
RUN cd javaapi && mvn install -DskipTests 

FROM amazoncorretto:8
WORKDIR /emartapp
COPY --from=builder /emartapp/javaapi/target/book-work-0.0.1-SNAPSHOT.jar ./javaapi/book_0.0.1.jar

EXPOSE 9000

ENTRYPOINT ["java","-jar","javaapi/book_0.0.1.jar"]
