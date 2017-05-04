+++
Tags        = ["Development","leandro","foda"]
date        = "2017-05-04T13:56:41-03:00"
menu        = "main"
title       = "Diferencas entre linguagens de programacao para web"
slug        = "diferencas-entre-linguagens-de-programacao-para-web"
description = "Descobrindo o submundo do desenvolvimento para se criar um blog"
+++
> ***ESTE E UM ARTIGO ESCRITO NO ANO 2009 MUITAS COISAS MUDARAM DE LA PARA 2017, ESTOU IMPORTANDO ESTE ARTIGO ANTIGO MEU PARA ESTE NOVO BLOG***

Ola a todos.... para quem não me conhece, sou desenvolvedor front-end e back-end, atualmente trabalho em um grupo de comunicação com 2 portais de noticias de alta escala.

Sempre procuro na internet sobre linguagens de programação e seus diferenciais, qual e a melhor, qual tem mais função, qual a linguagem mais rápida para se programar... vejo poucas comparações sobre isto.. e vejo que algumas linguagens tender a ser melhor que outras porem você demora mais no desenvolvimento e testes, ja outras tendem a ter o desenvolvimento mais ágil e rápido. umas mais robustas outras menos. Todas lhe dão segurança para seu aplicativo, basta saber programar.

Atualmente contamos com inúmeras linguagens de programação para WEB algumas bem difundidas outras nem tanto. Para se ter uma idéia vou citar as Linguagens que mais se usam na internei. ( PHP , PYTHON, JAVA, RUBY, TCL, PERL, CGI, ASP, MIVA, COLDFUSION ) e varias outras que existem por mundo a fora, neste artigo vou comparar as linguagens mais atuais da internet.

## Aqui vou comparar JAVA, RUBY, PYTHON, ASP e PHP.

Se você pesquisar no google sobre cada linguagem você vera o quão ela e difundida pelos usuários, abaixo vou mostrar os resultados buscados no google.com:

    > PHP:      About 7,210,000,000 results
    > ASP:      About 1,250,000,000 results
    > PYTHON:   About 280,000,000 results
    > JAVA:     About 173,000,000 results 
    > RUBY:     About 48,200,000 results

Claro que isto foi uma busca genérica, mas podemos ver que o PHP e a mais comentada, falada, difundida da internet. 

Abaixo vou demonstrar um exemplo de um simples formulário escrita em cada linguagem, para terem uma idéia de qual linguagem e a mais rápida para desenvolvimento, lembrando que estou comparando qual a linguagem mais rápida para desenvolvimento e não a mais flexível, robusta ou segura... Cada linguagem tem sua característica.

### PHP

-- Para executar o código abaixo utilizei um sistema Apache + PHP5

```PHP
<form action="?" method="post">
  Nome: <input type="text" name="nome" />
  Idade: <input type="text" name="idade" />
  <input type="submit" name="submit" />
</form>
<?php
  if(isset($_POST['submit'])) {
    echo "Bem-vindo " . $_POST["nome"] . " voce tem " . $_POST["idade"] . " anos.";
  }
?>
```

### ASP

-- Para rodar o código abaixo utilizei um sistema IIS

```HTML
<form action="?" method="post">
  Nome: <input type="text" name="nome" />
  Idade: <input type="text" name="idade" />
  <input type="submit" name="submit" />
</form>
<%
  if (Request.form("nome") <> "") Then
    response.write("Bem vindo " & request.form("nome") & "<br />")
    response.write("Voce tem " & request.form("idade") & " anos")
  End If
%>
```

### PYTHON

-- Para rodar o código abaixo utilizei um sistema Apache + PYTHON + MOD_PYTHON

```PYTHON
#!/usr/bin/python
import cgi
import cgitb; cgitb.enable()
form = cgi.FieldStorage()
paginahtml = """Content-Type: text/html\n
  <form action="?" method="post">
    Nome: <input type="text" name="nome" />
    Idade: <input type="text" name="idade" />
    <input type="submit" name="submit" />
  </form>
 """
print paginahtml
if 'submit' in form:
 if 'nome' in form:
  if 'idade' in form:
   Nome = form['nome'].value
   Idade = form['idade'].value
   print 'Bem vindo ' + Nome + '<br />'
   print 'Voce tem ' + Idade + ' anos'
```

### RUBY

-- Para testar o código utilizei um ambiente com Apache + RUBY + mod_ruby

***Arquivo HTML***
```HTML
<form action="processa.rb" method="post">
  Nome: <input type="text" name="nome" />
  Idade: <input type="text" name="idade" />
  <input type="submit" name="submit" />
</form>
```

***Arquivo RUBY (processa.rb)***
```RUBY
require 'cgi'
cgi = CGI.new("html4")
cgi.out{
  cgi.html{
    cgi.body{
     cgi.p { "Bem vindo " +cgi['nome'] + "<br />" } +
     cgi.p { "Voce tem " + cgi['idade'] + " anos" }
    }
  }
}
```
### JAVA

-- Não cheguei a testar o código abaixo.. retirei ele do site http://bit.ly/bTIEPC e fiz algumas modificações seguindo a logica.

### ***PROS X CONTRAS***

Vocês acabaram de ver o mesmo modelo de formulário rodado em vários tipos de linguagens umas mais complexas outras nem tanto, algumas com muitos arquivos outras com apenas 1 arquivo. Todos os códigos que escrevi acima, foram revisados e testados a não ser o JAVA pois não tenho servidor para rodar e testar o mesmo, as demais foram todas testadas em Ambiente LINUX + APACHE.
Vou começar a citar os PROS de cada linguagem que vimos a cima e logo abaixo irei resumir em poucas linhas os CONTRA de cada linguagem, para assim 

