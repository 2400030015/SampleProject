# ---------- Stage 1: Build Stage ----------
FROM eclipse-temurin:11-jdk AS build
WORKDIR /app
COPY HelloWorld.java .
RUN javac HelloWorld.java

# ---------- Stage 2: Runtime Stage ----------
FROM eclipse-temurin:11-jre
WORKDIR /app
COPY --from=build /app/HelloWorld.class .
CMD ["java", "HelloWorld"]

