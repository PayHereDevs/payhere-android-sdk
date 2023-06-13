## Publishing SDK to GitHub packages

1. Create an account in GitHub or add your existing account as part of PayHereLK GitHub organization
2. Generate Personal Access Token (PAT) with `write:packages` and `read:packages` permissions. Steps to generate PATs described [here](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token).
3. create ~/.gradle/gradle.properties file (if not exist and add the following lines)

```
github.user=<Your GitHub username>
github.token=<Generated PAT value>

ex:I
github.user=chamikaPH
github.token=ghp_11111111555555AAAAAAAAAAAAAAAABBBBBB
```

4. Set the necessary SDK release version at `sdk_version` in `./androidsdk/build.gradle`
5. Run following command to publish to GitHub packages. (or just run `sh upload.sh`)

```
./gradlew --no-configure-on-demand --no-parallel :clean :androidsdk:assembleRelease :androidsdk:publishReleasePublicationToGitHubPackagesRepository
```  

## Publishing SDK to Repsy

1. create ~/.gradle/gradle.properties file (if not exist and add the following lines)

```
repsy.user=<Your Repsy username>
repsy.password=<Your Repsy password>

ex:I
repsy.user=payhere
repsy.password=XXXXXXXX
```

2. Set the necessary SDK release version at `sdk_version` in `./androidsdk/build.gradle`
3. Run following command to publish to Repsy maven repository. (or just run `sh upload.sh`)

```
./gradlew --no-configure-on-demand --no-parallel :clean :androidsdk:assembleRelease :androidsdk:publishReleasePublicationToRepsyRepository
```  