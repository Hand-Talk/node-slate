# Tradutor de Sites

## Começando

> ### Exemplo de Instalação <br />
Troque `<TOKEN>` por seu token de acesso
 
```javascript
var ht = new HT({
  // Troque por seu token, exemplo:
  // token: "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
  token: "<TOKEN>",
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

Para a instalação do plugin deve-se inserir o script da Hand Talk e instanciar a classe HT passando por argumento um dicionário com o token e demais configurações.

No exemplo de instalação à direita, utilizamos a última versão do script hospedado em https://api.handtalk.me/plugin/latest/handtalk.min.js, após inserir o script da Hand Talk instanciamos a classe `HT` passando por parâmetro um dicionário com o token.

Você pode adquirir um token para o seu domínio em [account.handtalk.me](https://account.handtalk.me/) ou fale com um dos nossos consultores em [handtalk.me/sites](http://handtalk.me/sites).


## Parâmetros

### Parâmetros para versão mobile

## Exemplo avançado

## Adicionando exceções

## Aumentando o limite de captura de texto

## Tornando iframes acessíveis

## Iframes dinâmicos

## Traduzindo imagens

## Desativando requisições de melhorias do sistema