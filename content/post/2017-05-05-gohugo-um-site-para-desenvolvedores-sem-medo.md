+++
date        = "2017-05-05T09:28:01-03:00"
title       = "GoHugo - Um site para desenvolvedores sem medo"
description = "GoHugo - Um site para desenvolvedores sem medo"
slug        = "gohugo-um-site-para-desenvolvedores-sem-medo"
+++

## Introdução

Aprenda como iniciar com Hugo, vou explicar de forma clara como se gerar um site/blog do zero e fazer o deploy em um servidor rodando nginx e github. Este tutorial fará exatamente isso.

## Instalando Hugo

Vamos começar do zero, como se estivesse acontecido o bigbang a poucos segundos e você precisasse de fogo para se aquecer e se proteger dos perigos que o rondam, como sou usuário do windows em desktop, 

### Windows

Primeiro passo seria a criação da estrutura de pastas, conforme a própria documentação do Hugo sugere a instalação vou seguir aqui também, mão na massa vamos criar as seguintes pastas `c:\hugo`  dentro da pasta vamos criar a subpasta `sites` temos agora duas pasta ***`c:\hugo`*** e ***`c:\hugo\sites`***.

Com a nossa estrutura criada vamos aos download esta e a url para pegar a ultima versão do Hugo https://github.com/spf13/hugo/releases procure pelo arquivo  "Windows-64bit.zip" ***Impossível na era que estamos alguém rodar windows 32Bit*** ao concluir o download extraia o arquivo para a pasta que criamos `c:\hugo` e a partir de agora precisamos definir o set path para o comando ficar conhecido globalmente no windows.

>set PATH=%PATH%;c:\hugo

Se funcionou beleza, caso contrario vai ter que editar as variáveis de ambiente a adicionar na mão, e não estou afim de explicar como se faz isso. Se você de um desenvolvedor já deve ter formatado muito computador e instalação de windows, bem o google esta ai!!!!

## Criando um blog

Antes de mais nada, abre o shell/dos e execute o seguinte comando na pasta `c:\hugo` a pasta pode ser qualquer uma, mas como você esta aprendendo o melhor e seguir o que estou escrevendo. `hugo new site meublog.dev`.  Putz a estrutura esta criada vamos entrar na pasta que o hugo criou `meublog.dev`, nosso primeiro blog feito em hugo esta criado, para visualizar ele sem muita dificuldade rode o comando `hugo serve` dentro da pasta do blog. O próprio hugo vai gerar uma url do tipo ***http://localhost:1313/***

> -- Não vai aparecer nada, pois ainda não temos um layout, tenha paciência!

## Criando o tema e o layout

Dentro do diretório que acabamos de criar vamos rodar o comando `hugo new theme meutema` abra agora um editor de sua preferencia a vamos editar sempre dentro da pasta ***c:\hugo\sites\meublog.dev\themes\meutema*** antes de iniciar a edição do tema vamos rodar o comando para setar o tema em especifico ***`hugo -t meutema`***

### themes/meutema/layouts/
-- Aqui basicamente temos dois arquivos um `404.html` e outro `index.html` dentro desta pasta você pode ter mais arquivos do tipo `rss.xml`.

#### index.html

```
{{ partial "header.html" . }}

<div class="columns">
  {{ partial "sidebar.html" . }}
  <section class="hero is-fullheight is-default is-bold">
    <div class="hero-body">
      <div class="container">
        {{ range first 10 .Data.Pages }}
          {{ if eq .Type  "post" }}
            {{ .Render "summary"}}
          {{ end }}
        {{ end }}            
        </div>
    </div>
  </section>
</div>

{{ partial "footer.html" . }}
```

> -- intendendo as definições aqui escritas `{{ range first 10 .Data.Pages }}` aqui a definição é clara quero que o Hugo me traga os últimos 10 Posts.
> --  `{{ if eq .Type  "post" }}` como o Hugo e inteligente ele vai me apresentar todas os últimos posts não importa em qual "categoria/pasta" ele esteja por isso vamos filtrar apenas os que estão na pasta **post** logo mais vou explicar como iniciar um novo post.

### themes/meutema/layouts/post/
-- essa pasta você terá que criar pois ela também não existe, ela contem a pagina do customização do sumario do post e o próprio post.

#### summary.html

```HTML

<div class="column is-full-desktop content">
  <div class="heading">
    <span class="is-small"> {{ .Date.Format "Mon, Jan 2, 2006" }} </span>
    <h1 class="is-medium"><a href="{{ .Permalink }}"> {{ .Title }} </a></h1>
    <p> {{ .Summary }} </p>
  </div>
</div>
```

#### single.html

```
{{ partial "header.html" . }}

<div class="columns">
  {{ partial "sidebar.html" . }}
  <section class="hero is-fullheight is-default is-bold">
    <div class="hero-body">
      <div class="container">
        <div class="column is-full-desktop content">
          <div class="heading">
            <time class="is-small"> {{ .Date.Format "Mon, Jan 2, 2006" }} </time>
            <h1 class="is-medium"><a href="{{ .Permalink }}"> {{ .Title }} </a></h1>
            <p> {{ .Content }} </p>
          </div>
        </div>       
      </div>
    </div>
  </section>
</div>

{{ partial "footer.html" . }}
```

### themes/meutema/layouts/partials/
-- vamos trabalhar na pasta partials para separar um pouco nosso layout

#### header.html
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title> {{ .Title }} &middot; {{ .Site.Title }} </title>
  <link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/bulma/0.4.1/css/bulma.min.css" />
</head>
<body>
```

#### footer.html
```
<footer class="footer">
  <div class="container">
    <div class="content has-text-centered">
      <p>Meu Copyright</p>
    </div>
  </div>
</footer>
```

#### sidebar.html
-- Esse arquivo não existe você terá que criar ele
```
<div class="column is-half-desktop">
  <section class="hero is-primary is-fullheight is-default is-bold">
    <div class="hero-body">
      <div class="container has-text-centered">
        <div class="title is-1"> {{ .Site.Title }} </div>
        <div class="title is-5"> Descrição </div>
      </div>
    </div>
  </section>
</div>
```
## Quase tudo pronto

-- Bem o site esta quase pronto ao rodar ***hugo serve*** já da para ter uma ideia de como o site vai estar,  agora vem a porte de como criar um novo post, um processo um tanto fácil extremamente. Execute o comando ***hugo new post/meu-post-bonito.md*** pronto temos nosso primeiro post, porem precisamos escrever ele Hugo trabalha com texto do tipo Markdown, se alguém não estiver familiarizado eu utilizo este editor online https://stackedit.io/editor simples e objetivo, segue abaixo um exemplo de um post.

```HTML
+++
date  = "2017-05-05T10:54:26-03:00"
title = "Meu Post tem um titulo bem bonito"
slug  = "posso-configurar-o-slug-facil"
+++
Aqui vai seu texto
```

> -- Duvidas posta nos comentários!!! FLW Pessoal.