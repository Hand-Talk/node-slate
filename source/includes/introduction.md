<h1 id='introducao'>Introdução</h1>

O plugin desenvolvido pela Hand Talk torna os sites acessíveis em língua de sinais. Sua principal funcionabilidade é tradução de texto.

<h2 id='sobre-o-tradutor-de-texto'>Sobre o Tradutor de Texto</h2>

O usuário pode ativar a funcionalidade clicando no ícone que representa a acessibilidade em língua de sinais:

![Site da Hand Talk com o Hugo centralizado e uma seta indicando o plugin ao lado direito.](images/screenshoots/tradutor-de-sites.png)

Ao clicar, será aberta uma janela com o intérprete 3D da Hand Talk, o Hugo.
  
![Janela de Libras aberta com o Hugo parado esperando para texto para traduzir.](images/screenshoots/tradutor-de-sites-2.png)

Enquanto a janela estiver aberta, os textos e imagens com descrição ficarão clicáveis. Ao clicar, o Hugo captura o texto e sinaliza sua tradução.

![Janela de Libras aberta do lado direito, texto sendo clicado e Hugo traduzindo-o.](images/screenshoots/tradutor-de-sites-3.png)

<h2 id='sobre-o-tradutor-mobile'>Sobre o Tradutor Mobile</h2>

A tradução de textos e vídeos também está disponivel na versão mobile, com pequenos ajustes que tornam a usabilidade ainda melhor para o usuário surdo.
A funcionalidade de tradução em dispositivos móveis vem habilitada por padrão, mas você pode removê-la definindo o parâmetro `mobileEnabled` como `false` caso necessário.

![Plugin fechado no mobile, em seguida o Hugo esperando por uma tradução, à frente o Hugo traduzindo.](images/screenshoots/tradutor-mobile.png)

<h2 id='compatibilidade'>Compatibilidade</h2>

O plugin é compatível com a maioria dos navegadores modernos com suporte a WebGL, tais como, Chrome, Firefox, Edge, Safari e Opera.

Abaixo o resultado de testes feitos em sistemas operacionais diferentes usando o plugin em vários navegadores.

| Navegador / S.O.     | Windows | MacOs | Ubuntu (Linux) |
| -------------------- | ------- | ----- | -------------- |
|![Logotipo Chrome](images/icons/chrome.png)    | ✔       | ✔     | ✔             |
|![Logotipo Firefox](images/icons/firefox.png)    | ✔       | ✔     | ✔             |
|![Logotipo Opera](images/icons/opera.png)    | ✔      | ✔     | ✔             |
|![Logotipo Safari](images/icons/safari.png)   | --       | ✔     | --             |
|![Logotipo EDGE](images/icons/edge.png)   | ✔       | --    | --             |
|![Logotipo Internet Explorer 11](images/icons/internet-explorer.png)<span style="margin-left: 15px;">**11**</span>   | ✔       | --    | --             |
|![Logotipo Internet Explorer 10](images/icons/internet-explorer.png)<span style="margin-left: 15px;">**10**</span>   | ✖       | --    | --             |
|![Logotipo Internet Explorer 9](images/icons/internet-explorer.png)<span style="margin-left: 15px;">**9**</span>  | ✖       | --    | --             |
  
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

<h2 id='eventos-introducao'>Eventos</h2>

> Exemplo de Listener de Eventos

```javascript
ht.on('signalized', function () {
  console.log('Nova frase traduzida!');
});
```

```html
<body>
  <!-- Pega a ultima versão do plugin Hand Talk -->
  <script src="https://plugin.handtalk.me/web/latest/handtalk.min.js"></script>

  <script>
    var ht = new HT({
      // Troque por seu token de acesso
      token: '<SEU TOKEN>'
    });

    // Escuta o evento signalized
    ht.on('signalized', function () {
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
| coreReady | Avatar carregado | ```true``` |
| activated | Tradutor de texto foi ativada | ```undefined``` |
| deactivated | Tradutor de texto foi desativada | ```undefined``` |
| signalized | Dispara quando o texto é sinalizado por completo | ```undefined``` |
| errorOnAuth | Erro ao autenticar | ```string: mensagem referente ao erro ocorrido``` |
| errorOnTranslate | Erro ao traduzir texto no servidor da Hand Talk | ```undefined``` |
| notCompatible | Navegador ou hardware não compatível | string: ```'withoutCanvas'``` ou ```'withoutWebGL'``` |
