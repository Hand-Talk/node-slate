# Tradutor de Sites

## Começando

> ### Exemplo de Instalação <br /> 
 
```javascript
var ht = new HT({
  // Troque por seu token de acesso
  token: "<TOKEN>"
});
```

```html
<body>

  <h1>Hand Talk</h1>
  <h2>Conte com a ajuda do Hugo, nosso intérprete virtual, para tornar a sua comunicação mais acessível.</h2>
  <p>Oferecemos tradução digital para acessibilidade em Libras, a Língua Brasileira de Sinais.</p>

  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

  <script>
  var ht = new HT({
    // Troque por seu token de acesso
    token: "<TOKEN>"
  });
  </script>
</body>
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
| exceptions    | Lista de queries que serão ignoradas pelo plugin, ex.: ```['a', 'form', '.main', '#site-title']```                                                    | array                          | [ ]       |
| mobileConfig  | Objeto de configuração para a plataforma mobile, quando definido, sobscreve as configurações padrões de HT.                                           | Object                         | { }       |


### Parâmetros para versão mobile

> ### Adicionando Parâmetros Exclusivos para Versão Mobile

```javascript
var ht = new HT({
  // Troque por seu token de acesso
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
<body>
  <h1>Hand Talk</h1>
  <h2>Conte com a ajuda do Hugo, nosso intérprete virtual, para tornar a sua comunicação mais acessível.</h2>
  <p>Oferecemos tradução digital para acessibilidade em Libras, a Língua Brasileira de Sinais.</p>

  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

  <script>
  var ht = new HT({
    // Troque por seu token de acesso
    token: "<TOKEN>",
    // Posiciona o Tradutor de Sites ao lado esquerdo da página
    side: "left",
    // Quando mobile, Posiciona o Tradutor de Sites ao lado direito da página 
    mobileConfig: {
      side: "right"
    }
  });
  </script>
</body>
```

Você pode passar parâmetros especificos para dispositivos movéis, para isso basta utilizar a propriedade ```mobileConfig```, e passar os parâmetros que serão sobrescritos. O Parâmetro ```bottom``` é exclusivo para dispositivos movéis.

| Configurações | Descrição                                                                                                                                                     | Valores | Padrão |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- | ------ |
| bottom        | Posicionamento do botão de acessibilidade e do Hugo em relação a parte inferior da tela na versão mobile. Especifique também a unidade de medida (em, %, px). | string  | "0px"  |

Consulte o exemplo ao lado.

## Adicionando Exceções

> ### Adicionando Exceções

```javascript
var ht = new HT({
  // Troque por seu token de acesso
  token: "<TOKEN>",
  // Ignora todo o conteúdo que possuir o id/class referenciado
  exceptions: ["#carousel", ".formulario"]
});
```

```html
<body>
  <!-- Não existe nenhuma referência do elemento abaixo na lista de exceções, então ele será traduzido. -->
  <h1 id="titulo">Hand Talk</h1>

  <!-- a classe formulario está sendo ignorada, logo todo o conteúdo deste form não será traduzido. -->
  <form class="formulario">
    <input type="text" placeholder="Insira o texto ">
    <input type="submit" value="Pesquisar">
  </form>

  <!-- Este slide será ignorado devido ao id carousel ter sido adicionado a lista de exceções  -->
  <div id="carousel">
    <div>Meu slide 1</div>
    <div>Meu slide 2</div>
    <div>Meu slide 3</div>
  </div>

  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

  <script>
  var ht = new HT({
    // Troque por seu token de acesso
    token: "<TOKEN>",
    // Ignora todo o conteúdo que possuir o id/class referenciado
    exceptions: ["#carousel", ".formulario"]
  });
  </script>
</body>
```

Em alguns casos, pode haver algum conflito entre o código da Hand Talk e algum script que o site possui. Para evitar esse conflito, basta adicionar esse elemento como uma exceção.

### Tratamento de Exceção de ID e CLASS:

Caso seu site tenha algum problema de conflito com um scripts de carousel, por exemplo, você pode adicionar o elemento na propriedade `exceptions`.

Declare qual ID ou CLASS não utilizará o Hand Talk, como também nenhum dos seus elementos filhos, ou seja, quando declarar que `#carousel` não vai utilizar a tradução, nada dentro desta DIV ou elemento irá ser traduzido. Estes elementos devem ser inseridos entre aspas e separados por vírgula: 

`exceptions: ["#menu", "#carousel", ".listas", ".formulario"]`

No exemplo ao lado, colocamos na exceção um ID de elemento HTML e uma classe CSS, consecutivamente.

**Atenção**: Ao adicionar o conteúdo como uma exceção, ele não será traduzido pela Hand Talk.

**Importante**: Dependendo da linguagem e/ou lógica de programação aplicada no desenvolvimento do website, para possibilitar o pleno funcionamento ou aprimorar os resultados obtidos pelo serviço, pode ser necessária a realização de outras customizações no código da Hand Talk, que deverão ser feitas pelo cliente.

## Iframes Dinâmicos

> ### Exemplo de Compatibilidade com Iframes Dinâmicos

```javascript
var ht = new HT({
  // Troque por seu token de acesso
  token: "<TOKEN>"
});

// Aguarda 3 segundos e insere um iframe na página
window.setTimeout(function() {
  // Cria o iframe e adiciona na pagina
  var iframe = document.createElement("iframe");
  document.body.appendChild(iframe);
    
  //Define o conteúdo do iframe
  iframe.contentDocument.write("<div>Olá mundo!</div>");
  
  // Adiciona os listeners no iframe
  ht.addListenersToIframe(iframe);
  // Ou utilize
  // ht.addListenersToIframeAll();
  // Para fazer a varredura na página inteira novamente
}, 3000);
```

```html
<body>
  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://api.handtalk.me/plugin/latest/handtalk.min.js"></script>

  <script>
    var ht = new HT({
      // Troque por seu token de acesso
      token: "<TOKEN>"
    )};

    // Após 3 segundos cria um iframe
    window.setTimeout(function() {
      // Cria o iframe e adiciona na pagina
      var iframe = document.createElement("iframe");
      document.body.appendChild(iframe);
      
      //Define o conteúdo do iframe
      iframe.contentDocument.write("<div>Olá mundo!</div>");
      
      // Adiciona os listeners no iframe
      ht.addListenersToIframe(iframe);
      // Para buscar iframes e adicionar os listeners, utilize:
      // ht.addListenersToIframeAll();
    }, 3000);
  </script>
</body>
```

Ao ser carregado, o plugin Hand Talk faz uma varredura na página buscando iframes e adicionando os listeners necessários para identificar o conteúdo de um elemento. Em casos de iframes que são atualizados dinâmicamente, deve ser utilizada a função `addIframesListenersAll()` para buscar novamente por iframes, ou `addListenersToIframe(iframe)` para um iframe especifico.

Veja o exemplo ao lado.