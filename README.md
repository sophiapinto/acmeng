<p align="center">

  <h3 align="center">Site oficial da ACM Engenharia Civil</h3>

<p align="center">
  <img src="https://img.shields.io/static/v1?label=Lincense&message=MIT&color=0000ff " alt="License" />
</p>

<p align="center">
    Projeto desenvolvido para empresa do ramo da Engenharia Civil.
    <br />
  </p>
</p>

## :book: Sobre o projeto

Proposta a criação de um projeto utilizando SCSS e Node.js que apresenta-se:  

  - [x] Responsável técnico
  - [x] Projetos realizados
  - [x] Formulário de contato

Você pode ver a demo do projeto [aqui](https://acmengenhariacivil.com.br).


## :bricks: Instalação

Este projeto usa [Node.js](https://nodejs.org/en/) e [Yarn](https://yarnpkg.com), você precisará deles para instalar as dependências.

### :construction: Pré-requisitos

Clone este repositório:

```bash

$ git clone https://github.com/sophiapinto/acmeng.git

# Entre na pasta `acmeng`:

$ cd acmeng
```

🚨 Se você não possui git instalado em sua máquina, você pode instalá-lo [aqui](https://git-scm.com/downloads).

### :construction: Instalando dependências

Na pasta acmeng, instale as dependências pelo seguinte comando:

```bash
$ yarn install
```

### :arrow_forward: Rodando o Projeto

Rode os seguintes comando:

```bash

# Para o servidor

$ yarn compile:scss

```

Depois de executar yarn compile:scss, abra o index.html dentro do seu navegador favorito ou usando a extensão do servidor ativo.

## :book: Envie e-mail a partir de um formulário HTML *estático* usando o Google Apps Mail!

### 1. Planilha de modelo

> Sample: https://docs.google.com/spreadsheets/d/1Bn4m6iA_Xch1zzhNvo_6CoQWqOAgwwkOWJKC-phHx2Q/copy

Faça login na sua conta Google e clique em "**Fazer uma cópia**..."

![1-make-copy](https://user-images.githubusercontent.com/1406149/29245471-feb7b034-7f97-11e7-9c0d-f06238e8362b.png)

Isso deverá exibir para você algo como isso:

![2-copy-of-sheet](https://cloud.githubusercontent.com/assets/194400/10559710/3aec92f0-74ef-11e5-9295-f1988a23257b.png)

> Observação: fique à vontade para alterar o nome da Cópia para o que quiser, isso não vai afetar o resultado.

### 2. No Editor de Script

Abra o **Editor de script...** clicando em "**Ferramentas**" > "**Editor de script...**"

![2 script-editor](https://cloud.githubusercontent.com/assets/194400/10559732/8db2b9f6-74ef-11e5-8bf2-de286f079929.png)

### 3. Defina o valor de `TO_ADDRESS` no Script

### 4. Salve uma *nova versão* do seu Script

### 5. Publique o script *atualizado* como um Web App

Selecione a versão *mais recente* do projeto para publicar.  
:warning: Aviso: Você *deve* selecionar a opção `Qualquer um, mesmo anônimo` (`Anyone, even anonymous`) como a opção em 'Quem tem acesso ao aplicativo' ('Who has access to the app') ou as respostas do formulário não serão adicionadas à planilha! :warning:

### 6. Autorize o script a enviar e-mails

![5 auth-required](https://cloud.githubusercontent.com/assets/194400/10560412/89d3fb0c-7502-11e5-81ce-fb239bf545b2.png)

A menos que você [verifique seu script com o Google](https://developers.google.com/apps-script/guides/client-verification#requesting_verification), você precisará clicar em "Avançado" e "Ir para ... (inseguro)" para conceder permissões a este aplicativo.

![5-auth-failed-verification](https://user-images.githubusercontent.com/1406149/44312495-79583780-a3b6-11e8-9740-8c9b50f195d6.png)

![5-allow-sending-emails](https://cloud.githubusercontent.com/assets/194400/10560416/a86a26ae-7502-11e5-9add-d5081d409af4.png)

Copie o URL do web app para a área de transferência / bloco de notas.
Em seguida, clique em "OK".

![22 1-deploy-as-web-app](https://cloud.githubusercontent.com/assets/194400/10558255/6eec31e2-74c1-11e5-9c07-cea6209526df.png)


### 7. Crie seu formulário HTML *básico*

Usando o modelo `index.html` deste repositório,
crie seu próprio arquivo HTML com o formulário básico.

> Lembre-se de alterar a propriedade `action` do formulário com a URL você copiou no passo anterior:

![7-html-form](https://user-images.githubusercontent.com/1406149/44312329-9b9c8600-a3b3-11e8-9816-4bdbbc96dc62.png)

### 8. Abra o formulário HTML (*página*) no seu navegador

Preencha o formulário HTML com alguns dados de teste.

Envie o formulário. Você deve ver uma confirmação de que foi enviado.

### 9. Verifique a caixa de entrada do e-mail que você configurou

> ***Pronto***. É isso. Você acabou de criar um formulário HTML que envia e-mails!

# *Parte Dois - Deixe seu formulário mais bonito* ...

### 10. Enviar o formulário usando **JavaScript** "***AJAX***"

Para *evitar* que a página mude para a resposta/resultado `JSON`,
precisamos enviar o formulário usando ***AJAX***.

Baixe [este arquivo Javascript](form-submission-handler.js) e atualize seu `index.html` para incluir ele ao *final* do arquivo
(*antes do fechamento da tag`</body>`)

```html
<script data-cfasync="false" type="text/javascript" src="form-submission-handler.js"></script>
```

**Aviso**: Se você não definiu a variável `TO_ADDRESS` no Passo 3, então será necessário incluir um atributo `data-email="example@email.net"` dentro do elemento principal do formulário. Veja o formulário de exemplo para mais detalhes. Caso contrário, se você definiu essa variável, não precisa deste atributo no formulário.

Isso mantém a pessoa na mesma página. Sem atualizar. O próximo passo é fazer uma mensagem de agradecimento aparecer.

### 11. Adicione uma mensagem de agradecimento personalizada exibida quando o formulário for enviado

Depois de concluir o passo 10, você pode escolher adicionar uma mensagem de agradecimento após o envio. Adicione o seguinte código entre as tags `<form>` e `</form>`:

```html
<div style="display:none" class="thankyou_message">
 <!-- Você pode personalizar a mensagem de agradecimento editando o código abaixo -->
 <h2><em>Thanks</em> for contacting us! We will get back to you soon!
 </h2>
</div>
```

Isso agora exibirá uma *mensagem* de "Agradecimento" quando o formulário for enviado:

![thankyou message](https://cloud.githubusercontent.com/assets/194400/10561147/4086a89a-7517-11e5-840d-7f490353e225.png)

Ajuste sua mensagem editando o conteúdo da div `thankyou_message`.

### 12. Usando CSS para fazer o formulário *ficar bonito*

Para **este** *exemplo* estamos usando ***Pure CSS***: https://purecss.io/start/ 
porque ele é ***leve*** (***4,0 KB minificado e gzipado***)
e *resolve* nosso "*problema*" atual: fazer ele ficar bonito.

![PureCSS-Logo-Intro](https://github-cloud.s3.amazonaws.com/assets/194400/10565838/72d6d52a-75d2-11e5-9b92-ca02b1124920.png)

![PureCSS-module-sizes](https://github-cloud.s3.amazonaws.com/assets/194400/10565844/8f4885a0-75d2-11e5-9490-e3fc42c32616.png)

Sem gastar *tanto* tempo, podemos fazer o formulário *parecer* ***muito mais*** agradável:

![contact form with pure css](https://github-cloud.s3.amazonaws.com/assets/194400/10566392/f38bc454-75dd-11e5-85dd-6819494a98f2.png)

### 13. Faça o e-mail ficar bonito também!

Por padrão, o corpo do e-mail enviado contém os pares de chave-valor do formulário, com a chave como um `<h4>` e o valor como um `<div>`. Esta é uma visulização relativamente básica e infalível dos dados.

Você deve obter algo parecido com:
![Nicely formatted email](https://cloud.githubusercontent.com/assets/5610747/22168070/335ad734-df62-11e6-9523-6e193e94151f.png)

> Lembre-se de que este é um projeto em andamento e pode permitir que você receba mais do que esperava no e-mail. Como o conteúdo do e-mail agora está passando por todos os dados enviados no formulário, se um robô ou usuário mal-intencionado decidir fazer um `POST` com mais dados do que você pediu, você provavelmente os receberá na sua caixa de entrada. Use com cautela por enquanto. Estamos investigando melhorias.

No entanto, você pode modificar isso, por meio do **Editor de script**. A linha:

```javascript
result += "<h4 style='text-transform: capitalize; margin-bottom: 0'>" + key + "</h4><div>" + obj[key] + "</div>";
```

tem tudo que você precisa. Você pode ajustar a marcação para se adequar à sua necessidade. 
Escolhemos um `<h4>` porque era o melhor tamanho para o e-mail e adicionamos uma pequena quantidade de CSS para corrigir a capitalização (as letras são todas minúsculas no objeto JS) e um pouco de espaçamento por padrão. 
Embora estilos inline como estes sejam geralmente má prática em páginas web normais, para um HTML no e-mail eles são a única maneira fiável de usar CSS!
Optamos por um `<div>` para a parte do valor, porque ele poderia ser qualquer coisa - uma linha só, múltiplas linhas (um `<p>` por exemplo não seria suficiente).

Aproveitando que já estamos aqui, também há uma opção `replyTo` para o método `sendEmail()` que está comentada por padrão:

```javascript
MailApp.sendEmail({
  to: TO_ADDRESS,
  subject: "Contact form submitted",
  // replyTo: String(mailData.email), // Isso é opcional e depende do seu formulário possuir um campo denominado `email`
  htmlBody: formatMailBody(mailData)
});
```

Você pode descomentar essa opção se quiser adicionar um campo de "Responder para..." no seu e-mail. O exemplo no script definirá o "Responder para..." (`reply-to`) como o e-mail enviado no formulário.

A documentação do Google fornece mais informações sobre o método `MailApp.sendEmail` (por exemplo `cc`/`bcc` etc.) se estiver interessado: https://developers.google.com/apps-script/reference/mail/mail-app

# *Parte Três - Armazenar os dados enviados pelo formulário de contato em uma planilha*

Enviar os dados do formulário diretamente para a caixa de entrada 
do seu e-mail é um *ótimo* primeiro passo, mas podemos fazer melhor.
Além disso, conforme já vimos acima, o Google tem limites de quantos 
e-mails você pode enviar por dia, portanto, armazenar os dados em uma 
planilha é mais seguro e menos sujeito a perda de informações.

### 14. Adicione a função `record_data` no seu Google Apps Script

![record_data example](https://cloud.githubusercontent.com/assets/194400/10581613/8b4f9ad4-767b-11e5-90cc-962a9d6acc91.png)

Isso irá salvar os dados recebidos do `POST` como uma *linha* na planilha.
Consulte: [**google-apps-script.js**](google-apps-script.js) para o código completo que você pode *copiar e colar*.

### 15. Salve uma nova versão e publique-a novamente

Siga os passos 4, 5 e 6 para salvar uma nova versão e ***publicar novamente*** (***re-publish***) o script.

### 16. Teste novamente o envio do formulário

![submit the form](https://cloud.githubusercontent.com/assets/194400/10582654/cf3081e6-7680-11e5-9fd1-b989a8ba0b65.png)

### 17. Confirme se os dados foram inseridos na planilha

![17-confirm-data-inserted](https://cloud.githubusercontent.com/assets/194400/10582676/eb8af5d8-7680-11e5-92bb-30dd08d2d7b3.png)


### _Live_ Server (_no seu `localhost`_)

Como estamos carregando arquivos **.js** externos, nosso navegador 
não nos _permite_ simplesmente abrir o **index.html** de um diretório 
local para testar o formulário.

Abra seu terminal e execute o commando 
para _**instalar** o **node_modules** e **iniciar** o **live server**_:

```sh
npm install live-server --save-dev && node_modules/.bin/live-server --port=8000
```

A instalação levará um minuto para concluir, 
mas assim que terminar, seu `live-server` será inicializado.

Isso inicia um servidor HTTP Node.js na porta 8000
e abre o formulário, que você acabou de criar, em seu navegador padrão.
Se quiser atualizar os estilos de formulário em **style.css**
ou o Javascript client-side em **form-submit-handler.js**,
certifique-se de editar o **index.html** para carregar esses recursos
localmente em vez de por meio do GitHub.

> **Observação**: Esta é apenas uma _pequena_ amostra do Node.js para iniciantes.
Você **não** precisa do Node.js para "publicar" este formulário,
você consegue fazer ele funcionar em **_qualquer_ servidor web** que hospede HTML/CSS/JavaScript.
Se você nunca usou Node.js antes, veja: http://nodeguide.com/beginner.html,
mas para os fins deste exercício (_enviar um formulário **sem** um servidor_),
você _não **precisa**_ do Node.js ou do `live-server`
eles são apenas uma adição _agradável_ para quando se está criando
seu formulário, pois eles automaticamente recarregam a página quando você
faz alterações nos arquivos do projeto usando seu editor de texto!


# *Quer mais*?

Se quiser que continuemos com este tutorial, [***por favor nos avise***!](https://github.com/dwyl/learn-to-send-email-via-google-script-html-no-server/issues)

Para sua conveniência, hospedamos uma demonstração do formulário no GitHub Pages,
confira para ver o código e como funciona:
https://dwyl.github.io/learn-to-send-email-via-google-script-html-no-server/


## Adicione seus próprios campos!

Em resposta à [solicitação de Henry Beary](https://github.com/dwyl/learn-to-send-email-via-google-script-html-no-server/issues/9),
tornamos o tratamento do formulário *genérico*, o que significa que agora você pode adicionar quaisquer campos que desejar ao formulário.

Também criamos um formulário, `test.html`, que usa todos os tipos de elementos de input para que você possa simplesmente copiar e colar os elementos como quiser em seu próprio formulário. Apenas certifique-se de atualizar seus `name`s e `id`s. Você pode encontrar um exemplo funcional deste formulário de teste aqui:
https://dwyl.github.io/learn-to-send-email-via-google-script-html-no-server/test.html

Lembre-se de incluir os campos *dentro* do formulário que possui a classe `gform` 
e certifique-se de que o `name` do elemento do formulário corresponda ao título da nova coluna em sua planilha. 
Por exemplo:
```HTML
<fieldset class="pure-group">
  <label for="color">Favourite Color: </label>
  <input id="color" name="color" placeholder="green" />
</fieldset>
```
Com isso você consegue salvar a cor favorita da pessoa. 
Por exemplo:
![new-field-contains-data](https://cloud.githubusercontent.com/assets/194400/11547132/9f162f6a-9949-11e5-89ac-aeb91e025844.png)

Nos avisem se tiver quaisquer dúvidas!

## Enviando arquivos

[Este material](https://www.labnol.org/internet/receive-files-in-google-drive/19697/) pode ajudá-lo a dar início no envio de arquivos para o Google Drive a partir do Google Script.


## Perguntas Frequentes (FAQ's)

1. _Como posso obter ajuda para usar este tutorial?_

- Sinta-se à vontade para [criar uma issue](https://github.com/dwyl/learn-to-send-email-via-google-script-html-no-server/issues/new) descrevendo detalhadamente quais passos você realizou e o que não está funcionando. Para obter uma resposta relevante, forneça um [exemplo funcional](https://stackoverflow.com/help/mcve) que reproduza seu problema. Por exemplo, veja [este CodePen de modelo](https://codepen.io/mckennapsean/pen/gdYzNY).

2. _Posso obter permissão de edição na planilha de modelo?_

- Não. Ela está sendo usada para demonstrar um exemplo funcional que qualquer pessoa pode copiar, e uma versão editável poderia quebrar acidentalmente, ou maliciosamente, por qualquer usuário.

3. _Por que a página está me encaminhando para um monte de texto quando clico em enviar?_

- Você não está carregando corretamente o JavaScript necessário para enviar os dados via AJAX ou seu navegador não oferece suporte a AJAX. Por favor, consulte a Parte 2 e verifique os logs do seu console caso esteja encontrando erros.

4. _Por que a página não está enviando o formulário com sucesso?_

- Verifique os logs do console JavaScript do seu navegador. Pode haver um erro ao ler o JavaScript que fornecemos. Pode haver erros ao enviar o formulário. É necessário que seu formulário tenha uma classe de `gform` e também um atributo `data-email` se você não definiu a variável `TO_ADDRESS` dentro do arquivo do Google Script. Além disso, o código JavaScript fornecido também espera encontrar um elemento de formulário de e-mail que usa para verificação, uma mensagem de aviso para esse elemento quando um e-mail impróprio é enviado e, em seguida, um div de `agradecimento` (`thank-you`) também, que é mostrado após ser enviado com sucesso. Certifique-se de que todos esses elementos HTML estejam em seu formulário. Consulte o arquivo de exemplo para obter códigos que você pode copiar e colar. Quando tiver todos esses elementos e um formulário configurado corretamente, não deverá ver nenhuma mensagem de erro no console JavaScript ao clicar em enviar.

5. _A página está dizendo que meus dados foram enviados, mas por que eles não estão sendo salvos ou enviados para mim?_

- Quando você copiou a planilha e publicou o Google Script, você definiu as permissões como "Qualquer pessoa, até mesmo anônima" ("Anyone, even Anonymous")? Isso é necessário para que o formulário funcione, já que qualquer pessoa na Internet pode clicar em enviar para fornecer seus dados. Certifique-se de ter publicado a versão adequada do script e usado "Gerenciar versões..." ao fazer alterações.

6. _Como altero os e-mails que este script envia?_

- Você pode ajustar o Google Script no servidor para enviar e-mails para qualquer pessoa e no formato que quiser. Isso pode ser usado para enviar um e-mail de confirmação para aqueles que entram em contato com você, mas não adicionamos esse recurso a este tutorial para evitar possível spam. Porém, o remetente do e-mail sempre será a conta do Google que você usar para criar o formulário/script. Mais detalhes sobre como personalizar o e-mail podem ser encontrados [na documentação da `MailApp` API](https://developers.google.com/apps-script/reference/mail/mail-app). Em vez disso, você pode usar [a `GmailApp` API](https://developers.google.com/apps-script/reference/gmail/), que pode ser mais flexível para certos casos de uso.


7. _Isso é seguro? Posso usá-lo para dados sensíveis?_

- Não. Embora os dados enviados por POST possam estar mais protegidos, as informações podem ser facilmente interceptadas por terceiros ou intermediários, e o Google tem acesso total aos dados em uma planilha do Google. E-mail também não é um meio de comunicação muito seguro por padrão. Recomendamos que você invista em uma plataforma e servidor seguros para armazenar seus dados, se isso for um requisito.


## Leituras complementares

+ Google Apps Scripts Basics: https://developers.google.com/apps-script/articles
+ Logger (como `console.log`):
https://developers.google.com/apps-script/reference/base/logger
+ Mail Merge simples utilizando Google Spreadsheets:
https://developers.google.com/apps-script/articles/mail_merge
+ Tutorial original: AJAX post to google spreadsheet: https://stackoverflow.com/questions/10000020/ajax-post-to-google-spreadsheet que direciona para:
  + https://mashe.hawksey.info/2011/10/google-spreadsheets-as-a-database-insert-with-apps-script-form-postget-submit-method/

## :page_facing_up: Licença

Este projeto usa a licença [MIT](https://github.com/3salles/user-crud/blob/main/LICENSE).

## :woman_technologist: :man_technologist: Autoria

[Sophia Pinto](https://github.com/sophiapinto)

<p align="center">Developed with 💜 </p>


