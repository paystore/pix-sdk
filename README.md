# pix-sdk é uma biblioteca que integra o pagamento via pix para applicativos de parceiros

Para utilizar a lib em um aplicativo de parceiro basta realizar a configuração no arquivo *settings.gradle.tks* (ou equivalente em gradle) de onde a aplicação deve buscar a lib, veja:

```bash

    repositories {
        google()
        mavenCentral()
        ...
        //adicionar a configuação do GitHubPackages aqui.    
    }
}
```

deve ser adicionando a configuração do GitHubPackages

```java
import java.io.File
import java.util.Properties
import java.io.FileInputStream

    repositories {
        google()
        mavenCentral()
        maven {
            val githubProperties = Properties()
            githubProperties.load(FileInputStream(File("github.properties")))
            //obter as credenciais junto a phoebus
            val gprUser = githubProperties.getProperty("USER") 
            val token = githubProperties.getProperty("TOKEN")
            name = "GitHubPackages"
            url = uri("https://maven.pkg.github.com/paystore/pix-sdk")

            credentials {
                username = gprUser
                password = token
            }
        }

    }
}
```

na raiz do projeto deve ser criado um arquivo chamado *github.properties* com o seguinte conteúdo:

```bash
USER = manoelneto83
TOKEN = obter na doc da phoebus
```
Após isso basta adicionar a dependência no build.gradle.kts do modulo (app):

```bash
implementation ("com.phoebus.libraries:pix-sdk:1.0.0.0")
```

pronto sua aplicação já pode utilizar os recursos da lib. Para maiores detalhes veja a doc: [Paystore Android SDK](http://177.69.97.18:6655/ "")
