# Tradutor de vídeos

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

Para a instalação do plugin, deve-se inserir o script da Hand Talk e instanciar a classe HT passando por argumento um dicionário com o token e demais configurações.

No exemplo de instalação à direita, utilizamos a última versão do script hospedado em https://api.handtalk.me/plugin/latest/handtalk.min.js, após inserir o script da Hand Talk instanciamos a classe `HT` passando por parâmetro um dicionário com o token.

Sem um token válido, a ferramenta não irá funcionar, emitindo o erro:

<aside class="warning">
406 - O serviço está desabilitado temporariamente para este website.
</aside>

após clicar no botão de ativação da ferramenta.

Você pode adquirir um token para o seu domínio em [account.handtalk.me](https://account.handtalk.me/). <br /> 
Ou fale com um de nossos consultores em [handtalk.me/sites](http://handtalk.me/sites).

## Utilizando o player acessível

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
