# ZIMA — versões instaláveis

Este repositório **não tem código**. Ele existe por uma razão só: o iPhone precisa de um
endereço **público** para baixar o `.ipa`, e o repositório do ZIMA é privado.

Aqui ficam duas coisas:

- os `.ipa` de cada build, como *releases*;
- `zima.json`, a **source do AltStore** que aponta para o mais recente.

Tudo é publicado automaticamente pela esteira do repositório privado. Nada aqui é editado à mão.

## Instalar no iPhone

No **AltStore Classic**, aba *Browse* → **+** no canto → adicionar esta URL:

```
https://raw.githubusercontent.com/lucas2331/zima-releases/main/zima.json
```

A partir daí o ZIMA aparece na lista com botão de instalar, e cada build novo aparece como
atualização disponível — sem transferir arquivo para o telefone.

## O que isto não resolve

A assinatura continua expirando em **7 dias**, porque é feita com Apple ID gratuito. Isso é
política da Apple e nenhuma automação muda: só a adesão paga ao Apple Developer Program. O
AltServer re-assina em segundo plano quando o iPhone está na mesma rede do computador com ele
rodando — então, com o AltServer ligado, a renovação cuida de si.

Reassinar nunca apaga dados. **Desinstalar apaga** — o banco é local ao app. Sincronize antes.

## Por que o IPA sai sem assinatura

A esteira compila num runner do GitHub, que não tem certificado nenhum, e não precisa ter: quem
assina é o AltStore, no seu computador, com o seu Apple ID. O que a esteira garante é que os
*entitlements* estão embutidos no binário, porque é deles que o AltStore parte para pedir as
capacidades à Apple.
