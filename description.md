# Deployment
In order to run both server and client, the following commands need to be executed:
```bash
./gradlew :server:build
./gradlew :server:bootRun
```

After that, we can build and deploy the client:
```bash
./gradlew :client:build
./gradlew :client:bootRun
```

# Fixing the code
After reproducing [Deployment](#deployment) steps, an error will appear because `translation()` is not implemented. Hence, to implement this function it is necessary to write this code:

```Kotlin
fun translation(@RequestPayload request: TranslationRequest): TranslationResponse = 
        TranslationResponse().apply {
            translation = "¡Tradúceme!"
        }
```