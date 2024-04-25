# Projeto criado para consumir a api de geração de imagem do Spring AI

### Documentação do Spring AI
https://docs.spring.io/spring-ai/reference/api/clients/image/openai-image.html

### Observação:

Atualmente, o Spring AI não é distribuído no repositório central, mas sim no próprio repositório Maven do Spring. Portanto, para incluí-lo, você precisa adicionar o endereço do repositório do Spring no arquivo pom.xml.

Logo abaixo da tag ``<java.version>17</java.version>``, que fica dentro da tag ``<properties></properties>``é necessário adicionar a versão do Spring AI

```
<properties>
		<java.version>17</java.version>
		<spring-ai.version>0.8.1</spring-ai.version>
	</properties>
```

Logo após a tag ``</dependencies>`` adicione a dependência do Spring IA desta forma:

```
<dependencyManagement>
		<dependencies>
			<dependency>
				<groupId>org.springframework.ai</groupId>
				<artifactId>spring-ai-bom</artifactId>
				<version>${spring-ai.version}</version>
				<type>pom</type>
				<scope>import</scope>
			</dependency>
		</dependencies>
	</dependencyManagement>
```
Por último, após a tag ``</build>`` adicione este repository:

```
<repositories>
		<repository>
			<id>spring-milestones</id>
			<name>Spring Milestones</name>
			<url>https://repo.spring.io/milestone</url>
			<snapshots>
				<enabled>false</enabled>
			</snapshots>
		</repository>
	</repositories>
```

