# Introdução

O plugin desenvolvido pela Hand Talk torna os sites acessíveis em língua de sinais. O mesmo conta com duas principais funcionalidades: tradução de texto e tradução de vídeos.

## Sobre o Tradutor de Texto

O usuário pode habilitar a funcionalidade clicando no ícone que representa a acessibilidade em língua de sinais:

![](images/screenshoots/tradutor-de-sites.png)

Ao clicar, será aberta uma janela com o intérprete 3D da Hand Talk, o Hugo.
  
![](images/screenshoots/tradutor-de-sites-2.png)

Enquanto a janela estiver aberta, os textos e imagens com descrição ficaram clicáveis. Ao clicar, o Hugo captura o texto e sinaliza sua tradução.

![](images/screenshoots/tradutor-de-sites-3.png)

## Sobre o Tradutor de Vídeos

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

Consulte a guia [Tradutor de Vídeos > Começando](#come-ando18) para um guia de implementação.

## Sobre o Tradutor Mobile

A funcionalidade de tradução em dispositivos móveis vem habilitada por padrão, mas você pode removê-la definindo o parâmetro `mobileEnabled` como `false` caso necessário.

![](images/screenshoots/tradutor-mobile.jpg)

## Compatibilidade

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