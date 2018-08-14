# Tradutor de Vídeos

## Começando

> Exemplo de Instalação
 
```javascript
var ht = new HT({
  // Troque por seu token de acesso
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
    // Troque por seu token de acesso
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
Nota: Para utilizar o player acessível, certifique-se de estar com o plugin devidamente configurado de acordo com a sessão [Tradutor de Vídeos > Começando](index.html?html#come-ando14).
</aside>


Você pode tornar um vídeo acessível definindo o atributo `ht-data` em um elemento de vídeo, primeiramente defina o tech e caminho do vídeo (obrigatório).

`src=<VIDEO_TECH>:<VIDEO_URL>`

```html
<video data-ht="src=<VIDEO_TECH>:<VIDEO_URL>;subtitle=<CAPTIONS_TYPE>:<CAPTIONS_URL>"></video>
```

```javascript
// Confira o exemplo em html
```

Em seguida, separando por ponto e virgula (`;`), defina o tipo e caminho da legenda. (opcional)

`subtitle=<CAPTIONS_TYPE>:<CAPTIONS_URL>`

## Utilizando Apenas o Tradutor de Vídeos

> Exemplo de Utilização

```javascript
var ht = new HT({
  // Troque por seu token de acesso
  token: '<SEU TOKEN>',
  // Se true, exibe o tradutor de sites para texto
  textEnabled: false,
  // Habilita o tradutor de sinais nos players
  videoEnabled: true

  // Use as linhas abaixo para replace automatico de vídeos

  // Efetua replace de embeds do youtube automaticamente ao ser inicializado.
  //ytEmbedReplace: true,
  // Efetua replace de players existentes do videojs automaticamente ao ser inicializado.
  //videojsReplace: true
});
```

```html
<body>

  <!-- Troque os campos <VIDEO_TYPE>, <VIDEO_URL>, <CAPTION_TYPE> e <CAPTION_URL>, pelos dados solicitados -->
  <video data-ht="src=<VIDEO_TYPE>:<VIDEO_URL>;subtitle=<CAPTION_TYPE>:<CAPTION_URL>"></video>

  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

  <script>
    var ht = new HT({
      // Troque por seu token de acesso
      token: '<SEU TOKEN>',
      // Se true, exibe o tradutor de sites para texto
      textEnabled: false,
      // Habilita o tradutor de vídeos
      videoEnabled: true

      // Use as linhas abaixo para replace automatico de vídeos

      // Efetua replace de embeds do youtube automaticamente ao ser inicializado.
      //ytEmbedReplace: true,
      // Efetua replace de players existentes do videojs automaticamente ao ser inicializado.
      //videojsReplace: true
    });
  </script>
</body>
```

Em alguns casos pode ser necessário adicionar apenas o tradutor de vídeos na página. Geralmente acontece quando a página inteira só possui um vídeo e, está incorporada em outra página em formato de iframe. Pra isso basta desativar o tradutor de textos, assim o botão de acessibilidade em Libras não irá aparecer nas laterais.


## Replace Automático de Vídeos

É possível substituir automaticamente os embeds do Youtube e player existentes do Videojs pelo Player Acessível da HandTalk, sempre que uma legenda for encontrada.

Caso o vídeo não possua legenda no idioma **pt-BR** ou **pt**, o mesmo ficará com a funcionalidade de Tradução para Libras bloqueada.

> Exemplo de Utilização de Embeds do Youtube

```javascript
var ht = new HT({
  // Troque por seu token de acesso
  token: "<TOKEN>",
  // Habilita o tradutor de vídeos
  videoEnabled: true,
  // Habilita embeds do Youtube
  ytEmbedReplace: true
});
```

### Replace automático de embeds do Youtube

A ferramenta busca por embeds (iframes) do youtube, e substitui por players accesíveis da Hand Talk.

Você pode habilitar o replace automático passando o valor `true` a configuração `ytEmbedReplace` ao instanciar o plugin. Lembrando que você deve também habilitar a feature de vídeo passando `true` na configuração `videoEnabled`.


Se embeds do Youtube forem inseridos após a inicialização do plugin, você deve chamar a função `ht.ytEmbedReplaceAll();` para que os novos vídeos tornem-se acessíveis.
Também é possível efetuar o replace de um único embed com `ht.ytEmbedReplace(elem)`:

```html
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/H2Io3y98FV4" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

<script>
  var iframe = document.querySelector('iframe');
  ht.ytEmbedReplace(iframe);
