# Acessibilidade Web em aplicações com uso intenso de JavaScript - Português

Este repositório contém informações sobre acessibilidade Web para autores de aplicações com uso intenso de JavaScript.

Não há grupo de discussão sobre o tema neste momento.

Interessados podem entrar em contato com emerson@alligo.com.br.


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

NÃO PODE usar estilo CSS `visibility: hidden;`. Isto oculta também para leitores de tela e mecanismos de busca.

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

PODE usar estilo CSS `display:none`.

PODE usar estilo CSS `visibility: hidden;`.

É RECOMENDÁVEL usar atributo `aria-hidden="true"` no elemento HTML para ocultá-lo e todos os seus descendentes de leitores de tela.
Este uso não afeta demais agentes de usuário (isto é, os que não usam leitores de tela).
Não há indícios de que isso afete intexação de mecanismos de busca.

<!-- ### 4. Acessibilidade de Ícones -->

### 5. Por onde começo?
Os seguintes materiais de alta qualidade, que foram revisados por grupos especializados no tema estão disponíveis em português:

- [JavaScript Acessível](http://acessibilidade.pt.webiwg.org/webaim/tecnicas/javascript/)
- [Criando Formulários Acessíveis](http://acessibilidade.pt.webiwg.org/webaim/tecnicas/formularios/)

Outros materiais devem ser publicados em breve.

## Autoria e Licença de uso

Os [autores](humans.txt) licenciam este projeto como [Domínio Público](LICENSE). 