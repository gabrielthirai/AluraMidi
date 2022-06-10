<h1>Anotações</h1>

Da mesma forma que o css não é feito inline no html, o JS também não é, temos que criar um arquivo externo. Para importar o arquivo usamos o:
```
    <script src="main.js"></script>
```

Caso queira adicionar uma caixa de mensagem do navegador, uma caixa de alerta, temos que usar:
```
    alert('');
```
(obs: o ponto e virgula no js é opicional, porém para boas práticas é sempre bom a utilização).


Mas afinal, como faço para atacar uma classe ou tag no JS? Na verdade é mais simples que parece.

```
    querySelector('');
```
Nesse caso estamos falando pro js consultar/procurar o seletor, que será colocar dentro das aspas simples (' '). Podemos colocar uma tag de html, uma classe de css, ou um id, é só utilizar como se estivesse no css, para a tag é só colocar a tag (exemplo: button), para classes você utiliza o . (exemplo: .tecla_pom), e no id se usa o # (exemplo: #tecla). Porém há um problema nisso, se o querySelector não tiver um escopo com ele, o js não vai identificar aonde o elemento está, dessa forma temos que utilizar uma propriedade do js, que é o document, o document vai mostrar aonde vai ser buscado o seletor e o elemento.

```
    document.querySelector(' ');
```
OBS: tome cuidado com as letras maiusculas e minusculas no js, ele é case-sensitive.