</script>
```

> Exemplo Para Habilitação de Replace Automático no Videojs

```javascript
var ht = new HT({
  // Troque por seu token de acesso
  token: "<TOKEN>",
  // Habilita o tradutor de vídeos
  videoEnabled: true,
  // Habilita embeds Videojs
  videojsReplace: true 
});
```

### Replace automático de embeds do Videojs

Parecido com o Youtube Embed Replace, a ferramenta varre a página e adiciona os componentes de acessibilidade em um player existente do videojs, de maneira que você não perca a referência.

Você pode habilitar o replace automático passando com valor `true` a configuração `videojsReplace` ao instanciar o plugin. Lembrando que você deve também habilitar a feature de vídeo passando `true` na configuração `videoEnabled`.

Veja o exemplo ao lado.

Se os players do videojs forem inseridos após a inicialização do plugin, você deve chamar a função `ht.videojsReplaceAll();` para que os novos vídeos tornem-se acessíveis.

Conforme o exemplo ao lado direito, também é possível efetuar o replace de um único  player com `ht.videojsReplace(vjsPlayer):`

> Exemplo de Utilização de Embeds do Videojs <br /> 

```html
<video id="vid" class="video-js vjs-default-skin" controls width="800" height="450">
  <source src="HandTalk.mp4" type='video/mp4'>
  <track src="HandTalk.vtt" kind="captions" srclang="pt" label="Português">
</video>

<script>
  var vjsPlayer = videojs('vid');
  ht.videojsReplace(vjsPlayer);
</script>
```

## Vídeos Dinâmicos

> Exemplo: Embeds dinâmicos do youtube

```javascript
var ht = new HT({
  // Troque por seu token de acesso
  token: "<TOKEN>",
  // Habilita o tradutor de sinais nos players
  videoEnabled: true
});

// Adiciona um vídeo do youtube após 3 segundos
window.setTimeout(function() {
  var iframe = document.createElement('iframe');
  iframe.src='https://www.youtube.com/embed/a9qsp7l5C3o';
  document.body.appendChild(iframe);
      
  // Aguarda o iframe carregar
  iframe.onload = function() {
    // Torna o embed acessível em Libras 
    ht.replaceYtEmbed(iframe);
    // Ou utilize a linha abaixo para buscar e substituir varios embeds
    // ht.replaceYtEmbedAll();
  }
}, 3000);
```

```html
<body>

  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

  <script>

    var ht = new HT({
      // Troque por seu token
      token: "<TOKEN>",
      // Habilita o tradutor de sinais nos players
      videoEnabled: true
    });

    // Adiciona um vídeo do youtube após 3 segundos
    setTimeout(function() {
      var iframe = document.createElement('iframe');
      iframe.src='https://www.youtube.com/embed/a9qsp7l5C3o';
      document.body.appendChild(iframe);
      
      // Aguarda o iframe carregar
      iframe.onload = function() {
        // Torna o embed acessível em Libras 
        ht.replaceYtEmbed(iframe);
        // Ou utilize a linha abaixo para buscar e substituir varios embeds
        // ht.replaceYtEmbedAll();
      }
    }, 3000);
  </script>

</body>
```

Caso o elemento do vídeo seja adicionado ao HTML dinâmicamente depois do carregamento do plugin, você precisa chamar a função de busca para renderizar os players novos.

<aside class="info">
Nota: Para realizar esse procedimento, certifique-se de estar com o plugin devidamente configurado de acordo com a sessão [Tradutor de Vídeos > Começando](#come-ando14).
</aside>

Para player construidos manualmente, ou seja, utilizando o [Player Acessível](#utilizando-o-player-acess-vel):

`videoManager.search();`

Para embeds do youtube:

`replaceYtEmbedAll()` ou `replaceYtEmbed(ytembed)`.

Para players existentes do videojs:

`replaceVideoJsAll()` ou `replaceVideoJs(vjsplayer)`.

Para mais detalhes sobre o replace consulte a guia [Replace Automático de Vídeos](#replace-autom-tico-de-v-deos)

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

## Resolvendo Conflitos de Estilo (css)
É provável que na substituição do elemento `<iframe />` do Youtube, pelo elemento `<div />` com a classe CSS video-js do player da Hand Talk, você perca a referência do elemento no seu CSS e Javascript.

No exemplo ao lado o código CSS espera que o filho da classe video seja um iframe:
> Exemplo para o código CSS

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
      // Habilita o tradutor de sinais nos players
      videoEnabled: true,
      // Habilita embeds do Youtube
      ytEmbedReplace: true
    });
  </script>

</body>
```

Ao substituir o elemento `<iframe />` por uma `<div />` a estrutura do site ficará quebrada. A solução seria esperar como filho um elemento com a classe video-js também.

> Solução para a quebra na estrutura

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
      // Troque por seu token
      token: "<TOKEN>",
      videoEnabled: true,
      ytEmbedReplace: true
    });
  </script>
</body>
```