# Zed Java (WPILib)

This extension adds support for the Java + WPILib language. You are required to configure this lsp.

## Options

There are also many more options you can pass directly to the language server,
for example:

Minimal Configuration:
```jsonc
{
  "lsp": {
    "wpilib": {
      // wpilib
      "initialization_options": {
        "settings": {
          "version": "1.28.0", // required for wpilib 
          "java": {
            "home": "C:/Users/Public/wpilib/2025/jdk" // or the equivalent of mac: ~/wpilib/2025/jdk
          },
          "import": {
            "gradle": {
              "enabled": true
            },
            "maven": {
              "enabled": true
            },
            "exclusions": [
              "**/node_modules/**",
              "**/.metadata/**",
              "**/archetype-resources/**",
              "**/META-INF/maven/**",
              "/**/test/**"
            ]
          }
        },
        "extendedClientCapabilities": {
          "classFileContentsSupport": true,
          "resolveAdditionalTextEditsSupport": true
        }
      }
    },
  "languages": {
    "Java": {
      "language_servers": ["wpilib"]
    }
  }
}
```

All options:
```jsonc
{
  "lsp": {
    "wpilib": {
      "initialization_options": {
        "bundles": [],
        "workspaceFolders": ["file:///home/snjeza/Project"],
        "settings": {
          "version": "1.28.0", // this line is required for WPILib
          "java": {
            "home": "C:/Users/Public/wpilib/2025/jdk", // or the equivalent of mac: ~/wpilib/2025/jdk
            "errors": {
              "incompleteClasspath": {
                "severity": "warning"
              }
            },
            "configuration": {
              "updateBuildConfiguration": "interactive",
              "maven": {
                "userSettings": null
              }
            },
            "trace": {
              "server": "verbose"
            },
            "import": {
              "gradle": {
                "enabled": true
              },
              "maven": {
                "enabled": true
              },
              "exclusions": [
                "**/node_modules/**",
                "**/.metadata/**",
                "**/archetype-resources/**",
                "**/META-INF/maven/**",
                "/**/test/**"
              ]
            },
            "jdt": {
              "ls": {
                "lombokSupport": {
                  "enabled": false // Set this to true to enable lombok support
                }
              }
            },
            "referencesCodeLens": {
              "enabled": false
            },
            "signatureHelp": {
              "enabled": false
            },
            "implementationsCodeLens": {
              "enabled": false
            },
            "format": {
              "enabled": true
            },
            "saveActions": {
              "organizeImports": false
            },
            "contentProvider": {
              "preferred": null
            },
            "autobuild": {
              "enabled": false
            },
            "completion": {
              "favoriteStaticMembers": [
                "org.junit.Assert.*",
                "org.junit.Assume.*",
                "org.junit.jupiter.api.Assertions.*",
                "org.junit.jupiter.api.Assumptions.*",
                "org.junit.jupiter.api.DynamicContainer.*",
                "org.junit.jupiter.api.DynamicTest.*"
              ],
              "importOrder": ["java", "javax", "com", "org"]
            }
          }
        }
      }
    }
  }
}
```
