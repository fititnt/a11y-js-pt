# Acessibilidade Web e JavaScript - Português

Este repositório contém informações exclusivamente em português sobre acessibilidade com foco para autores de HTML com uso intenso de JavaScript.
Se destinam a aplicações acessadas em navegadores e deveriam, sem garantias, também se aplicar para uso de HTML em aplicatívos híbridos.

Em um mundo ideal, todos deveriam testar seus softwares com leitores de tela.
Esse mundo não é uma realidade.
Continuar insistindo nisso depois de meia década não vai mudar.

Este projeto assume que o desenvolvedor,
mesmo sem ter experiência com leitores de tela ou conhecimentos _avançados_ de acessibilidade Web,
irá desenvolver uma aplicação mais acessível encarando essa realidade.
E para isto, reforça padrões de código que impactam muito além de usuários cegos e ferramentas de validação de erros durante o desenvolvimento.

Colabore ao fazer parte do [Grupo de Pesquisa e Desenvolvimento](#grupo-de-pesquisa-e-desenvolvimento).

---

* [Perguntas Frequentes](#perguntas-frequentes)
    * [1. Para ser considerado acessível, meu site precisa funcionar mesmo sem JavaScript habilitado?](#1-para-ser-considerado-acessível-meu-site-precisa-funcionar-mesmo-sem-javascript-habilitado)
    * [2. Como exibir conteúdo para leitores de tela e esconder dos demais?](#2-como-exibir-conteúdo-para-leitores-de-tela-e-esconder-dos-demais)
    * [3. Como ocultar conteúdo de leitores de tela?](#3-como-ocultar-conteúdo-de-leitores-de-tela)
    * [5. Por onde começo?](#5-por-onde-começo)
* [Grupo de Pesquisa e Desenvolvimento](#grupo-de-pesquisa-e-desenvolvimento)
* [Autoria e Licença de uso](#autoria-e-licença-de-uso)


## Perguntas Frequentes

As palavras-chave "DEVE", "NÃO DEVE", "REQUER", "DEVERIA", "NÃO  DEVERIA",
"PODERIA", "NÃO PODERIA", "RECOMENDÁVEL", "PODE", e "OPCIONAL" neste documento
devem ser interpretadas como descritas no RFC 2119 da IETF, traduzidas pela
WebIWG e disponibilizadas em http://rfc.pt.webiwg.org/rfc2119.

### 1. Para ser considerado acessível, meu site precisa funcionar mesmo sem JavaScript habilitado?

**Não**. Mais de [97% das pessoas tem JavaScript habilitado](http://webaim.org/projects/screenreadersurvey5/#javascript).

Porém é NÃO RECOMENDÁVEL usar CSS e JavaScript para criar visual e comportamentos de HTML que já os tem.

### 2. Como exibir conteúdo para leitores de tela e esconder dos demais?

NÃO PODE usar estilo CSS `display:none`. Isto oculta também para leitores de tela e mecanismos de busca.

NÃO PODE usar estilo CSS `visibility: hidden`. Isto oculta também para leitores de tela e mecanismos de busca.

Você PODE usaro seguinte CSS:

```css
.sr-only {
    position:absolute;
    left:-10000px;
    top:auto;
    width:1px;
    height:1px;
    overflow:hidden;
}
```

Veja [CSS em ação: conteúdo invisível apenas para usuários de leitores de tela](http://acessibilidade.pt.webiwg.org/webaim/tecnicas/css/conteudo-invisivel-apenas-para-leitores-de-tela/).

### 3. Como ocultar conteúdo de leitores de tela?

PODE usar estilo CSS `display:none`. Note que isto esconde também de outros agentes de usuário.

PODE usar estilo CSS `visibility: hidden;`. Note que isto esconde também de outros agentes de usuário.

É RECOMENDÁVEL usar atributo `aria-hidden="true"` no elemento HTML para ocultá-lo e todos os seus descendentes de leitores de tela.
Este uso não afeta demais agentes de usuário (isto é, os que não usam leitores de tela).
Não há indícios de que isso afete intexação de mecanismos de busca.

### 4. Acessibilidade de Ícones

O uso de ícones com fins não meramente estéticos DEVE levar em consideração usuários de teclado.
**Caso não sejam meramente visuais**, e possuírem funcionalidade, devem permitir navegação por <kbd>Tab</kbd>.
Usar bons padrões de código para elementos que possúem comportamento distinto uso de tags como `<a>` ou `<button>` evita reescrita mais tarde e maior chance de erro com uso de elementos menos semânticos como `<div>` ou `<span>` que requerem atributos ARIA.

Para acessibilidade com leitores de tela, consulte o manual do framework CSS que você usa para recomendações específicas.

No futuro este guia rápido deve ter mais informações a respeito.

### 5. Por onde começo?
Os seguintes materiais de alta qualidade, que foram revisados por grupos especializados no tema estão disponíveis em português:

- [JavaScript Acessível](http://acessibilidade.pt.webiwg.org/webaim/tecnicas/javascript/)
- [Criando Formulários Acessíveis](http://acessibilidade.pt.webiwg.org/webaim/tecnicas/formularios/)

Outros materiais devem ser publicados em breve.

## Grupo de Pesquisa e Desenvolvimento

Temos um pequeno grupo independente de pesquisa e desenvolvimento.
É focado nas implicações de acessibilidade no uso de aplicações HTML de uso intenso de JavaScript,
como com uso de [AngularJS](https://angular.io/) e [ReactJS](https://facebook.github.io/react/).
É coordenador por [Emerson Rocha](https://github.com/fititnt),
via [WebIWG](https://github.com/webiwg), em parceria com a [WebSchool.io](https://github.com/Webschool-io).

Entre em contato com emerson@alligo.com.br para saber mais a respeito.

## Autoria e Licença de uso

Os [autores](humans.txt) licenciam este projeto como [Domínio Público](LICENSE). 