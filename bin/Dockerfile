FROM maven:3.6-alpine

ENV APP_DIR /src/app/

RUN mkdir -p $APP_DIR

COPY ./pom.xml ${APP_DIR}

WORKDIR ${APP_DIR}

RUN ["mvn", "clean"]

RUN ["mvn", "de.qaware.maven:go-offline-maven-plugin:resolve-dependencies", "-P", "integration"]

COPY . .

ENTRYPOINT ["sh"]
