
Maven Build LifeCycle
---------------------
<img src="/imgs/maven-life-cycle-diagram.png" alt="">

Link for maven build lifecycle
-------------------------------
https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html#Lifecycle_Reference



concept about pom.xml
----------------------
    
    root tag/element name is project
    
    <project>
   
    Its consist following elements
    1) <properties></properties>            --to configure properties
    2) <dependencies></dependencies>        --to configure jar/dependency
    3) <repository></repository>            --to configure reposioty from where mnaven will download the jar.    
    4) <pluginrepository></pluginrepository> --to repository for plugin jar
    5) <build></build>                       --to configure build plan
    6) <profiles></profiles>                -- to configure evn respective build plan
    7) <reporting></reporting>              -- to get report as per need.
     
     </project>


    1) <properties></properties>
    ------------------------
    
    This uses to provide properties inside build life cycles.
    
    example:
      <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
      </properties>
      
    here property name is project.build.sourceEncoding value is UTF-8
    inside pom anywhere you can get value of property using ${property-name}  
    example:
    ${project.build.sourceEncoding}
    
    There are alot of inbuilt propertry in maven that helps developer work with Maven.
    1) ${basedir} return path of project.
    Java System properties also can be use as inbuit properties like ${user.home}

click here to more details
--------------------------
https://maven.apache.org/archives/maven-1.x/reference/properties.html
    
    
    2) <dependencies></dependencies>
    ----------------------------------

    This is use to maintain dependecy liberary(jar) file.
    in java project are also dependent upon some external /internal lib(jar file) to include those jar file automatically into project we have defined as dependecy.
    Maven assume also java project can be work as dependecy to other.
    To make java project/lib/dependency as unique identifier maven introduction following terms
    1)groupId        This similer to java package name of any class.
    2)artifactId     This is similer to class name. 
    3)version        This is version of the project
    
    
    example
    
    <dependencies>
    
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>3.8.1</version>
      <scope>test</scope>
    </dependency>
    
    </dependencies>
 
    Maven automatically downlaod junit jar (from maven-central-repositoty) and cofigure into project.
    