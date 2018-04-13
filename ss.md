
//////////////////////////////////////
buildscript {
    repositories {
        maven {
            url 'http://rbcnexus.fg.rbc.com:8081/nexus/content/repositories/gradle-plugins-m2/'
        }
    }
}

plugins {
    id 'java' }

group 'com.rbc'
version '1.0-SNAPSHOT'


project.ext {
    cucumberVersion = '2.3.1'
    cucumberProVersion = '2.0.4'
    junitVersion = '4.12'
}


sourceCompatibility = 1.8

repositories {
    maven {
        url 'http://rbcnexus.fg.rbc.com:8081/nexus/content/repositories/central/'
    }

}

dependencies {
    testCompile 'io.cucumber:cucumber-java:' + cucumberVersion
    testCompile 'io.cucumber:cucumber-junit:' + cucumberVersion
    testCompile 'io.cucumber:pro-plugin:' + cucumberProVersion
    testCompile 'junit:junit:' + junitVersion
    testCompile group: 'io.rest-assured', name: 'rest-assured', version: '3.0.7'
    testCompile 'io.rest-assured:rest-assured:3.0.7'
    testCompile "com.github.tomakehurst:wiremock:2.14.0"
    compile group: 'org.apache.commons', name: 'commons-csv', version: '1.5'
    compile group: 'org.seleniumhq.selenium', name: 'selenium-java', version: '3.11.0'
    compile group: 'org.yaml', name: 'snakeyaml', version: '1.20'
    compile group: 'org.springframework', name: 'spring-beans', version: '3.0.5.RELEASE'
    compile group: 'org.springframework', name: 'spring-core', version: '5.0.5.RELEASE'
    compile group: 'org.springframework', name: 'spring-context', version: '5.0.5.RELEASE'

}


test {
    systemProperty "cucumber.options", System.properties.getProperty("cucumber.options")
}

/////////////////////////////
