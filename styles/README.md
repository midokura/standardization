# Style
		
Programming style is a set of rules or guidelines used to write a code. Following a particular coding style helps developers read and understand the code conforming to the style, and help to avoid introducing errors.
		
# Midokura Styles
		
The goal of this section is to define Midokura's coding style and format rules. 
		
Every developer is free to decide which tool to use to apply them. To enforce the implementation of the rules, before pushing the code to the main development branch, the code must comply with the defined rules.

## Java

### Code Format and Style 

Midokura uses the [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html).

- [IntelliJ XML Configuration](https://github.com/google/styleguide/blob/gh-pages/intellij-java-google-style.xml)
- [Eclipse XML Configuration](https://github.com/google/styleguide/blob/gh-pages/eclipse-java-google-style.xml)
- [Checkstyle XML Configuration](https://checkstyle.sourceforge.io/google_style.html)

Google has its own tool that developers can use with IntelliJ, Eclipse, Maven, Gradel and an executable JAR.

- [Google Format Tool](https://github.com/google/google-java-format)


**GitHub Action Check**


```yaml
jobs:

    formatting:
        runs-on: ubuntu-latest
        steps:
            - uses: actions/checkout@v2
            - uses: axel-op/googlejavaformat-action@v3
```

### Static and Security Analysis

Midokura uses [Sonar Java Rules](https://rules.sonarsource.com/java).


- [IntelliJ/Eclipse Sonar Lint](https://rules.sonarsource.com/java)
- [Maven Sonar](https://docs.sonarqube.org/latest/analysis/scan/sonarscanner-for-maven/)
- [Gradel Sonar](https://docs.sonarqube.org/latest/analysis/scan/sonarscanner-for-gradle/)
- [Sonnar Scanner](https://docs.sonarqube.org/latest/analysis/scan/sonarscanner/)

**GitHub Action Check**

```yaml
jobs:

    sonar:
        runs-on: ubuntu-latest
        steps:
            - uses: actions/checkout@v2
            - uses: actions/setup-java@v2
              with:
                distribution: 'temurin'
                java-version: '17'
            - name: Test and Package
              run: mvn clean verify sonar:sonar
              env:
                GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
                SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}
```









