# Full-Identity-SDK-Android

## Installation

## Step 1
```sh
#Create a github.properties file in the root folder of android. Path should be like below: E.g. "myReactApp/android/github.properties"

# Add the following in github.properties:
USERNAME_GITHUB=MyUsernameOnGithub
TOKEN_GITHUB=TokenFromGithubClassicToken
```

## Step 2: build.gradle (app)
```sh


def githubPropertiesFile = rootProject.file("github.properties")
def githubProperties = new Properties()
githubProperties.load(new FileInputStream(githubPropertiesFile))

android{
  ...
}

repositories {
        maven {
            name "GitHubPackages"
            url 'https://maven.pkg.github.com/Blusalt-FS/Liveness-Only-Android-Package'

            credentials {
                username githubProperties['USERNAME_GITHUB']
                password githubProperties['TOKEN_GITHUB']
            }
        }

        maven {
            name "GitHubPackages"
            url 'https://maven.pkg.github.com/Blusalt-FS/Blusalt_Document_Verification-Android-Package'

            credentials {
                username githubProperties['USERNAME_GITHUB']
                password githubProperties['TOKEN_GITHUB']
            }
        }

        maven {
            name "GitHubPackages"
            url 'https://maven.pkg.github.com/Blusalt-FS/Full-Identity-SDK-Android-Package'

            credentials {
                username githubProperties['USERNAME_GITHUB']
                password githubProperties['TOKEN_GITHUB']
            }
        }
}

dependencies{
    implementation 'net.blusalt:full_identity_sdk:1.0-1'
  
    implementation 'net.blusalt:identity_document_verification:1.1-0'
    implementation 'net.blusalt:liveness_android_data:1.4-7'
    implementation 'net.blusalt:liveness_android_core:1.4-7'
}
```
