# Magamobi Sass Styleguide
![Magamobi](assets/img/logo.png)

Este é um guia de escrita de estilos utilizando o pré-processador Sass seguido pelos desenvolvedores da Magamobi E-Business S/A.

Todas as regras descritas neste foram concebidas e discutidas como melhores práticas pela equipe de desenvolvimento.

**Sugestões e correções são bem vindas!**

## Tópicos

- [Introdução](#introdu%C3%A7%C3%A3o)
- [Princípios](#princ%C3%ADpios)
- [Stack e Instalação]()
- [Terminologias]()
- [Sintaxe e formatação]()
  - [Strings]()
  - [Números]()
  - [Cores]()
  - [Lists]()
  - [Maps]()
  - [Declaração]()
  - [Ordenação]()
  - [Aninhamento de seletores]()
- [Nomeação]()
- [Comentários]()
- [Responsividade]()
  - [Nomeação de breakpoints]()
  - [Uso das media queries]()
- [Variáveis]()
- [Extends]()
- [Mixins]()
- [Condicionais]()
- [Loops]()

## Introdução

Pequenos projetos escritos por pequenas equipes podem não necessitar de um guia de estilos, mas conforme o projeto e a equipe aumentam torna-se insustentável a manutenção de código sem a adoção de um padrão. Nós, desenvolvedores, sabemos que cada um possui sua maneira de trabalhar, de identar, de organizar, ordenar e assim por diante, logo, se não houver uma padronização no que é desenvolvido o próximo a realizar manutenção perderá tempo para entender e até reorganizar o código.

Portanto o objetivo deste guia é proporcionar uma escrita coesa e concisa, escalável e de fácil manutenção a todos envolvidos no projeto que adotar este guia como base.

## Princípios

Princípios básicos a serem adotados por quem utiliza a linguagem Sass são praticamente os mesmos dos adotados para escrita do CSS. O código deve, sem exceção, ser mantido o mais simples possível (utilizando o princípio [KISS](https://pt.wikipedia.org/wiki/Keep_It_Simple)). Esse princípio deve prevalecer sobre outro princípio comum e que também é adotado neste guia, o [DRY](https://pt.wikipedia.org/wiki/Don%27t_repeat_yourself) (Don't Repeat Yourself, não repita a si mesmo), que consiste em não repetir codigo quando o mesmo poderia ser reutilizado.

Isso quer dizer que, por vezes, é preferível repetir trechos para manter a legibilidade e manutenabilidade do código.

## Stack

É interessante que todos os membros da equipe tenham conhecimento a respeito das tecnologias e ferramentas utilizadas e saibam como instalá-las.

### Sass

Segundo a própria documentação:
> Sass é uma extensão de CSS que adiciona novas possibilidades e elegância à linguagem base.

O seu propósito é corrigir as falhas do CSS. Que é uma linguagem simples de aprender mas pode se tornar complexa de ser mantida. Por este motivo foi idealizado o Sass como uma meta-linguagem para melhorar a sintaxe original do CSS, oferencedo mais funcionalidades.

Sass é uma biblioteca (*gem*) Ruby e para instalá-la é necessário possuir o Ruby instalado.

Para Windows é necessário a instalação do [Ruby Installer](http://rubyinstaller.org/). 

Após instalado basta abrir o terminal (linha de comando) e digitar `gem install sass`.

> Para mais informações clique [aqui](http://sass-lang.com/install).

### Compass

O Compass é uma framework CSS que utiliza a linguagem Sass para agregar poder e facilitar a escrita de estilos.

Ele possui uma grande quantidade de mixins previamente implementados que facilitam e diminuem a complexidade com atributos e sua compatibilidade cross-browser, como por exemplo `border-radius` and `text-shadow`. O Compass ainda facilita a utilização de sprites de imagens.

Para instalá-lo você deve possuir o Ruby previamente instalado e executar o seguinte comando no terminal (linha de comando): `gem install compass`.

> Para mais informações clique [aqui](http://compass-style.org/install/).

### Susy

Susy é um grid framework que auxilia na delimitação das colunas de conteúdos, auxiliando a criar layouts responsivos.

Para instalá-lo você deve possuir o Ruby previamente instalado e executar o seguinte comando no terminal (linha de comando): `gem install susy`.

> Para mais informações clique [aqui](http://susydocs.oddbird.net/en/latest/install/).

### Outros Componentes

- **Compass-normalize:** É um plugin do Compass que facilita o uso do `normalize.css`, que é um pequeno CSS cujo objetivo é aumentar a consistência do CSS em diferentes browser, essa consistência é atingida removendo as regras aplicadas por cada browser. Para instalar: `gem install compass-normalize`, mais [aqui](https://github.com/ksmandersen/compass-normalize).
- **Breakpoint:** É uma biblioteca que auxilia a escrita de media queries. Para instalar: `gem install breakpoint`, mais [aqui](https://github.com/at-import/breakpoint/wiki/Installation#installation).
- **optipng:** Otimizador de imagens. Para instalar siga as instruções no [site oficial](http://optipng.sourceforge.net/). Lembrando que no Windows o caminho para o executável deve estar no Path.


## Referências

Este guia de estilos foi baseado nos seguintes conteúdos:
- [Airbnb CSS / Sass Styleguide](https://github.com/airbnb/css)
- [Sass Guidelines](http://sass-guidelin.es/)
- [Sass Style Guide](https://css-tricks.com/sass-style-guide/)