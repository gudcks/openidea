# Independent Gradle builds demo

This folder intentionally has no root Gradle build. `alpha` and `beta` are independent Gradle 8.10.1 builds; each includes an `:app` project with an `identify` task. It contains no company code or data.

1. Open this parent folder in OpenIDEA.
2. Use Link Gradle Projects to select both settings.gradle files.
3. Run beta → app → verification → identify. Expected: BUILD=beta;PROJECT=:app.
4. Unlink beta and confirm alpha remains. Unlink alpha and confirm Link is still available.
5. Link both again and reopen the project to verify persistence.

CLI check: run `./gradlew :app:identify` from either build directory. The first run may download Gradle; no external libraries or services are used.