### ***PROS de Cada Linguagem***

> ***PHP***

> -- PHP é considerada mais rápida e mais eficiente para tarefas complexas e simples de programação e para tentar novas idéias. 
Tem otina integração com diversos banco de dados, sistema de arquivos, manipulação de imagens(requer plugin GD), suporta expressões regulares, tem api própria para manipulação de banco de dados(PDO).
Existe uma vasta documentação e artigos na internet sobre o PHP, muitos scripts prontos, vários frameworks para agilizar o desenvolvimento.
Tem funcionamento com vários Web Server`s incluindo Apache o que significa hospedagem barata.
O manual online é amplamente considerado como o melhor de qualquer linguagem de programação.
Não precisa ser Compilado nada. com algumas linhas de código você já cria um programa.

----------

> ***ASP***

> -- Código-fonte protegido através da ferramenta de encritação da Microsoft, que já vem incluído no IIS.
Banco de dados a linguagem ASP funciona muito bem para visualizar e manipular informações em bancos de dados que suportam OBDC.
Linguagem similar ao Visual Basic - se você já programa em Visual Basic terá muita facilidade em aprender ASP, pois ambas as linguagens são parecidas.
Aprendizado descomplicado - mesmo que você não conheça Visual Basic, poderá aprender ASP sem dificuldades. A linguagem é clara e cheia de recursos.
A Microsoft tem uma ampla documentação sobre ASP e Visual Basic, alem de vários artigos, sites e scripts espalhados pela internet.

----------

> ***PYTHON***

> -- Python inclui módulos, exceções, tipagem dinâmica, muito alto nível, os tipos de dados dinâmicos e classes. Possui interfaces para as chamadas de sistema e bibliotecas, bem como aos vários sistemas baseados no Windows. Livre disponibilidade (como Perl, Python é open source). Estabilidade (Python está na versão 2.6.6 neste momento e, como já observado anteriormente, é mais velho do que Java). Bom suporte para objetos, módulos e outros mecanismos de reutilização. Fácil integração e extensibilidade usando C e Java.
Economias de custos no desenvolvimento e manutenção. Roda em Plataforma Windows ou Linux(Unix).

----------

> ***JAVA***

> -- Sintaxe familiar para programadores que sabem qualquer linguagem baseada em C.
A Plataforma JAVA tem uma grande gama de bibliotecas e classes. Boa portabilidade podendo rodar em qualquer sistema operacional. Tem uma documentação completa na internet alem de vários frameworks para lhe ajudar a desenvolver mais rapidamente seus sistemas.
Varias IDE`s para agilizar o desenvolvimento e manutenção de aplicações escritas em JAVA.
Tem um ótimo desempenho para aplicações de larga escala.
Aplicativos podem ser desenvolvidos mais rapidamente que em C/C++.

----------

> ***RUBY***

> -- Vou citar os prós do Ruby on Rails (Framework  escrita em Ruby para desenvolvimento web). Ótima linguagem para desenvolvimento rápido, nos economiza uma tonelada de trabalho ao se criar um novo aplicativo.
Ruby é uma linguagem concisa (em comparação com mais tradição linguagens C-style), bem pensado, e muito legível.
Lotes de interessante plug-ins e gemas você pode usar para poupar tempo.
Tem uma boa documentação na internet, muitos artigos e tutoriais estão espalhados por ai.. 
Funciona em ambientes Linux(Unix) lhe trazendo muito economia ou você pode utilizar clusters de VPS. ruby te da o suporte a isso. Ruby é uma linguagem totalmente orientada a objetos apresentados.
A tecnologia template construído em Rails pode ser usado para gerar páginas web, e-mails, documentos XML ou qualquer documento de texto que exige conteúdo dinâmico.

### ***CONTRAS de Cada Linguagem***

> ***PHP***

> -- Fraca Tipagem, esta engatinhando a Orientação de Objetos, Não muito rápido por não trabalhar com tipagem, tudo é dinâmico, a verificação também é feita dinâmica, aumentando o tempo de interpretação.

----------

> ***ASP***

> -- Roda somente em ambiente Windows sob o IIS da Microsoft.

----------

> ***PYTHON***

> -- Poucos artigos na web falando sobre python for web. Poucos e raros profissionais. Ausência de um apoio comercial, mesmo para um projeto Open Source (embora esta situação está mudando). Software de desempenho (embora benchmarks, demonstraram repetidamente Python é comparável ao de Java, na maioria dos aplicativos). Python sofre com a falta de documentação, extensa acessível e livros publicados.

----------

> ***JAVA***

> -- Grande parte do código Java escrito por programadores experientes. Utiliza muita memoria da maquina que esta rodando o seu código. Se você não for cuidadoso, você pode escrever programas lentos. Bugs em implementações de biblioteca. Tende a ter a mão e obra mais cara dentre as linguagens que citei no artigo.

----------

> ***RUBY***

> -- Difícil encontrar hospedagem a preços acessíveis. Difícil de encontrar profissionais para desenvolvimento. Nem tudo o que se lé sobre ruby realmente funciona. Mão de obra cara.

----------

Acho que deu para se ter uma idéia de qual seria a melhor linguagem para desenvolver seu sistema, claro vale ressaltar que você precisa fazer um estudo sobre qual a espectativa de crescimento do seu projeto... para poder escolher a melhor linguagem adequada... Muitos portais nacionais são desenvolvidos em JAVA pela sua escalabilidade... mas temos também enormes sites escritos em PHP (facebook.com).. no caso de RUBY temos o (twitter.com)...

Vou terminando este artigo e qualquer duvida podem perguntar se estiver no meu conhecimento responderei.
