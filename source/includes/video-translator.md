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

## Eventos

Você pode tornar um vídeo acessível definindo o atributo ht-data em um elemento de vídeo, primeiramente defina o tipo e caminho do vídeo (obrigatório).

## Utilizando apenas o tradutor de vídeos
```javascript
var ht = new HT({
  token: '<SEU TOKEN>',
  textEnabled: false,
  videoEnabled: true,
  ytEmbedReplace: true,
  videojsReplace: true
});
```

Em alguns casos pode ser necessário adicionar apenas o tradutor de vídeos na página. Geralmente acontece quando a página inteira só possui um vídeo e, estar incorporada em outra página em formato de iframe. Pra isso basta desativar o tradutor de textos, assim o botão de acessibilidade em Libras não irá aparecer nas laterais.


## Replace automático de vídeos

É possível substituir automaticamente os embeds do Youtube e player existentes do Videojs pelo Player Acessível da HandTalk, sempre que uma legenda for encontrada.

### Replace automático de embeds do Youtube

A ferramenta busca por embeds (iframes) do youtube, e substitui por players accesíveis da Hand Talk.

Você pode habilitar o replace automático passando o valor `true` a configuração `ytEmbedReplace` ao instanciar o plugin. Lembrando que você deve também habilitar a feature de vídeo passando `true` na configuração `videoEnabled`.

```javascript
var ht = new HT({
  token: "<TOKEN>",
  videoEnabled: true,
  ytEmbedReplace: true
});
```

```html
<body>
<!-- Pega a ultima versão do plugin Hand Talk -->
<script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

<script>
var ht = new HT({
  // Troque por seu token
  token: "<TOKEN>",
  // ativa/desativa o tradutor de sinais nos players
  videoEnabled: true,
  // ativa/desativa embeds do Youtube
  ytEmbedReplace: true
});
</script>
</body>
```

Se embeds do Youtube forem inseridos após a inicialização do plugin, você deve chamar a função `ht.ytEmbedReplaceAll();` para que os novos vídeos tornem-se acessíveis.
Também é possível efetuar o replace de um único embed com `ht.ytEmbedReplace(elem)`:

```html
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/H2Io3y98FV4" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

<script>
var iframe = document.querySelector('iframe');
ht.ytEmbedReplace(iframe);
</script>
```

Caso o vídeo não possua legenda no idioma `pt-BR` ou `pt` hospedada no Youtube, o mesmo ficará com a funcionalidade de Tradução para Libras bloqueada.

### Replace automático de embeds do Videojs


## Vídeos dinâmicos

### Exemplos

## Legendas
As legendas precisam ser breves e de acordo com o tempo que será utilizado nelas para que o Hugo possa traduzí-las de forma que ele não acelere e não perca a sincronia com o vídeo.

### Exemplos
Abaixo está um exemplo de legenda boa e outro de legenda ruim, respectivamente:


`00:00:04.868 --> 00:00:10.500` </br>
Os grandes feitos da humanidade seriam inúteis se não houvesse a comunicação. 

O exemplo acima retrata uma prática boa para legendas.

`00:00:01.000 --> 00:00:01.500`</br>
Asteroblaudo corria pela rua do alagamento no deserto para poder fugir de um casal de rinocerontes.

Enquanto que o exemplo acima retrata uma prática ruim para legendas.

## Resolvendo conflitos de estilo (css)
É provável que na substituição do elemento `<iframe />` do Youtube, pelo elemento `<div />` com a classe CSS video-js do player da Hand Talk, você perca a referência do elemento no seu CSS e Javascript.

No exemplo ao lado o código CSS espera que o filho da classe video seja um iframe:
>### Exemplo para o código CSS

```html
<style>
  .video {
  width: 800px;
  height: 600px;
}

.video > iframe {
  width: 100%;
  height: 100%;
}
</style>

<body>
  <div class="video">
  <iframe src="https://www.youtube.com/embed/H2Io3y98FV4" frameborder="0"></iframe>
  </div>

  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

  <script>
    var ht = new HT({
      // Troque por seu token
      token: "<TOKEN>",
      // ativa/desativa o tradutor de sinais nos players
      videoEnabled: true,
      // ativa/desativa embeds do Youtube
      ytEmbedReplace: true
    });
  </script>

</body>
```

Ao substituir o elemento `<iframe />` por uma `<div />` a estrutura do site ficará quebrada. A solução seria esperar como filho um elemento com a classe video-js também.

>### Solução para a quebra na estrutura

```html
<style>
.video {
  width: 800px;
  height: 600px;
}

.video > iframe,
.video > .video-js {
  width: 100%;
  height: 100%;
}
</style>

<body>
  <div class="video">
  <iframe src="https://www.youtube.com/embed/H2Io3y98FV4" frameborder="0"></iframe>
  </div>

  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

  <script>
    var ht = new HT({
      // Troque por seu token, exemplo:
      // token: "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
      token: "<TOKEN>",
      videoEnabled: true,
      ytEmbedReplace: true
    });
  </script>
</body>
```