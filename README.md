# Go Configuration Manager

## Installation
```go get https://gitlab.com/rosenpin/config-manager```

## Usage
1. Create a configuration struct for your project. IE: models.Config
``` go
    type Config struct {
        Path
        Port
        Username
        ...
    }
```
2. Create the configuration file. IE: config.yaml
``` yaml
Path: /home/user/projectpath
Port: 8080
Username: rosenpin
```
3. Load the configuration
``` go
configLoader := config.NewLoader("config.yaml")

config := &models.Config{}

err := configLoader.Load(yaml.Unmarshal, config) 
if err != nil {
    panic(err)
}
```
