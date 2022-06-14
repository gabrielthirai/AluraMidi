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


Agora para adicionar um comportamento no js não é tão diferente do que ja vimos, nesse caso vamos usar o mesmo escopo e seletor, porém vamos adicionar um ponto depois de tudo isso, que vai acessar todas as funcionalidades que o elemento em questão pode trazer para o js, então vejamos:
```
    document.querySelector('#som_tecla_pom').play();
```
Nesse caso a musica que está vinculada ao id vai dar play. Os parenteses está lá pois o play é uma função.
Porém se executarmos assim, vai dar erro, o navegador retorna que o document.querySelector é null. Isso se da devido ao local da tag script. Então para resolver devemos nos perguntar se o que vamos fazer em JS depende dos elemento do html executados, ou não. Caso necessite dos elemento executados, ou seja, que o body seja executado para que o js funcione, se coloca a tag script dentro do body ao final dele. Caso não dependa do que está sendo executado no body, no caso pode ser algo tipo o reset.css, se coloca a tag script dentro do head.


Só que nesse caso o som vai dar play logo que iniciarmos a página, e não é isso que queremos, queremos que assim que o usuario clicar no botão do som, o som inicie, então devemos fazer uma função.
```
    function tocaSomPom (){
        document.querySelector('#som_tecla_pom').play();
    }
```

Porém, se clicarmos no botão em questão, ele não vai reproduzir o som ainda, porque não definimos o click dele no js. Se voltarmos no html e colocarmos o "onclick" com a funcão da tecla pom, ele vai reproduzir, porém sabemos que fazer isso manualmente, linha por linha não é a melhor opção, então temos que adicionar esse onclick no js, e como fazemos isso? É bem simples, adicionamos o "." na frente do document.querySelector da tecla pom para acessarmos os atributos dela, e adicionamos o onclick depois do ponto, assim: 
```
    document.querySelector('.tecla_pom').onclick = tocaSomPom;
```
Nesse caso ja chamamos a função do tocaSomPom que definimos anteriormente, e chamamos pela atribuição da função no atributo de onclick. Porém se atente a uma coisa, a função foi colocada sem os parenteses, porque se colocarmos o parenteses a função vai ser chamada junto com a outra função do tocaSomPom, e não queremos isso.


Agora como passamos um som para todos os botões do site? Se a gente for fazer uma função pra cada tecla, para cada botão, vai ficar gigante o código, e não é isso que queremos. Temos que usar algo para puxar todos os seletores, então:
```
    document.querySelectorAll('');
```
Vai buscar todos os seletores que informarmos entre os parenteses. Ele vai formar uma lista, se podemos dizer assim.

