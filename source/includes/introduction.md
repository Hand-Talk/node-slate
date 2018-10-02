<h1 id='introducao'>Introdução</h1>

O plugin desenvolvido pela Hand Talk torna os sites acessíveis em língua de sinais. O mesmo conta com duas principais funcionalidades: tradução de texto e tradução de vídeos.

<h2 id='sobre-o-tradutor-de-texto'>Sobre o Tradutor de Texto</h2>

O usuário pode ativar a funcionalidade clicando no ícone que representa a acessibilidade em língua de sinais:

![Site da Hand Talk com o Hugo centralizado e uma seta indicando o plugin ao lado direito.](images/screenshoots/tradutor-de-sites.png)

Ao clicar, será aberta uma janela com o intérprete 3D da Hand Talk, o Hugo.
  
![Janela de Libras aberta com o Hugo parado esperando para texto para traduzir.](images/screenshoots/tradutor-de-sites-2.png)

Enquanto a janela estiver aberta, os textos e imagens com descrição ficarão clicáveis. Ao clicar, o Hugo captura o texto e sinaliza sua tradução.

![Janela de Libras aberta do lado direito, texto sendo clicado e Hugo traduzindo-o.](images/screenshoots/tradutor-de-sites-3.png)

<h2 id='sobre-o-tradutor-de-videos'>Sobre o Tradutor de Vídeos</h2>

O plugin oferece um player de vídeo acessível em Libras, que suporta:

- [VideoJS](https://videojs.com)
- [YouTube](https://www.youtube.com/)
- [Vimeo](https://vimeo.com/pt-br/)
- [Sambatech](https://www.sambatech.com.br/)
- [Html5](https://www.w3schools.com/htmL/html5_video.asp)

Também é possível adicionar acessibilidade automaticamente aos embeds do Youtube e player existentes do Videojs, desde que tenham sempre uma legenda vinculada.

O usuário pode clicar no ícone que representa a acessibilidade em língua de sinais para iniciar o vídeo junto com a tradução do Hugo, ou apenas clicar no botão central para assistir o vídeo sem acessibilidade.

![Exemplo de player acessível com botão centralizado indicando acessibilidade em Libras.](images/screenshoots/tradutor-de-videos.png)

No player acessível você encontra os botões de ativar e desativar tradução para língua de sinais, assistir em tela cheia, tocar e pausar, ajustar volume e a linha do tempo.

![Player acessível com o Hugo posicionado à direita traduzindo o vídeo para Libras.](images/screenshoots/tradutor-de-videos-2.png)

Consulte a guia [Tradutor de Vídeos > Começando](index.html?html#comecando-tradutor-de-videos) para um guia de implementação.

<h2 id='sobre-o-tradutor-mobile'>Sobre o Tradutor Mobile</h2>

A tradução de textos e vídeos também está disponivel na versão mobile, com pequenos ajustes que tornam a usabilidade ainda melhor para o usuário surdo.
A funcionalidade de tradução em dispositivos móveis vem habilitada por padrão, mas você pode removê-la definindo o parâmetro `mobileEnabled` como `false` caso necessário.

![Plugin fechado no mobile, em seguida o Hugo esperando por uma tradução, à frente o Hugo traduzindo.](images/screenshoots/tradutor-mobile.png)

<h2 id='compatibilidade'>Compatibilidade</h2>

O plugin é compatível com a maioria dos navegadores modernos com suporte a WebGL, tais como, Chrome, Firefox, Edge, Safari e Opera.

Abaixo o resultado de testes feitos em sistemas operacionais diferentes usando o plugin em vários navegadores.

| Navegador / S.O.     | Windows | MacOs | Ubuntu (Linux) |
| -------------------- | ------- | ----- | -------------- |
|![](images/icons/chrome.png)    | ✔       | ✔     | ✔             |
|![](images/icons/firefox.png)    | ✔       | ✔     | ✔             |
|![](images/icons/opera.png)    | --      | ✔     | --             |
|![](images/icons/safari.png)   | ✔       | ✔     | ✔             |
|![](images/icons/edge.png)   | ✔       | --    | --             |
|![](images/icons/internet-explorer.png)<span style="margin-left: 15px;">**11**</span>   | ✔       | --    | --             |
|![](images/icons/internet-explorer.png)<span style="margin-left: 15px;">**10**</span>   | ✖       | --    | --             |
|![](images/icons/internet-explorer.png)<span style="margin-left: 15px;">**9**</span>  | ✖       | --    | --             |
  
Legenda:

✔ Compatível

✖ Não compatível

-- Sistema operacional não suporta o navegador

<h2 id='mensagens-de-erro'>Mensagens de Erro</h2>

Algumas mensagens de erro podem surgir por má configuração da ferramenta, são elas:

Sem um token válido, a ferramenta não irá funcionar, emitindo o erro:

<aside class="warning">
**406 - O serviço está desabilitado temporariamente para este website.**
</aside>

O Tradutor de vídeos está disponível no plano **Gold 2** ou superior. Caso a sua assinatura não suporte a funcionalidade de vídeos e a flag `videoEnabled` estiver habilitada, receberá o erro:

<aside class="warning">
**406 - A funcionalidade de vídeo não está habilitada para a sua assinatura.**
</aside>

<h2 id='eventos-introducao'>Eventos</h2>

> Exemplo de Listener de Eventos

```javascript
ht.on('translated', function () {
  console.log('Nova frase traduzida!');
});
```

```html
<body>
  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

  <script>
    var ht = new HT({
      // Troque por seu token de acesso
      token: '<SEU TOKEN>'
    });

    // Escuta o evento translated
    ht.on('translated', function () {
      console.log('Nova frase traduzida!');
    });
  </script>
</body>
```

Em alguns momentos você pode necessitar de dados de uso da ferramenta, como quantidade de aberturas, traduções, saber se a ferramenta carregou, e entre outros.
Pra isso, você deve ouvir os eventos disparados por `HT`, conforme o exemplo ao lado.

Os eventos disparados por `HT` são:

| Evento | Descrição | Retorno |
|---|---|---|
| authenticating | Autenticando | ```undefined``` |
| errorOnAuth | Erro ao autenticar | ```undefined``` |
| authenticated | Autenticado | ```undefined``` |
| notCompatible | Navegador ou hardware não compatível | string: ```'withoutCanvas'``` ou ```'withoutWebGL'``` ou ```'hardwareDoesNotSupport'``` |
| customizing | Customizando | ```undefined``` |
| customized | Customizado | ```undefined``` |
| hugoLoaded | Hugo carregado | ```undefined``` |
| activated | Feature de texto ou vídeo ativada | string: ```'textManager'``` ou ```'videoManager'``` |
| translate | Dispara quando um texto é capturado e enviado para tradução pela feature de tradução de texto | string: texto capturado |
| translating | Traduzindo texto no servidor da Hand Talk | ```undefined``` |
| errorOnTranslate | Erro ao traduzir texto no servidor da Hand Talk | ```undefined``` |
| translated | Texto traduzido corretamente no Servidor da Hand Talk | ```undefined``` |
| signalized | Sentença sinalizada por completo | ```undefined``` |
| videoManagerReady | Disparado quando o assistente de vídeo esta pronto, utilize para chamar as funções de replace manualmente | ```undefined``` |
