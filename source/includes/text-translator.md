# Tradutor de Sites

## Começando

> ### Exemplo de Instalação <br />
Troque `<TOKEN>` por seu token de acesso
 
```javascript
var ht = new HT({
  // Troque por seu token, exemplo:
  // token: "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
  token: "<TOKEN>"
});
```

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

    <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

    <script>
    var ht = new HT({
      // Troque por seu token, exemplo:
      // token: "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
      token: "<TOKEN>"
    });
    </script>
  </body>

</html>
```

Para a instalação do plugin, deve-se inserir o script da Hand Talk e instanciar a classe HT passando por argumento um dicionário com o token e demais configurações.

No exemplo de instalação à direita, utilizamos a última versão do script hospedado em https://api.handtalk.me/plugin/latest/handtalk.min.js, após inserir o script da Hand Talk instanciamos a classe `HT` passando por parâmetro um dicionário com o token.

Sem um token válido, a ferramenta não irá funcionar, emitindo o erro  ***O serviço está desabilitado temporariamente para este website***, após clicar no botão de ativação da ferramenta.

Você pode adquirir um token para o seu domínio em [account.handtalk.me](https://account.handtalk.me/). <br /> 
Ou fale com um de nossos consultores em [handtalk.me/sites](http://handtalk.me/sites).

## Parâmetros

Você pode pode preferir habilitar/desabilitar algumas funcionalidades do Tradutor de Sites, para isso utilize os parâmetros abaixo:

| Configurações | Descrição                                                                                                                                             | Valores                        | Padrão    |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ | --------- |
| textEnabled   | Quando verdadeiro: exibe o tradutor de sites para textos.                                                                                             | false ou true                  | true      |
| side          | Define o posicionamento da janela do tradutor no site. O Tradutor de Sites pode ser inicializado do lado esquerdo ou do lado direito da tela.         | "right" ou "left"              | "right"   |
| align         | Define o alinhamento horizontal da janela do tradutor no site.                                                                                        | "default" ou "top" ou "bottom" | "default" |
| zIndex        | Define o posicionamento da profundidade do tradutor no site, ou seja, determinar se o Tradutor de Sites estará mais próximo ou mais afastado da tela. | Inteiros                       | 1000000   |
| maxTextSize   | Define o tamanho máximo de caracteres para captura de texto em um elemento.                                                                           | Inteiros                       | 500       |
| doNotTrack    | Se o valor desta propriedade for verdadeiro, as frases traduzidas não serão armazenadas ou utilizada para a melhoria do sistema de tradução.          | false ou true                  | false     |
| exceptions    | Lista de queries que serão ignoradas pelo plugin, ex.: ```['a', 'form', '.main', '#site-title']```                                                  | array                          | [ ]       |
| mobileConfig  | Objeto de configuração para a plataforma mobile, quando definido, sobscreve as configurações padrões de HT.                                           | Object                         | { }       |

Consulte a guia [Definindo Parametros] para mais detalhes de implementação.

### Parâmetros para versão mobile

```javascript
var ht = new HT({
  // Troque por seu token, exemplo:
  // token: "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
  token: "<TOKEN>",
  // Posiciona o Tradutor de Sites ao lado esquerdo da página
  align: "left",
  // Quando mobile, Posiciona o Tradutor de Sites ao lado direito da página 
  mobileConfig: {
    align: "right"
  }
});
```

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

    <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

    <script>
    var ht = new HT({
      // Troque por seu token, exemplo:
      // token: "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
      token: "<TOKEN>",
      // Posiciona o Tradutor de Sites ao lado esquerdo da página
      align: "left",
      // Quando mobile, Posiciona o Tradutor de Sites ao lado direito da página 
      mobileConfig: {
        align: "right"
      }
    });
    </script>
  </body>

</html>
```

Você pode passar parâmetros especificos para dispositivos movéis, para isso basta utilizar a propriedade ```mobileConfig```, e passar os parâmetros que serão sobrescritos. O Parâmetro ```bottom``` é exclusivo para dispositivos movéis.

| Configurações | Descrição                                                                                                                                                     | Valores           | Padrão  |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- | ------- |
| bottom        | Posicionamento do botão de acessibilidade e do Hugo em relação a parte inferior da tela na versão mobile. Especifique também a unidade de medida (em, %, px). | string            | "0px"   |

Consulte o exemplo ao lado.

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
  
Legenda:

✔ Compatível

✖ Não compatível

-- Sistema operacional não suporta o navegador

## Adicionando exceções

## Aumentando o limite de captura de texto

## Tornando iframes acessíveis

## Iframes dinâmicos

## Traduzindo imagens

## Desativando requisições de melhorias do sistema