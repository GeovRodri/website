---
title: "Dica CSS: Limitar tamanho de um texto"
date: 2020-06-09 00:00:00 +03:00
tags: [css, ui, ux]
description: Dica de CSS sobre como limitar um texto colocando "..."
---

E aí pessoal, hoje vou explicar algo bem simples mas muito importante para a criação de páginas.
Sabe quando você tem um texto um texto muito grande mas só quer mostrar uma parte? Vou explicar
como fazer isso sem a necessidade de JavaScript. Então vamos lá!!

Vamos considerar o seguinte cenário:
<div style="box-shadow: 0 0 3px; padding: 10px;">
  <h2 style="margin: 0 0 5px;">Titulo</h2>
  <div class="description">
    Lorem ipsum dolor sit amet,   consectetur adipiscing elit. Aliquam consequat feugiat nunc nec aliquet. Suspendisse nisi odio, posuere a dapibus quis, tincidunt eu lorem. Donec ut ornare nisl, a ornare dolor. Integer vestibulum, dui eu lacinia sodales, neque ante dapibus magna, ac ornare lorem lectus tempor nunc. Duis elementum, tortor nec tincidunt suscipit, ante lacus rutrum tellus, id fermentum nulla lectus ac risus. Nulla aliquet, ligula eget finibus imperdiet, augue metus consectetur justo, ac tempus nunc lectus vitae eros. Aliquam  iaculis vestibulum ultrices.
    </div>
</div>

Para limitar o tamanho do texto (Apenas uma linha) basta colocar o seguinte código na sua classe CSS:

``` css
max-width: 500px; // Limite máximo do texto
white-space: nowrap; // Removendo quebra de linha
overflow: hidden; // Removendo a barra de rolagem
text-overflow: ellipsis; // Adicionando "..." ao final do texto
```

O resultado será esse (<a href="https://codepen.io/geovrodri/pen/NWxGYwo" target="_blank">Codepen</a>):
<div style="box-shadow: 0 0 3px; padding: 10px;">
  <h2 style="margin: 0 0 5px;">Titulo</h2>
  <div style="max-width: 100%; white-space: nowrap; overflow: hidden; text-overflow: ellipsis;">
    Lorem ipsum dolor sit amet,   consectetur adipiscing elit. Aliquam consequat feugiat nunc nec aliquet. Suspendisse nisi odio, posuere a dapibus quis, tincidunt eu lorem. Donec ut ornare nisl, a ornare dolor. Integer vestibulum, dui eu lacinia sodales, neque ante dapibus magna, ac ornare lorem lectus tempor nunc. Duis elementum, tortor nec tincidunt suscipit, ante lacus rutrum tellus, id fermentum nulla lectus ac risus. Nulla aliquet, ligula eget finibus imperdiet, augue metus consectetur justo, ac tempus nunc lectus vitae eros. Aliquam  iaculis vestibulum ultrices.
    </div>
</div>


Para limitar o tamanho em várias linhas:

``` css
overflow: hidden; // Removendo barra de rolagem
text-overflow: ellipsis; // Adicionando "..." ao final
display: -webkit-box;
-webkit-line-clamp: 2; // Quantidade de linhas
-webkit-box-orient: vertical; 
```

O resultado será esse (<a href="https://codepen.io/geovrodri/pen/eYJpMyp" target="_blank">Codepen</a>):
<div style="box-shadow: 0 0 3px; padding: 10px;">
  <h2 style="margin: 0 0 5px;">Titulo</h2>
  <div style="max-width: 100%; overflow: hidden; text-overflow: ellipsis; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical;">
    Lorem ipsum dolor sit amet,   consectetur adipiscing elit. Aliquam consequat feugiat nunc nec aliquet. Suspendisse nisi odio, posuere a dapibus quis, tincidunt eu lorem. Donec ut ornare nisl, a ornare dolor. Integer vestibulum, dui eu lacinia sodales, neque ante dapibus magna, ac ornare lorem lectus tempor nunc. Duis elementum, tortor nec tincidunt suscipit, ante lacus rutrum tellus, id fermentum nulla lectus ac risus. Nulla aliquet, ligula eget finibus imperdiet, augue metus consectetur justo, ac tempus nunc lectus vitae eros. Aliquam  iaculis vestibulum ultrices.
    </div>
</div>
