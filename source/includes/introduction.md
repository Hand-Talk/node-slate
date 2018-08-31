<h1 id='introducao'>Introdução</h1>

O plugin desenvolvido pela Hand Talk torna os sites acessíveis em língua de sinais. O mesmo conta com duas principais funcionalidades: tradução de texto e tradução de vídeos.


<h2 id='sobre-o-tradutor-de-texto'>Sobre o Tradutor de Texto</h2>

O usuário pode ativar a funcionalidade clicando no ícone que representa a acessibilidade em língua de sinais:

![](images/screenshoots/tradutor-de-sites.png)

Ao clicar, será aberta uma janela com o intérprete 3D da Hand Talk, o Hugo.
  
![](images/screenshoots/tradutor-de-sites-2.png)

Enquanto a janela estiver aberta, os textos e imagens com descrição ficarão clicáveis. Ao clicar, o Hugo captura o texto e sinaliza sua tradução.

![](images/screenshoots/tradutor-de-sites-3.png)

<h2 id='sobre-o-tradutor-de-videos'>Sobre o Tradutor de Vídeos</h2>

O plugin oferece um player de vídeo acessível em Libras, que suporta:

- [VideoJS](https://videojs.com)
- [YouTube](https://www.youtube.com/)
- [Vimeo](https://vimeo.com/pt-br/)
- [Sambatech](https://www.sambatech.com.br/)
- [Html5](https://www.w3schools.com/htmL/html5_video.asp)

Também é possível adicionar acessibilidade automaticamente aos embeds do Youtube e player existentes do Videojs, desde que tenham sempre uma legenda vinculada.

O usuário pode clicar no ícone que representa a acessibilidade em língua de sinais para iniciar o vídeo junto com a tradução do Hugo, ou apenas clicar no botão central para assistir o vídeo sem acessibilidade.

![](images/screenshoots/tradutor-de-videos.png)

No player acessível você encontra os botões de ativar e desativar tradução para língua de sinais, assistir em tela cheia, tocar e pausar, ajustar volume e a linha do tempo.

![](images/screenshoots/tradutor-de-videos-2.png)

Consulte a guia [Tradutor de Vídeos > Começando](index.html?html#comecando-tv) para um guia de implementação.

<h2 id='sobre-o-tradutor-mobile'>Sobre o Tradutor Mobile</h2>

A tradução de textos e vídeos também está disponivel na versão mobile, com pequenos ajustes que tornam a usabilidade ainda melhor para o usuário surdo.
A funcionalidade de tradução em dispositivos móveis vem habilitada por padrão, mas você pode removê-la definindo o parâmetro `mobileEnabled` como `false` caso necessário.

![](images/screenshoots/tradutor-mobile.jpg)

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

<h2 id='eventos'>Eventos</h2>

Você pode escutar os eventos utilizando o método .on(eventName, callback).

> ### Exemplo de Instalação

```javascript
ht.on('hugoLoaded', function () {

  console.log('Hugo carregado!');

});
```