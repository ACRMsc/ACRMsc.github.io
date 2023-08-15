## [ACRM (Tool)](https://github.com/ACRMsc/ACRMsc.github.io)

## Introduction 

The undocumented evolution of a software project and its underlying architecture underscores the need to recover the architecture from the software's implementation-level artifacts. 
Despite the existence of various software remodularization techniques, they often suffer from inaccuracies and evaluating their effectiveness is challenging due to the absence of accurate "ground-truth" architectures or reference models.
In this paper, we propose **A**utomated **C**onstruction of **R**eference **M**odel (ACRM), an approach for automatically constructing reference models for various software projects using the metadata of all software versions and historical maintenance records. 
We evaluate ACRM through both quantitative and qualitative analysis. 
The experiment results provide quantitative validation and show that the generated reference models are reasonable, as confirmed by the relationship between proposed reference models and architecture-level bugs or code smells. 
We also conduct a qualitative study, involving industrial developers and students, which further validates the generated reference models. 
The survey shows that, on average, 89% of the participants agree with the reference models generated by ACRM. 
Moreover, we propose an improved metric, *wc2c*, which analyze the strengths and weaknesses of different types of software clustering techniques using the proposed reference models of the analyzed software. 
Finally, we discuss the potential benefits of using ACRM in analyzed projects, particularly in terms of improving software quality, reducing maintenance costs, and enhancing developer productivity.

## Studied Subject

