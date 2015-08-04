# Magamobi Sass Styleguide
![Magamobi](assets/img/logo.png)

Este é um guia de escrita de estilos utilizando o pré-processador Sass seguido pelos desenvolvedores da Magamobi E-Business S/A.

Todas as regras descritas neste foram concebidas e discutidas como melhores práticas pela equipe de desenvolvimento.

**Sugestões e correções são bem vindas!**

## Tópicos

- [Introdução](#introdu%C3%A7%C3%A3o)
- [Princípios](#princ%C3%ADpios)
- [Stack]()
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


## Referências

Este guia de estilos foi baseado nos seguintes conteúdos:
- [Airbnb CSS / Sass Styleguide](https://github.com/airbnb/css)
- [Sass Guidelines](http://sass-guidelin.es/)
- [Sass Style Guide](https://css-tricks.com/sass-style-guide/)