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
2. Load the configuration
``` go
    configLoader := config.NewLoader(configPath)

	config := &models.Config{}

	err := configLoader.Load(yaml.Unmarshal, config)
	if err != nil {
		panic(err)
	}
```
