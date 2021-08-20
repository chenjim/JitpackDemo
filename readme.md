### jitpack demo

> https://jitpack.io/ 仓库使用示例

1. 增加 jitpack.yml 使用jdk11

2. build.gradle 中增加 `maven { url 'https://jitpack.io' }`

3. settings.gradle 中增加 `maven { url 'https://jitpack.io' }`

4. ./jplib/build.gradle 增加 `id 'maven-publish'`  同时增加

```
afterEvaluate {
    publishing {
        publications {
            // Creates a Maven publication called "release".
            release(MavenPublication) {
                from components.release
                groupId = 'org.mediasoup.droid'
                artifactId = 'mediasoup-client'
                version = '0.0.7'
            }
        }
    }
}
```