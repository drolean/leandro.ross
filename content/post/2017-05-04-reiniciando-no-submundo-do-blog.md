+++
date        = "2017-05-04T09:43:21-03:00"
title       = "Reiniciando no submundo do Blog"
description = "Descobrindo o submundo do desenvolvimento para se criar um blog"
slug        = "reiniciando-no-submundo-do-blog"
+++
### Ahhhhhhhhhhhhh!!!!!!!! 

Vou criar um blog, que coisa mais fácil vai no site do **wordpress** e cria um gratuito ou vai no **blogspot** e cria um gratuito ou **medium** ou não cria nada. Como iniciar um blog, sendo um developer e não querer utilizar tecnologias que você conhece, quero criar um blog mas quero algo novo, quero algo desafiador. 

O que fazer!!! Quero criar um blog, mas quero ser diferente, vou contar um pouco dos últimos dois dias ate criar esse blog. *Nem sei por que criei este blog, talvez uma emoção de momento ou para se ter um domínio para hospedar meus trabalhos, vai saber nem eu mesmo me intendo*

**1° Dia**

Procurar novas tecnologias que eu não conheço ou que nunca trabalhei, como um belo intendedor de google "como buscar uma informação", fiz uma pesquisa por tecnologias que me chamaram atenção logo na apresentação e em sua data de criação, quanto mais recente melhor para o meu projeto. Primeiro fui buscar tecnologias de CSS, Javascript e um framework novo ou algo que me permitisse desenvolver e publicar esse meu blog.

Abaixo vou citar algumas coisas na qual encontrei nesse primeiro momento.

> ***CSS Framework***

> -- A primeira busca por coisas novas me surgiu esses dois caras, um já tinha visto em alguns videos o pessoal o utilizar o **Bulma** porem o outro nunca tinha ouvido falar, fui conferir a documentação a comunidade e o ultimo release quando foi lançado. O que mais chamou a minha atenção foi o **Spectre**, acho que pela documentação que me apresentou alguns exemplos interessantes. Ao escrever este texto que fui notar, sou entusiasta e desenvolvedor de **SASS** e notei agora que o escolhido e **LESS**, mesmo assim gostei do Spectre para este projeto. *pronto agora tenho um framework de css*
> 
> - https://picturepan2.github.io/spectre/index.html
> - http://bulma.io/

> ***Javascript***

> -- Com javascript foi a mesma coisa que a busca de CSS o primeiro resultado e o unico foi este cara, que apenas dei uma olhada na documentação *sabe aquela olhada que o scroll desce em um segundo* foi bem isso que eu fiz e coloquei na mente que iria usar ele, sem mesmo saber o por que usuária uma lib de javascript. **nem tem javascript no site**
> 
> - https://svelte.technology/

> ***Web Framework***

> -- Não sei se posso dizer Web Framework mas vou citar assim, para a tecnologia que iria gerir o blog, esta busca foi complicada e difícil encontrar algo novo ainda mais quando você e envolvido já em uma comunidade como no meu caso, trabalho com **PHP** mais precisamente com **Laravel** e muitas das minhas buscas me retornam frameworks de php porem eu queria algo novo, e nas buscas os resultados eram sempre os mesmos "Synfony, Laravel, YUII, CodeIgniter, Cake ou Zend" já passei por alguns desses citados, e como seria um blog algo fácil e sem complicação, a minha busca passou a procurar algo mais dinâmico, para um desenvolvimento simples e rápido.
> -- Em um post do SitePoint vi um resultado de pesquisa e um nome me chamou a atenção **PHPIXIE** em primeira visita ao site um texto e um botão muito chamativo **"LEARN PHPIXIE IN 30 MINUTES"** opa acho que encontrei o meu novo framework.
>
> - https://phpixie.com/

> ***Novas Definições***

