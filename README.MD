# Open Weather Testing Framework

A Java testing framework for the Open Weather API. The framework retrieves json responses and returns objects that allow for thorough testing of the API via all possible endpoint URLs. With the use of comprehensive helper methods, the framework ensures quick and simple testability. A BDD testing layer is also included using gherkin features to test the API against acceptance criteria.

---

## Usage

*IMPORTANT*

To use this framework you will need to first acquire an API key from [Open Weather](https://openweathermap.org/). 
Instructions on how to add your API key to the framework is outlined below.

- [Java 14](https://www.oracle.com/uk/java/technologies/javase/jdk14-archive-downloads.html)
- [Maven 4](https://maven.apache.org/ref/4-LATEST/)
  
**Dependenices:**
- [JUnit 5.8.2](https://junit.org/junit5/)
```java
<dependency>
  <groupId>org.junit.jupiter</groupId>
  <artifactId>junit-jupiter</artifactId>
  <version>5.8.2</version>
</dependency>
```
- [Jackson 2.13.3](https://github.com/FasterXML/jackson)
```java
<dependency>
  <groupId>com.fasterxml.jackson.core</groupId>
  <artifactId>jackson-databind</artifactId>
  <version>2.13.3</version>
</dependency>
```
- [Cucumber 7.3.3](https://cucumber.io/)
```java
<dependency>
  <groupId>io.cucumber</groupId>
  <artifactId>cucumber-java</artifactId>
  <version>7.3.3</version>
</dependency>
<dependency>
    <groupId>io.cucumber</groupId>
    <artifactId>cucumber-junit</artifactId>
    <version>7.3.3</version>
</dependency>
```
- [Mockito 4.6.1](https://site.mockito.org/) - Used only to allow for testing of the framework.
```java
<dependency>
  <groupId>org.mockito</groupId>
  <artifactId>mockito-core</artifactId>
  <version>4.6.1</version>
</dependency>
```
---
## API Key

You will need to create a *.properties* file and include it within your project. You must then include this file in your *.gitignore* DO NOT PUSH YOUR PERSONAL KEY TO PUBLIC REPOSITORIES.
Once you have acquired a key, add it to the file.

*.properties*
```java 
password={PUT YOUR KEY HERE}
```
You will then need to add the file location to the property loader.

*PropertiesLoader*
```java
properties.load(new FileReader({ADD YOUR .properties FILE PATH HERE}));
```
---

## Testing

The aim of the framework is to remove as much of the workload of the tester so that they can focus solely on what, within the API, to test. Offering methods to check for null values, valid value boundaries and consistent data, plus checking responses against the OW documentation. In most cases practical boundaries have been placed on values such as wind direction degrees being within 0 - 360, and wind speed being above 0 however, some reasonable assumptions have been made with regard to valid values, such as atmospheric pressure. 

---
## Packages

#### *OWWeatherDTO:*
Contains the DTO classes generated by the API response POJO. It includes classes for all fields within the API response plus OWWeatherDTO class which acts as the entry point for the object mapper.

#### *OWBadResponseDTO:*
Contains the status code response DTO class.

#### *injector_manager_loader:*
Contains the ConnectionManager class, responsible for generating the various connection URLs. The Injector class calls the API with the given URL and then instantiates the DTO objects with the received data by object mapping the JSON response. It is in the property loader where you will need to stipulate the location of your *.properties* file containing your API key.

#### *frameworktests*
Contains tests run on the framework for quality control.

#### *filemanager*
Contains json files with examples of API responses for both correct and incorrect data, used in the running of framework tests. It also includes a csv file of country codes used by the framework when checking for valid code responses.

#### *cucumber*
Contains the TestRunner class which enables the execution of multiple cucumber feature tests.

#### *cucumber.stepdefs*
contains the stepdef tests for the cucumber features.

#### *resources.features*
contains the gherkin features for each of the DTO classes.

#### *apitests*
Contains selection of example tests that can be run using the framework to test the Open Weather API.

---

## Contributors


[JoAustin312](https://github.com/JoAustin312)

[acharge91](https://github.com/acharge91)

[hibjam](https://github.com/hibjam)

[WillTran02](https://github.com/WillTran02/)

[leehalperin](https://github.com/leehalperin)

[EmemEtteh](https://github.com/EmemEtteh)

[GitMe23](https://github.com/GitMe23)

[AdelaideBaron](https://github.com/AdelaideBaron)

[Farrah-1](https://github.com/Farrah-1 )

[MoshainKhan](https://github.com/MoshainKhan)

[vsampath85](https://github.com/vsampath85)

[AhmedYYS](https://github.com/AhmedYYS)