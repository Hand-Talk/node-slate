<h1 id='tradutor-de-videos'>Tradutor de Vídeos</h1>

<h2 id='comecando-tradutor-de-videos'>Começando</h2>

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

  <!-- Troque os campos VIDEO_TYPE, VIDEO_URL, CAPTION_TYPE e CAPTION_URL, pelos dados solicitados-->
  <video
  data-ht-src-type="VIDEO_TYPE"
  data-ht-src="VIDEO_URL"
  data-ht-subtitle-type="CAPTION_TYPE"
  data-ht-subtitle="CAPTION_URL">
  </video>


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

<h2 id='utilizando-o-player-acessivel-tradutor-de-videos'>Utilizando o Player Acessível</h2>

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

Nota: Para utilizar o player acessível, certifique-se de estar com o plugin devidamente configurado de acordo com a sessão [Tradutor de Vídeos > Começando](index.html?html#comecando-tradutor-de-videos).
</aside>


Você pode tornar um vídeo acessível definindo o atributos abaixo:  


| Atributo                     | Descrição                                                       |
|-----------------------------|------------------------------------------------------------------|
| data-ht-src-type       | Define o tech do vídeo.|
| data-ht-src            | Define o caminho do vídeo.|
| data-ht-subtitle-type  | Define o tipo da legenda(Opcional).|
| data-ht-subtitle       | Define o caminho da legenda(Opcional).|
 

<aside class="info">

Nota: O construtor de vídeos através de um único atributo `ht-data="src=<VIDEO_TECH>:<VIDEO_URL>;subtitle=<CAPTIONS_TYPE>:<CAPTIONS_URL>"` está depreciado, e pode ser removido em futuras versões.

</aside>

> Construtor do player Hand Talk

```html
<video
data-ht-src-type="VIDEO_TYPE"
data-ht-src="VIDEO_URL"
data-ht-subtitle-type="CAPTION_TYPE"
data-ht-subtitle="CAPTION_URL">
</video>

```

```javascript
// Confira o exemplo em html
```

Os atributos de legenda não são obrigatórios:  
`data-ht-subtitle-type="CAPTION_TYPE"`  
`data-ht-subtitle="CAPTION_URL"`

<h3 id='exemplo-com-tech-youtube'>Exemplo com Tech do Youtube</h3>

> Exemplo: Criando um vídeo com o **tech** youtube
 
```html
<!-- Torna o vídeo https://www.youtube.com/watch?v=H2Io3y98FV4 acessivel -->
<video
data-ht-src-type="youtube"
data-ht-src="H2Io3y98FV4">
</video>

```

```javascript
// Confira o exemplo em html
```

Caso o campo subtitle fique em branco em um src do tipo Youtube, a legenda será obtida automaticamente. Como no exemplo ao lado.
 
<aside class="info">

Nota: No source do tipo Youtube, você pode optar por adicionar o link do vídeo, ou apenas o ID. Conforme exemplo ao lado.
</aside>
 
Caso o vídeo esteja definido como **não listado**, ou algum outro tipo de restrição no Youtube", não conseguiremos acessar a legenda, restornando o erro:

<aside class="warning">
404 - Legenda não encontrada.
</aside>

O exemplo ao lado *(Criando um vídeo com o tech youtube)* deve gerar o seguinte player:


<video class='video-js' data-ht-src-type="youtube" data-ht-src="H2Io3y98FV4"></video>


<h3 id='exemplo-com-tech-do-vimeo'>Exemplo com Tech do Vimeo</h3>

> Exemplo: Criando um vídeo com o **tech** vimeo

```html
<!-- Cria um novo player com uma legenda estatica -->
<video
data-ht-src-type="vimeo"
data-ht-src="https://player.vimeo.com/video/259226390"
data-ht-subtitle-type="vtt"
data-ht-subtitle="assets/HandTalk.vtt">
</video>

```

```javascript
// Confira o exemplo em html
```

Para vídeos hospedados no Vimeo, você deve informar a legenda manualmente.
Como no exemplo ao lado, o vídeo deve aparecer da seguinte forma:



<video data-ht-src-type="vimeo" data-ht-src="https://player.vimeo.com/video/259226390" data-ht-subtitle-type="vtt" data-ht-subtitle="assets/HandTalk.vtt">
</video>

  
<h3 id='exemplo-com-tech-de-mp4-webm'>Exemplo com Tech de MP4/WEBM/OGG</h3>
 
> Exemplo: Criando um vídeo com o **tech** mp4

```html
<!-- Cria um novo player com uma legenda estatica -->
<video
data-ht-src-type="mp4"
data-ht-src="assets/HandTalk.mp4"
data-ht-subtitle-type="vtt"
data-ht-subtitle="assets/HandTalk.vtt">
</video>


```

```javascript
// Confira o exemplo em html
```

Utilize para vídeos e legendas hospedadas na internet com link direto - Exemplo ao lado.

<video data-ht-src-type="mp4" data-ht-src="assets/HandTalk.mp4" data-ht-subtitle-type="vtt" data-ht-subtitle="assets/HandTalk.vtt"></video>

<h3 id='exemplo-com-tech-da-sambatech'>Exemplo com Tech da SambaTech</h3>

> Exemplo: Criando um vídeo com o **tech** sambatech

```html
<!-- Cria um novo player com uma legenda estatica -->
<video
data-ht-src-type="sambatech"
data-ht-src="https://fast.player.liquidplatform.com/pApiv2/embed/c750c09d7d04891b7f3f5c9a9337d6b9/a40cc34d36f0ee05ae55a971b427888e"
data-ht-subtitle-type="vtt"
data-ht-subtitle="assets/HandTalk.vtt">
</video>
```

```javascript
// Confira o exemplo em html
```

Utilize para vídeos hospedados na SambaTech e legendas hospedadas na internet com link direto - Exemplo ao lado.

<video data-ht-src-type="sambatech" data-ht-src="https://fast.player.liquidplatform.com/pApiv2/embed/c750c09d7d04891b7f3f5c9a9337d6b9/a40cc34d36f0ee05ae55a971b427888e" data-ht-subtitle-type="vtt" data-ht-subtitle="assets/HandTalk.vtt" ></video>




<h2 id="manipulando-player-acessivel">Manipulando Player Acessível</h2>


Em alguns casos você pode precisar coletar dados do vídeo para saber se o mesmo foi assistido até o final, se foi iniciado, ou se está em reprodução.

| Configurações  | Descrição
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ | 
| play    | Evento disparado quando a reprodução do vídeo for iniciada.    |
| pause   | Evento disparado quando reprodução do vídeo for pausado.                  |
| timeupdate           | Evento disparado após ínicio do vídeo é responsável por contagem de tempo de execução do vídeo.         |
| ended          | Evento disparado após o término da reprodução.

**Nota: Caso você não possua as depedência do vídeo Js o nosso plugin irá adiciona-las automaticamente.**

Caso deseje mais informações da documentação do vídeo Js segue o link abaixo:
https://docs.videojs.com/docs/api/player.html

> Exemplo de Utilização

```html

<body>

  <!-- Caminho do vídeo-->
  <video data-ht="src=youtube:H2Io3y98FV4"></video>

  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

  <script>
  var ht = new HT({
    // Troque por seu token de acesso
    token: "<TOKEN>",
    // Habilita o Tradutor de Vídeos
    videoEnabled: true
    // Efetua replace de players existentes do videojs automaticamente ao ser inicializado.
    videojsReplace: true
  });
  </script>
  <script>

  // Criando variavél para manipulação do vídeo JS 
  var player= videojs('video');

  // Cria evento para verificar se o vídeo iniciou a reprodução.
  player.on('play', function () {
    console.log('play');
  });

  // Cria evento para verificar se o vídeo foi pausado
  player.on('pause', function () {
    console.log('pause');
  });

  // Cria evento para verificar o tempo que o vídeo esta sendo reproduzido.
  player.on('timeupdate', function () {
    console.log(player.currentTime());
  });

  // Cria evento para verificar se o vídeo terminou a reprodução.
  player.on('ended', function () {
    console.log('FIM DO VIDEO');
  });
</script>
</body>
```

```javascript





```

<h2 id="utilizando-apenas-o-tradutor-de-videos">Utilizando Apenas o Tradutor de Vídeos</h2>

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

  <!-- Troque os campos VIDEO_TYPE, VIDEO_URL, CAPTION_TYPE e CAPTION_URL, pelos dados solicitados -->
  <video
  data-ht-src-type="VIDEO_TYPE"
  data-ht-src="VIDEO_URL"
  data-ht-subtitle-type="CAPTION_TYPE"
  data-ht-subtitle="CAPTION_URL">
  </video>


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


<h2 id='replace-automatico-de-videos'>Replace Automático de Vídeos</h2>

É possível substituir automaticamente os embeds do Youtube e player existentes do Videojs pelo Player Acessível da HandTalk, sempre que uma legenda for encontrada.

Caso o vídeo não possua legenda no idioma **pt-BR** ou **pt**, o mesmo ficará com a funcionalidade de Tradução para Libras bloqueada. Conforme a imagem abaixo

![Exemplo de vídeo sem legenda em português brasileiro com ícone de tradução para libras bloqueado.](images/screenshoots/tradutor-de-videos-fail.png)


<aside class="notice">
Ao usar o replace automático de vídeos você perderá a referência do seu player atual, caso precise manipular o player, recomendamos que verifique a sessão [Utilizando o Player Acessível](#utilizando-o-player-acessivel-tradutor-de-videos).
</aside>

<h2 id='replace-automatico-de-embeds-do-youtube'>Replace Automático de Embeds do Youtube</h2>

> Exemplo de Utilização de Embeds do Youtube

```javascript
var ht = new HT({
  // Troque por seu token de acesso
  token: "<TOKEN>",
  // Habilita o tradutor de vídeos
  videoEnabled: true,
  // Busca por embeds do youtube ao inicializar a ferramenta
  ytEmbedReplace: true
});
```

<h3 id='replace-automatico-de-embeds-do-youtube'>Replace automático de embeds do Youtube</h3>

```html
<body>

  <!-- Embed padrão do youtube -->
  <iframe width="560" height="315" src="https://www.youtube.com/embed/H2Io3y98FV4" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

  <script>
    var ht = new HT({
      // Troque por seu token de acesso
      token: "<TOKEN>",
      // Habilita o tradutor de vídeos
      videoEnabled: true,
      // Busca por embeds do youtube ao inicializar a ferramenta
      ytEmbedReplace: true
    });
  </script>
</body>
```

A ferramenta busca por embeds (iframes) do youtube, e substitui por players accesíveis da Hand Talk.

Você pode habilitar o replace automático passando o valor `true` a configuração `ytEmbedReplace` ao instanciar o plugin. Lembrando que você deve também habilitar a feature de vídeo passando `true` na configuração `videoEnabled`.


Se embeds do Youtube forem inseridos após a inicialização do plugin, você deve chamar a função `ht.ytEmbedReplaceAll();` para que os novos vídeos tornem-se acessíveis.
Também é possível efetuar o replace de um único embed com `ht.ytEmbedReplace(elem)`:

<h2 id='replace-automatico-de-embeds-do-videojs'>Replace Automático de Embeds do Videojs</h2>

> Exemplo de Utilização de Embeds do Videojs

```html
<body>

  <!-- Embed padrão do videojs -->
  <video id="vid" class="video-js vjs-default-skin" controls width="800" height="450">
    <source src="HandTalk.mp4" type='video/mp4'>
    <track src="HandTalk.vtt" kind="captions" srclang="pt" label="Português">
  </video>

  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

  <script>
    videojs('vid');
    var ht = new HT({
      // Troque por seu token de acesso
      token: "<TOKEN>",
      // Habilita o tradutor de vídeos
      videoEnabled: true,
      // Busca por embeds do videojs ao inicializar a ferramenta
      videojsReplace: true
    });
  </script>
</body>
```

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

Parecido com o Youtube Embed Replace, a ferramenta varre a página e adiciona os componentes de acessibilidade em um player existente do videojs, de maneira que você não perca a referência.

Você pode habilitar o replace automático passando com valor `true` a configuração `videojsReplace` ao instanciar o plugin. Lembrando que você deve também habilitar a feature de vídeo passando `true` na configuração `videoEnabled`.

Veja o exemplo ao lado.


Se os players do videojs forem inseridos após a inicialização do plugin, você deve chamar a função `ht.videojsReplaceAll();` para que os novos vídeos tornem-se acessíveis.

Conforme o exemplo ao lado direito, também é possível efetuar o replace de um único  player com `ht.videojsReplace(vjsPlayer):`

<h2 id='videos-dinamicos'>Vídeos Dinâmicos</h2>

Caso o elemento do vídeo seja adicionado ao HTML dinâmicamente depois do carregamento do plugin, você precisa chamar a função de busca para renderizar os players novos.

<aside class="info">

Nota: Para realizar esse procedimento, certifique-se de estar com o plugin devidamente configurado de acordo com a sessão [Tradutor de Vídeos > Começando](index.html?html#comecando-tradutor-de-videos).

</aside>

> Exemplo de Utilização de Embeds dinâmicos do youtube

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

<h3 id='exemplos-videos-dinamicos'>Exemplos</h3>

Para player construidos manualmente, ou seja, utilizando o [Tradutor de Vídeos > Player Acessível](index.html?html#utilizando-o-player-acessivel-tradutor-de-videos):

`videoManager.search();`

Para embeds do youtube:

`replaceYtEmbedAll()` ou `replaceYtEmbed(ytembed)`.

Para players existentes do videojs:

`replaceVideoJsAll()` ou `replaceVideoJs(vjsplayer)`.

Para mais detalhes sobre o replace consulte a guia [Tradutor de Vídeos > Replace Automático de Vídeos](index.html?html#replace-automatico-de-videos).

<h2 id='legendas-tradutor-de-videos'>Legendas</h2>


As legendas precisam ser breves e de acordo com o tempo que será utilizado nelas para que o Hugo possa traduzí-las de forma que ele não acelere e não perca a sincronia com o vídeo.

<h3 id='exemplos-legendas'>Exemplos</h3>

Abaixo está um exemplo de legenda boa e outro de legenda ruim, respectivamente:


`00:00:04.868 --> 00:00:10.500`<br />
Os grandes feitos da humanidade seriam inúteis se não houvesse a comunicação. 

O exemplo acima retrata uma prática boa para legendas.

`00:00:01.000 --> 00:00:01.500`<br />
Asteroblaudo corria pela rua do alagamento no deserto para poder fugir de um casal de rinocerontes.

Enquanto que o exemplo acima retrata uma prática ruim para legendas.

<h2 id='resolvendo-conflitos-de-estilo-css'>Resolvendo Conflitos de Estilo (css)</h2>

É provável que na substituição do elemento `<iframe />` do Youtube, pelo elemento `<div />` com a classe CSS video-js do player da Hand Talk, você perca a referência do elemento no seu CSS e Javascript.

> Exemplo de Estrutura Quebrada

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

```javascript
// Confira o exemplo em html
```

É provável que na substituição do elemento `<iframe />` do Youtube, pelo elemento `<div />` com a classe CSS video-js do player da Hand Talk, você perca a referência do elemento no seu CSS e Javascript.

No exemplo ao lado o código CSS espera que o filho da classe video seja um iframe:

Ao substituir o elemento `<iframe />` por uma `<div />` a estrutura do site ficará quebrada. A solução seria esperar como filho um elemento com a classe video-js também.

> Solução para a Quebra na Estrutura

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

```javascript
// Confira o exemplo em html
```