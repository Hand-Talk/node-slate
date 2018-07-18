# Introdução

O plugin desenvolvido pela Hand Talk torna os sites acessíveis em língua de sinais. O mesmo conta com duas principais funcionalidades: tradução de texto e tradução de vídeos.


## Tradutor de texto

  

O usuário pode habilitar a funcionalidade clicando no ícone que representa a acessibilidade em língua de sinais:

  

![](http://i66.tinypic.com/r93878.jpg)

  

Ao clicar será aberta uma gaveta com o intérprete 3D da Hand Talk, o Hugo.

  

![](http://i66.tinypic.com/2ib26w6.jpg)

  

Enquanto a gaveta estiver aberta os textos e imagens com descrição ficaram clicáveis, ao clicar o Hugo captura o texto e sinaliza sua tradução.

  

![](http://i65.tinypic.com/20tqql1.jpg)

  

## Tradutor de vídeos

  

O plugin oferece um player de vídeo acessível em Libras, que suporta:

  

- HTML5;
- Youtube;
- Vimeo;

Também é possível substituir automaticamente os embeds do Youtube e player existentes do Videojs pelo player acessível da HandTalk, sempre que uma legenda for encontrada.

O usuário pode clicar no ícone que representa a acessibilidade em língua de sinais para iniciar o vídeo junto com a tradução do Hugo, ou apenas clicar no botão central para assistir o vídeo sem acessibilidade.

![](http://i67.tinypic.com/szzwpl.jpg)

No player acessível você encontra os botões de ativar e desativar tradução para língua de sinais, assistir em tela cheia, tocar e pausar, ajustar volume e a linha do tempo.

![](http://i67.tinypic.com/23qqt4.jpg)

## Tradutor Mobile


A funcionalidade de tradução em dispositivos móveis vem habilitada por padrão, mas você pode removê-la definindo o parâmetro `mobileEnabled` como `false` caso necessário.

![](http://i68.tinypic.com/nxn794.jpg)

## Compatibilidade

O plugin é compatível com a maioria dos navegadores modernos com suporte a WebGL, tais como, Chrome, Firefox, Edge, Safari e Opera.

Abaixo o resultado de testes feitos em sistemas operacionais diferentes usando o plugin em vários navegadores.

| Navegador / S.O.     | Windows | MacOs | Ubuntu (Linux) |
| -------------------- | ------- | ----- | -------------- |
| Chrome               | ✔       | ✔     | ✔              |
| Firefox              | ✔       | ✔     | ✔              |
| Safari               | --      | ✔     | --             |
| Opera                | ✔       | ✔     | ✔              |
| Edge                 | ✔       | --    | --             |
| Internet Explorer 11 | ✔       | --    | --             |
| Internet Explorer 10 | ✖       | --    | --             |
| Internet Explorer 9  | ✖       | --    | --             |

  

✔ Compatível

  

✖ Não compatível

  

-- Sistema operacional não suporta o navegador

  

## Instalação

  

Para a instalação do plugin deve se inserir o script da Hand Talk e instanciar a classe HT passando por argumento um dicionário com o token e demais configurações.

No exemplo abaixo utilizamos a última versão do script hospedado em https://api.handtalk.me/plugin/latest/handtalk.min.js, após inserir o script da Hand Talk instanciamos a classe `HT` passando por parâmetro um dicionário com o token.

Você pode adquirir um token para o seu domínio em [account.handtalk.me](https://account.handtalk.me/) ou fale com um dos nossos consultores em [handtalk.me/sites](http://handtalk.me/sites).

  
> Troque <TOKEN> por seu token de acesso

```html

<script src="http://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

<script>
var ht = new HT({
  token: "<TOKEN>",
});
</script>
```

## Exemplo  

> Troque <TOKEN> por seu token de acesso

```html

<!DOCTYPE html>
<html lang="pt-br">

  <head>
    <meta charset="UTF-8">
    <title>Website</title>
  </head>

  <body>

    <h1>Hand Talk</h1>
    <h2>Conte com a ajuda do Hugo, nosso intérprete virtual, para tornar a sua comunicação mais acessível.</h2>
    <p>Oferecemos tradução digital para acessibilidade em Libras, a Língua Brasileira de Sinais.</p>

    <script src="http://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

    <script>
    var ht = new HT({
      token: "<TOKEN>",
    });
    </script>
  </body>

</html>
```