> -- O que e ditado, o que novo, quais os novos caminhos, novas regras, o que tem de novo em desenvolvimento... Como um bom desenvolvedor eu me atualizo constantemente, sobre tendencias, tecnologias e afins relacionados a web e desenvolvimento, porem em meio a atualidade de hoje, vivemos uma constante mutação de tecnologias e parâmetros, como se ditássemos o que e bom e oque e ruim. Acho que isso e bom, a troca de informação, experiencia e etc, para poder chegar em algo útil a todos. Por isso fiz uma busca para saber o que poderia colocar de novo em meu novo projeto, alguma tendencia nova na qual não tinha visto ainda ou algo inusitado, foi difícil achar e creio que não achei nenhum novidade, levando em consideração o meu conhecimento na área.
>
> - Definições HTML5 fui rever se tinha mais alguma mudança ou boa pratica, para isso consultei este artigo https://www.sitepoint.com/defining-the-sample-sites-page-structure/
> - Por mais que seja um blog, preciso colocar boas praticas no código e definições ***TAG's*** para reconhecimento de sistemas terceiros, para isso eu achei este artigo bem interessante https://mention.com/blog/digital-marketing-checklists/
> - Checklist como qualquer produto precisamos criar um checklist de coisas para publicar nosso projeto aqui esta um link contendo alguns items a se checar https://moz.com/blog/launching-new-website-seo-checklist-whiteboard-friday - http://www.developerdrive.com/2017/02/the-ultimate-website-launch-checklist/
> 

**2° Dia**

Bom já com muitos dados coletados, chegou a hora de colocar a mão na massa, a primeira coisa que eu fiz foi seguir o tutorial do ***PHPIXIE*** https://phpixie.com/quickstart.html e la fui eu feliz da vida por entrar em contato com um novo framework, fiz a instalação dele via composer, setei o host no nginx e abri a url que designei para ele, voilá apareceu a primeira pagina um sinal que esta tudo certo, antes de mais nada fui setar o banco de dados, `resumindo como eu queria algo simples pensei em utilizar sqlite para database` veio a primeira decepção tentei de todas as formas me conectar a uma base sqlite previamente criada sem nada e não consegui, insisti por alguns minutos, fucei a documentação entrei no gitter e não consegui, tive que setar o mysql OK funcionando perfeito agora com banco de dados, rodei a primeira migration e achei que estaria na hora de definir o layout. 

Pensei em algo simples e funcional e ***MOBILE FIRST*** com o framework já em mãos segui o mesmo modelo da documentação que achei bonita e fui construindo, ate chegar esse modelo que você esta vendo.

Como o layout pronto e já separado continuei o tutorial do ***PHPIXIE*** até a etapa de relacionamentos, onde tive muita dor de cabeça `3. ORM relationships and pagination` exatamente nesta parte. A Partir dai perdi algumas horas (duas ou três) ate me decepcionar completamente.

![Gitter Chat](http://image.prntscr.com/image/4fa04774f3d24965b6a26a14a4203eb2.png)

Não vou desistir, fui ao google novamente procurar por `Blog Source site:github.com` e la me apareceram muitas coisas em Python, GO, PHP, Wordpress e etc... Baixei alguns e tentei compilar fazer funcionar mas todos sem retorno.

***Agulha no palheiro***
Nessa busca me deparei com o seguinte resultado que me remetia a um repositório no github https://github.com/jessfraz/blog olhei o código e não achei muito código, fiz o clone do repo e vi que tinha um arquivo `release.sh` rodei ele e logo o console me retornou erro:

<pre>Building site with hugo
./release.sh: line 28: hugo: command not found</pre>

OPA o que é HUGO, quem seria HUGO, vou atras do HUGO, e la vou eu de novo ao google buscar por ***"Building site with hugo"*** e o primeiro resultado https://gohugo.io/overview/quickstart/  um video logo de cara "***A New Hugo Site in Under 2 Minutes***" CARALH0 achei minha pepita de ouro, segui o tutorial e criei meu primeiro site feito em **HUGO** logo apos já quis portar o layouts que estava no PHPIXIE para o novo HUGO, fui olhando o tema que tinha acabo de instalar e vi a facilidade do mesmo.

> ***E CA ESTOU UM SITE FEITO EM HUGO COM SEUS POSTS ESCRITOS EM MARKDOWN COM CÓDIGO ABERTO, CASO NÃO ACREDITE VEJA O REPO ***https://github.com/drolean/leandro.ross

-- como e bom ter um site que você pode chamar de seu, acabei de atualizar minhas redes com meu endereço de site pessoal \o/