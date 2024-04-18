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

```bash

    repositories {
        google()
        mavenCentral()
        maven {
            name = "GitHubPackages"
            url = uri("https://maven.pkg.github.com/paystore/pix-sdk")

            credentials {
                username = "manoelneto83"
                password = "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"
            }
        }

    }
}
```

Após isso basta adicionar a dependência no build.gradle.kts do modulo (app):

```bash
implementation ("com.phoebus.libraries:pix-sdk:1.0.0.0")
```

pronto sua aplicação já pode utilizar os recursos da lib. Para maiores detalhes veja a doc: [Paystore Android SDK](http://177.69.97.18:6655/ "")
