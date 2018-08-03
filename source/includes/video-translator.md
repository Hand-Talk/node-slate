# Tradutor de Vídeos

## Começando

> ### Exemplo de Instalação <br /> 
Troque `<TOKEN>` por seu token de acesso
 
```javascript
var ht = new HT({
  // Troque por seu token, exemplo:
  // token: "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
  token: "<TOKEN>",
  // Habilita o Tradutor de Vídeos
  videoEnabled: true
});
```

```html
  <body>

    <!-- Troque os campos <VIDEO_TYPE>, <VIDEO_URL>, <CAPTION_TYPE> e <CAPTION_URL>, pelos dados solicitados-->
    <video data-ht="src=<VIDEO_TYPE>:<VIDEO_URL>;subtitle=<CAPTION_TYPE>:<CAPTION_URL>"></video>

    <!-- Pega a ultima versão do plugin Hand Talk -->
    <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

    <script>
    var ht = new HT({
      // Troque por seu token, exemplo:
      // token: "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
      token: "<TOKEN>",
      // Habilita o Tradutor de Vídeos
      videoEnabled: true
    });
    </script>
  </body>
```

Para começar a utilizar o Tradutor de Vídeos, você deve inserir o script da Hand Talk e instanciar a classe HT, passando por parâmetro um dicionário com o token e demais configurações.

No exemplo de instalação à direita, utilizamos a última versão do script hospedado em https://api.handtalk.me/plugin/latest/handtalk.min.js, após inserir o script da Hand Talk instanciamos a classe `HT` passando por parâmetro um dicionário com o `token` e `videoEnabled` para habilitar o Tradutor de Vídeos.

Sem a flag `videoEnabled` ativada, o Tradutor de Vídeos não irá funcionar.

Com o plugin devidamente configurado, siga os passos da sessão abaixo para implementar o Player Acessível.

## Utilizando o Player Acessível

O plugin oferece um player de vídeo acessível em Libras, que suporta os seguintes **Techs**:

- MP4;
- OGG;
- WEBM;
- Youtube;
- Vimeo;
- SambaTech.

Os tipos de legenda suportados são:

- VTT;
- SRT.

<aside class="info">
Nota: Para utilizar o player acessível, certifique-se de estar com o plugin devidamente configurado de acordo com a sessão **Começando** (logo acima).
</aside>

```html
<video data-ht="src=<VIDEO_TECH>:<VIDEO_URL>;subtitle=<CAPTIONS_TYPE>:<CAPTIONS_URL>"></video>
```

Você pode tornar um vídeo acessível definindo o atributo `ht-data` em um elemento de vídeo, primeiramente defina o tech e caminho do vídeo (obrigatório).

`src=<VIDEO_TECH>:<VIDEO_URL>`

Em seguida, separando por ponto e virgula `;`, defina o tipo e caminho da legenda. (opcional)

`subtitle=<CAPTIONS_TYPE>:<CAPTIONS_URL>`

> ### Exemplo: Criando um vídeo **tech** youtube

```html
<!-- Torna o vídeo https://www.youtube.com/watch?v=H2Io3y98FV4 acessivel -->
<video data-ht="src=youtube:H2Io3y98FV4"></video>
```

Caso o campo subtitle fique em branco em um src do tipo youtube, a legenda será obtida automaticamente. Como no exemplo ao lado.
  
Também é possível substituir automaticamente os embeds do Youtube e player existentes do Videojs pelo player acessível da HandTalk, sempre que uma legenda for encontrada.

O usuário pode clicar no ícone que representa a acessibilidade em língua de sinais para iniciar o vídeo junto com a tradução do Hugo, ou apenas clicar no botão central para assistir o vídeo sem acessibilidade.

### Exemplos

## Utilizando apenas o tradutor de vídeos

### Exemplos

## Replace automático de vídeos

### Exemplos

## Vídeos dinâmicos

### Exemplos

## Legendas
(boas praticas e exemplos)

## Resolvendo conflitos de estilo (css)
