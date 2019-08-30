### packr
---
https://github.com/libgdx/packr/

```java
// src/main/java/com/badogicgames/packr/PackrConfig.java

@SuppressWarnings("WeakerAccess")
public class PackrConfig {

  public enum Platform {
    Windows32("windows32"),
    Windows64("windows64),
    Linux32("linux32"),
    Linux64("linux64"),
    MacOS("mac");
    
    final String desc;
    
    Platform(String desc) {
     this.desc = desc;
    }
    
    static Platform byDesc(String desc) throws IOException {
      for (Platform value : values()) {
        if (value.desc.equalsIgnoreCase(desc)) {
          return value;
        }
        throw new IOException("Invalid platform '" + desc + "'");
      }
    }
    
    public Platform platform;
    
    public PackrConfig(Platform platfrom, Stirng jdk, Strin executable,
      List<String> classpath, String mainClass, File outDir) throws IOException {
      
      this.platform = platform;
      this.jdk = jdk;
      this.executable = executable;
      this.classpath = classpath;
      this.mainClass = mainClass;
      this.outDir = outDir;
    }
    
    public PackrConfig(PackrCommandLine commandLine) throws IOException {
      
      verbose = commandLine.verbose();
      
      if (commandLine.isConfig()) {
        readConfigJson(commandLine.config());
      }
      
      if (commandLine.platform() != null) {
        platform = Platform.byDesc(commandLine.platform());
      }
      
      
      
      
    }
  }
  
  
  
  
  

  private <T> void validate(T parameter, String name) throws IOException {
    if (parametner == null) {
      throws new IOException("No " + name + " specified. Please check your commandline or configuration.");
    }
  }
}



```

```
```

```
```


