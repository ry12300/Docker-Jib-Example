# Docker Goolge Jib Example
Simple Spring Boot application highlighting the use of the Google Jib container tool.

https://cloud.google.com/java/getting-started/jib

Jib plugin allows a Docker Image to be created without creating a DockerFile within a project.

Follow the below steps to create a docker image of this application and push the image to your docker hub account.

1. Within the pom.xml add the following and replace with your credentials:


			<plugin>
				<groupId>com.google.cloud.tools</groupId>
				<artifactId>jib-maven-plugin</artifactId>
				<version>2.8.0</version>
				<configuration>
				  <to>
				    <image>registry.hub.docker.com/YOUR_USER_NAME/IMAGE_NAME</image>
				  </to>
				</configuration>
			</plugin>
      
2. In your local maven settings file add the following, again replacing with your docker hub credentials:
      ```
      <server>
		      <id>registry.hub.docker.com</id>
		      <username>username</username>
		      <password>password</password>
	  </server>
      ```
      

3. Run  ```mvn clean compile jib:build ```

4. Check your Docker Hub account - your image should of been pushed.

5. You can now pull the image and run the container as usual.