| ID | Project | \# Versions | \# Major Versions | \# Stars | KLOC (Avg) | \# Classes (Avg) | Commits |
|:---: |:----: |:----: |:----:  |:----:  |:----:  |:----:  |:----:  |
| 1  | [Activemq](https://github.com/apache/activemq)                               | 64         | 2 | 1,764 | 324.9 | 3,057 | 11,309 |
| 2  | [Activemq-artemis](https://github.com/apache/activemq-artemis)               | 32         | 2 | 602 | 518.3 | 3,324 | 9,680|			
| 3  | [Aeron](https://github.com/real-logic/aeron)                                 | 86         | 2 | 5,065 | 51.1 | 330 | 15,842 |		
| 4  | [Alluxio](https://github.com/Alluxio/alluxio)                                | 62         | 3 | 4,613 | 248.0 | 916 | 30,937 |	
| 5  | [Apktool](https://github.com/iBotPeaches/Apktool)                            | 34         | 2 | 10,220 | 16.6 | 179 | 1,648 |
| 6  | [Assertj-core](https://github.com/assertj/assertj-core)                      | 50         | 3 | 1,756 | 109.9 | 2,600 | 2,870 |
| 7  | [Atmosphere](https://github.com/Atmosphere/atmosphere)                       | 204        | 3 | 3,430 | 40.6 | 259 | 5,931 |
| 8  | [Atomix](https://github.com/atomix/atomix)                                   | 95 | 3 | 1,901 | 55.6 | 619 | 4,265 |	
| 9  | [AxonFramework](https://github.com/AxonFramework/AxonFramework)              | 99 | 4 | 2,020 | 93.0 | 724 | 5,951 |	
| 10 | [Beam](https://github.com/apache/beam)                                       | 83 | 2 | 3,998 | 389.6 | 1,063 | 27,132 |
| 11 | [Bisq](https://github.com/bisq-network/bisq)                                 | 86 | 2 | 3,102 | 111.1 | 892 | 11,168 |
| 12 | [Byte-buddy](https://github.com/raphw/byte-buddy)                            | 202 | 2 | 3,485 | 117.0 | 581 | 5,200 |
| 13 | [Calcite](https://github.com/apache/calcite)                                 | 52 | 2 | 1,894 | 211.5 | 869 | 4,175 |
| 14 | [Camel](https://github.com/apache/camel)                                     |	154 | 3 | 3,242 | 680.0 | 7,981 | 45,096 |
| 15 | [Cas](https://github.com/apereo/cas)                                         | 218 |	4 | 7,620 | 91.1 | 1,219 | 16,869 |
| 16 | [Cassandra](https://github.com/apache/cassandra)                             | 241 | 4 | 5,950 | 189.2 | 775 | 25,297 |
| 17 | [Conversations](https://github.com/iNPUTmice/Conversations)                  | 215 | 3 | 3,541 | 54.6 | 150 | 6,274 |
| 18 | [Cxf](https://github.com/apache/cxf)                                         | 153 | 2 | 642 | 527.7 | 4,618 | 15,722 |
| 19 | [Dbeaver](https://github.com/dbeaver/dbeaver)                                | 108 | 4 | 13,652 | 286.0 | 2,233 | 16,052 |
| 20 | [Debezium](https://github.com/debezium/debezium)                             | 73 | 2 | 3,265 | 75.5 | 363 | 3,125 |
| 21 | [Discovery](https://github.com/Nepxion/Discovery)                            | 76 | 3 | 2,954 | 17.4 | 289 | 2,403 |
| 22 | [Dropwizard](https://github.com/dropwizard/dropwizard)                       | 147 | 3 | 7,657 | 44.0 | 509 | 5,430 |
| 23 | [Eclim](https://github.com/ervandew/eclim)                                   | 76 | 2 | 1,026 | 33.2 | 326 | 4,849 |
| 24 | [Flink](https://github.com/apache/flink)                                     | 101 | 2 | 13,149 | 698.3 | 4,037 | 22,170 |
| 25 | [Fresco](https://github.com/facebook/fresco)                                 | 40 | 2 | 16,207 | 89.2 | 547 | 2,531 |
| 26 | [Grakn](https://github.com/ranscoupcoli1970/grakn)                           | 45 | 2 | 2,107 | 76.6 | 570 | 4,291 |
| 27 | [Guacamole-client](https://github.com/apache/guacamole-client)               | 33 | 2 | 1,004 | 19.5 | 281 | 5,378 |
| 28 | [Hadoop](https://github.com/apache/hadoop)                                   | 293 | 4 | 10,489 | 972.6 | 1,784 | 23,874 |
| 29 | [Hawtio](https://github.com/hawtio/hawtio)                                   | 137 | 2 | 1,138 | 63.3 | 199 | 8,803 |
| 30 | [Hive](https://github.com/apache/hive)                                       | 40 | 2 | 3,174 | 850.3 | 2,345 | 14,501 |
| 31 | [Java-tron](https://github.com/tronprotocol/java-tron)                       | 51 | 3 | 2,380 | 80.2 | 849 | 14,129 |
| 32 | [karaf](https://github.com/apache/karaf)                                     | 82 | 3 | 480 | 80.0 | 655 | 8,197 |
| 33 | [Maxwell](https://github.com/zendesk/maxwell)                                | 170 | 2 | 2,141 | 68.8 | 123 | 3,110 |
| 34 | [Nifi](https://github.com/apache/nifi)                                       | 88 | 2 | 2,066 | 60.1 | 693 | 5,286 |
| 35 | [Okhttp](https://github.com/square/okhttp)                                   | 95 | 4 | 37252 | 50.3 | 167 | 4645 |
| 36 | [Openapi-generator](https://github.com/OpenAPITools/openapi-generator)       | 53 | 3 | 5,446 | 374.2 | 542 | 14,218 |
| 37 | [Orientdb](https://github.com/orientechnologies/orientdb)                    | 157 | 3 | 4,154 | 368.1 | 2,329 | 19,352 |
| 38 | [Pdfbox](https://github.com/apache/pdfbox)                                   | 52 | 2 | 1,162 | 134.7 | 939 | 8,962 |
| 39 | [Pmd](https://github.com/pmd/pmd)                                            | 70 | 2 | 2,887 | 184.3 | 1,415 | 16,532 |
| 40 | [Powermock](https://github.com/powermock/powermock)                          | 42 | 2 | 3,121 | 36.8 | 590 | 1,607 |
| 41 | [Redisson](https://github.com/redisson/redisson)                             | 163 | 3 | 13,242 | 74.7 | 486 | 5,675 | 
| 42 | [Rest-assured](https://github.com/rest-assured/rest-assured)                 | 56 | 3 | 4,748 | 20.0 | 180 | 1,959 |
| 43 | [Speedment](https://github.com/speedment/speedment)                          | 67 | 2 | 1,832 | 95.3 | 1,537 | 4,674 |
| 44 | [Spotbugs](https://github.com/spotbugs/spotbugs)                             | 41 | 2 | 1,894 | 227.6 | 1,891 | 16,206 |
| 45 | [Spring-framework](https://github.com/spring-projects/spring-framework)      | 175 | 3 | 37,411 | 502.5 | 3,773 | 20,896 |
| 46 | [Spring-security](https://github.com/spring-projects/spring-security)        | 143 | 4 | 4,843 | 145.0 | 1,231 | 8,732 | 
| 47 | [Storm](https://github.com/apache/storm)                                     | 33 | 2 | 6,078 | 160.0 | 920 | 10,316  | 
| 48 | [Testcontainers-java](https://github.com/testcontainers/testcontainers-java) | 73 | 2 | 3,805 | 8.3 | 175 | 2,008 |
| 49 | [Tika](https://github.com/apache/tika)                                       | 56 | 2 | 1,002 | 82.0 | 526 | 4,747 | 
| 50 | [Traccar](https://github.com/traccar/traccar)                                | 31 | 2 | 2,392 | 25.9 | 415 | 6,227 |

## Empirical Analysis

<img width="26" alt="dl" src="https://user-images.githubusercontent.com/104186731/168603749-1422d6db-921f-4976-8b95-5f77ca20bc5f.png">
[Empirical Analysis.zip](https://github.com/ACRMsc/ACRMsc.github.io/files/12345005/Empirical.Analysis.zip)



<img width="26" alt="dl" src="https://user-images.githubusercontent.com/104186731/168603749-1422d6db-921f-4976-8b95-5f77ca20bc5f.png"> 
[The analysis results for move refactoring operations of core and peripheral developers.xlsx](https://github.com/ACRMsc/ACRMsc.github.io/files/11672600/The.analysis.results.for.move.refactoring.operations.of.peripheral.developers.xlsx)


## Reasonability of Reference Model (RQ1)

### Quantitative evaluation

<img width="26" alt="dl" src="https://user-images.githubusercontent.com/104186731/168603749-1422d6db-921f-4976-8b95-5f77ca20bc5f.png">
[Statistical results for the location weight distribution of classes of the reference model, number of bugs, and architectural smells.xlsx](https://github.com/ACRMsc/ACRMsc.github.io/files/10895072/Statistical.results.for.the.location.weight.distribution.of.classes.of.the.reference.model.number.of.bugs.and.architectural.smells.xlsx)

<img width="26" alt="dl" src="https://user-images.githubusercontent.com/104186731/168603749-1422d6db-921f-4976-8b95-5f77ca20bc5f.png"> 
[Spearman rank correlation between the location weights of classes in reference models and architectural smells or bugs.xlsx](https://github.com/ACRMsc/ACRMsc.github.io/files/10895074/Spearman.rank.correlation.between.the.location.weights.of.classes.in.reference.models.and.architectural.smells.or.bugs.xlsx)





### Qualitative evaluation

<img width="26" alt="dl" src="https://user-images.githubusercontent.com/104186731/168603749-1422d6db-921f-4976-8b95-5f77ca20bc5f.png"> [Questionnair.zip](https://github.com/ACRMsc/ACRMsc.github.io/files/10916722/Questionnair.zip)


## Applicability of Reference Model (RQ2)

<img width="26" alt="dl" src="https://user-images.githubusercontent.com/104186731/168603749-1422d6db-921f-4976-8b95-5f77ca20bc5f.png">
[wc2c_cvg results.xlsx](https://github.com/ACRMsc/ACRMsc.github.io/files/10895084/wc2c_cvg.results.xlsx)

<img width="26" alt="dl" src="https://user-images.githubusercontent.com/104186731/168603749-1422d6db-921f-4976-8b95-5f77ca20bc5f.png">
[c2c_cvg.results.xlsx](https://github.com/ACRMsc/ACRMsc.github.io/files/11632885/c2c_cvg.results.xlsx)


