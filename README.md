# Magamobi Sass Styleguide
![Magamobi](assets/img/logo.png)

Este é um guia de escrita de estilos utilizando o pré-processador Sass seguido pelos desenvolvedores da Magamobi E-Business S/A.

Todas as regras descritas neste foram concebidas e discutidas como melhores práticas pela equipe de desenvolvimento.

**Sugestões e correções são bem vindas!**

## Tópicos

- [Introdução](#introdução)
- [Princípios](#princípios)
- [Stack e Instalação](#stack-e-instalação)
  - [Sass](#sass)
  - [Compass](#compass)
  - [Susy](#susy)
  - [Outros Componentes](#outros-componentes)
- [Terminologias](#terminologias)
  - [Propriedade](#propriedade)
  - [Seletor](#seletor)
  - [Regra](#regra)
- [Sintaxe e formatação](#sintaxe-e-formatacao)
  - [Strings](#strings)
  - [Números](#numeros)
  - [Cores](#cores)
  - [Lists](#lists)
  - [Maps](#maps)
  - [Declaração](#declaracao)
  - [Ordenação](#ordenacao)
  - [Aninhamento de seletores](#aninhamento-e-seletores)
- [Nomeação](#nomeacao)
- [Comentários](#comentarios)
- [Responsividade](#responsividade)
  - [Nomeação de breakpoints](#nomeacao-de-breakpoints)
  - [Uso das media queries](#uso-das-media-queries)
- [Variáveis](#variaveis)
<!-- - [Extends](#extends) -->
<!-- - [Mixins](#mixins) -->
<!-- - [Condicionais](#condicionais) -->
<!-- - [Loops](#loops) -->

## Introdução

Pequenos projetos escritos por pequenas equipes podem não necessitar de um guia de estilos, mas conforme o projeto e a equipe aumentam torna-se insustentável a manutenção de código sem a adoção de um padrão. Nós, desenvolvedores, sabemos que cada um possui sua maneira de trabalhar, de identar, de organizar, ordenar e assim por diante, logo, se não houver uma padronização no que é desenvolvido o próximo a realizar manutenção perderá tempo para entender e até reorganizar o código.

Portanto o objetivo deste guia é proporcionar uma escrita coesa e concisa, escalável e de fácil manutenção a todos envolvidos no projeto que adotar este guia como base.

## Princípios

Princípios básicos a serem adotados por quem utiliza a linguagem Sass são praticamente os mesmos dos adotados para escrita do CSS. O código deve, sem exceção, ser mantido o mais simples possível (utilizando o princípio [KISS](https://pt.wikipedia.org/wiki/Keep_It_Simple)). Esse princípio deve prevalecer sobre outro princípio comum e que também é adotado neste guia, o [DRY](https://pt.wikipedia.org/wiki/Don%27t_repeat_yourself) (Don't Repeat Yourself, não repita a si mesmo), que consiste em não repetir codigo quando o mesmo poderia ser reutilizado.

Isso quer dizer que, por vezes, é preferível repetir trechos para manter a legibilidade e manutenabilidade do código.

## Stack e Instalação

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

## Terminologias

### Propriedade

Propriedades são o que definem o estilo do elemento capturado identificado pelo seletor. É um composição de chave-valor.

Ex.:
```sass
/* seletor */ {
    background: #f1f1f1;
    color: #333;
}
```

### Seletor

É o que determina a quais elementos da árvore DOM a regra será aplicada. Seletores podem capturar elementos pelo próprio nome do elemento (ex.: div, img, etc), por classe, id ou algum de seus atributos.

Ex.:
```sass
div {
    /* propriedades */
}

.classe {
    /* propriedades */
}

#identificador {
    /* propriedades */
}

[atributo=valor]  {
    /* propriedades */
}
```

### Regra

É o conjunto das propriedades que serão aplicadas a determinado seletor (ou conjunto de seletores).

Ex.:
```sass
div,
.seletor {
    background: #f1f1f1;
    color: #333;
}
```

## Sintaxe e formatação

- Identação de 4 espaços
- Tentar manter linhas curtas, algo em torno de 80 caracteres no máximo
- Na declaração de uma propriedade sempre separar o valor do nome com um espaço
- Evitar linhas em branco nas regras

```sass
// BOM
.classe {
    display: block;
    height: 100px;
    margin: 0;    
}

// RUIM
.classe{  
  display: block; height: 100px;

  margin:0;
}
```

### Strings

Strings devem sempre ser envolvidas em aspas simples. Exceto se forem valores específicos de CSS, como `initial` ou `sans-serif`, ou cores (`red`, `white`, etc).

O mesmo se aplica às URLs: `background-image: url('/images/kittens.jpg');`.

Motivos:
- nomes de cores são tratados como cores quando não possuem aspas, o que pode levar a conflitos
- a maior parte dos highlighters de sintaxe têm problemas com strings sem aspas
- ajuda em geral à leitura

### Números

#### Zeros

Sempre utilizar mostrar o 0 (zero) à esquerda da virgula e nunca mostrar zeros à direita. Ex.:

```sass
// BOM
.classe {
    opacity: 0.5;
    font-size: 1.1em;
}

// RUIM
.classe {
    opacity: .5;
    font-size: 1.10em;
}
```

Quando lidar com medidas um valor zero nunca deve utilizar uma unidade. Ex.:

```sass
// BOM
.classe {
    font-size: 0;
}

// RUIM
.classe {
    font-size: 0em;
}
```

#### Cálculos

Sempre envolver cálculos com parênteses. Ex.:

```sass
// BOM
.classe {
    width: (100% / 3);
}

// RUIM
.classe {
    width: 100% / 3;
}
```

### Cores

Utilizar sempre o formato hexadecimal com 6 posições.

Caso seja necessário aplicar opacidade utilizar a função `rgba` do Sass, que aceita cores em formato hexadecimal. Ex.:

```sass
.classe {
    background-color: rgba(#000000, 0.5);
}
```

### Lists

É a estrutura de dados equivalente de arrays. Podem ser armazenados valores de todos os tipos, incluindo outras listas.

- Escrever sempre em várias linhas;
- Separar por vírgulas;
- Sempre envolver em parêntesis;
- Manter vírgula ao final do último item.

```sass
// BOM
$fontes: (
    'Arial',
    'Times New Roman',
    sans-serif,
);
```
- Utilizar a API disponível quando precisar acrescentar (programaticamente) um novo item à lista. Ex.:

```sass
$fontes: append($fontes, 'Helvetica');
```

### Maps

É uma estrutura de dados que mapeia chaves (de qualquer tipo) para valores de qualquer tipo.

Ao escrever um map, respeitar:

- Espaço após os dois pontos;
- Se a chave for uma string envolver com aspas;
- Chave e valor devem estar na mesma linha;
- Utilizar vírgula como separador;
- Manter vírgula ao final do último item.

```sass
// BOM
$breakpoints: (
    'small': 320px,
    'medium': 800px,
    'large': 1100px,
);
```

### Declaração

- Seletores relacionados devem ser escritos na mesma linha;
- Separar com espaço a chave de abertura do último seletor;
- Cada propriedade em sua linha;
- Espaço após os dois pontos;
- Ponto e vírgula no final da declaração da propriedade;
- Chave de fechamento em sua própria linha;
- Separar regras por uma linha em branco.

```sass
// BOM
.barra, .barra-extendida,
.linha {
    opacity: 0.5;
    font-size: 1.1em;
}

.classe2 {
    display: inline-block;
}

// RUIM
.barra,
.barra-extendida, .linha {
    opacity: 0.5; font-size: 1.1em; }
.classe2 {
    display: inline-block;}
```

Além destas regras de declaração (relacionadas à CSS somente), há algumas muito importantes na escrita de Sass:

- Ordem de escrita da composição da regra deve ser a seguinte:
  - Variáveis locais;
  - Propriedades;
  - Mixins sem `@content`;
  - Mixins com `@content`;  
  - Seletores aninhados;
- Variáveis locais, mixins (com `@content`) e seletores aninhados devem ser separados dos outros elementos por uma linha em branco.

Ex.:

```sass
.barra, .barra-extendida,
.linha {
    $font-size: 2em;

    display: block;
    overflow: hidden;
    margin: 0 auto;

    @include font-size($font-size);

    @include breakpoint('small') {
        display: none;
    }

    &:hover {
        color: red;

        @include font-size($font-size);
    }
}
```

### Ordenação

Esta é uma das questões mais fervorosamente discutidas quanto a eficácia e sentido. Nós, no entanto, vamos definir de forma muito clara qual o modo desejado.

As propriedades de uma regra devem ser ordenadas por tipo, primeiro os atributos que influenciam o posicionamento e comportamente de posição do elemento, sua exibição, o tamanho e então outras propriedades. Portanto seria esta a ordem: `position, display, tamanho, cores, tipo de letra e outros`.

### Aninhamento de seletores

O aninhamento de seletores é uma feature incrível do Sass mas é extremamente mal interpretada e utilizada. Seu objetivo é facilitar a escrita, mas quanto mais níveis descemos no aninhamento mais difícil será a manutenção deste trecho.

O desenvolvedor fará o processamento do CSS final mentalmente, com base no aninhamento, antes de decidir onde é o local adequado para inserir uma regra nova, por exemplo. Quanto maior o nível, maior será a complexidade para o desenvolvedor processar mentalmente qual será o CSS gerado. Sem nem citar a dificuldade acrescentada ao utilizar referências ao seletor atual (`&`).

Portanto, uma quantidade aceitável de níveis é `4`. Se você estiver ultrapassando o quarto nível seria interessante repensar a estrutura do seu código.

## Nomeação

**Variáveis, Funções e Mixins** devem ser nomeadas obedecendo a seguinte regra: sempre **letras minúsculas** e as **palavras separadas por hífen**.

Ex.:
```sass
$background-color: #ff0000;

@mixin aspect-ratio($width, $height) {
}

@function opposite-direction($direction) {
}
```

Infelizmente no Sass não temos como definir uma **constante** propriamente dita, para tanto é interessante adotar um padrão de nomeação que as identifique facilmente e ninguém que vá realizar alguma alteração utilize-a como variável.
Portanto a nomeação de **constantes** devem seguir a seguinte regra: sempre **letras maiúsculas** e as **palavras separadas por underline**.

Ex.:
```sass
$FONT_SIZE_BASE: 1.2em;
```

## Comentários

Basicamente qualquer coisa que não seja de óbvio entendimento à primeira vista deve ser comentado.

Para comentar uma regra inteira utilizar comentário multilinhas:

```sass
/**
 * This mixin keeps the box aspect ratio on every screen resolution, totally responsive.
 * This needs another box inside it with the class "content" wich, obviously,
 * will receive all the content that is desired to be displayed
 */
@mixin aspect-ratio($width, $height) {
};
```

Para comentários sobre um cálculo, uma variável, ou o porquê de uma propriedade em específico deve-se utilizar o comentário *in-line*:

```sass
//algum comentário relevante sobre o cálculo abaixo
$padding-top: ($height / $width) * 100%;
```

## Responsividade

### Nomeação de breakpoints

Os nomes dos breakpoints devem estar relacionados a um grupo de tamanhos de tela ou à uma proporção específica que atingirão, e não específicamente a um tipo de dispositivo ou outro nome qualquer.

Ex.:
```sass
// BOM
$breakpoint-big: min-width 1100px;
$breakpoint-medium: min-width 800px;
$breakpoint-small: min-width 520px;

// RUIM
$breakpoint-desktop: min-width 1100px;
$breakpoint-tablet: min-width 800px;
$breakpoint-smartphone: min-width 520px;

// RUIM
$breakpoint-alpha: min-width 1100px;
$breakpoint-omega: min-width 800px;
$breakpoint-beta: min-width 520px;
```

### Uso das media queries

As *media queries* devem ser escritas sempre dentro do seletor a qual elas pertencem/alteram, pois desta forma fica mais fácil componentizar a aplicação.

Ex.:

```sass
// BOM
.foo {
  color: red;

  @include breakpoint($breakpoint-medium) {
    color: blue;
  }
}

.bar {
  height: 100px;

  @include breakpoint($breakpoint-medium) {
    height: 50px
  }
}

// RUIM
.foo {
  color: red;
}
.bar {
  height: 100px;
}

@include breakpoint($breakpoint-medium) {
  .foo {
    color: blue;
  }
  .bar {
    height: 50px
  }
}
```

### Variáveis

A utilização de variáveis é, sem dúvidas, um dos maiores avanços trazidos pelo Sass, porém seu uso deve ser consciente, variáveis não devem ser utilizadas só porque lhe é permitido.
Segundo o Sass Guidelines (vide [referências](#referencias)), variáveis devem ser utilizadas quando atendem a uma das seguintes regras:
- o seu valor é repetido pelo menos duas vezes;
- o seu valor provavelemnte irá ser atualizado, pelo menos uma vez;
- todas as ocorrências do seu valor, estão diretamente ligadas à variável (não ser uma coicidência).

## Referências

Este guia de estilos foi baseado nos seguintes conteúdos:
- [Airbnb CSS / Sass Styleguide](https://github.com/airbnb/css)
- [Sass Guidelines](http://sass-guidelin.es/)
- [Sass Style Guide](https://css-tricks.com/sass-style-guide/)
