# [Start Bootstrap - Stylish Portfolio](https://startbootstrap.com/template-overviews/stylish-portfolio/)

[Stylish Portfolio](http://startbootstrap.com/template-overviews/stylish-portfolio/) is a responsive, one page portfolio theme for [Bootstrap](http://getbootstrap.com/) created by [Start Bootstrap](http://startbootstrap.com/). The theme features multiple content sections with an off canvas navigation menu.

## Preview

[![Stylish Portfolio Preview](https://startbootstrap.com/assets/img/templates/stylish-portfolio.jpg)](https://blackrockdigital.github.io/startbootstrap-stylish-portfolio/)

**[View Live Preview](https://blackrockdigital.github.io/startbootstrap-stylish-portfolio/)**

## Status

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/BlackrockDigital/startbootstrap-stylish-portfolio/master/LICENSE)
[![npm version](https://img.shields.io/npm/v/startbootstrap-stylish-portfolio.svg)](https://www.npmjs.com/package/startbootstrap-stylish-portfolio)
[![Build Status](https://travis-ci.org/BlackrockDigital/startbootstrap-stylish-portfolio.svg?branch=master)](https://travis-ci.org/BlackrockDigital/startbootstrap-stylish-portfolio)
[![dependencies Status](https://david-dm.org/BlackrockDigital/startbootstrap-stylish-portfolio/status.svg)](https://david-dm.org/BlackrockDigital/startbootstrap-stylish-portfolio)
[![devDependencies Status](https://david-dm.org/BlackrockDigital/startbootstrap-stylish-portfolio/dev-status.svg)](https://david-dm.org/BlackrockDigital/startbootstrap-stylish-portfolio?type=dev)

## Download and Installation

To begin using this template, choose one of the following options to get started:
* [Download the latest release on Start Bootstrap](https://startbootstrap.com/template-overviews/stylish-portfolio/)
* Install via npm: `npm i startbootstrap-stylish-portfolio`
* Clone the repo: `git clone https://github.com/BlackrockDigital/startbootstrap-stylish-portfolio.git`
* [Fork, Clone, or Download on GitHub](https://github.com/BlackrockDigital/startbootstrap-stylish-portfolio)

## Usage

### Basic Usage

After downloading, simply edit the HTML and CSS files included with the template in your favorite text editor to make changes. These are the only files you need to worry about, you can ignore everything else! To preview the changes you make to the code, you can open the `index.html` file in your web browser.

### Advanced Usage

After installation, run `npm install` and then run `gulp dev` which will open up a preview of the template in your default browser, watch for changes to core template files, and live reload the browser when changes are saved. You can view the `gulpfile.js` to see which tasks are included with the dev environment.

#### Gulp Tasks

- `gulp` the default task that builds everything
- `gulp dev` browserSync opens the project in your default browser and live reloads when changes are made
- `gulp css` compiles SCSS files into CSS and minifies the compiled CSS
- `gulp js` minifies the themes JS file
- `gulp vendor` copies dependencies from node_modules to the vendor directory

You must have npm and Gulp installed globally on your machine in order to use these features.

## Troubleshooting and Help

Start Bootstrap has a public Slack channel which is a great place to ask questions about this template and all things related to Start Bootstrap.

**[Click here to join the Slack channel!](https://startbootstrap-slack.herokuapp.com/)**

## Bugs and Issues

Have a bug or an issue with this template? [Open a new issue](https://github.com/BlackrockDigital/startbootstrap-stylish-portfolio/issues) here on GitHub or leave a comment on the [template overview page at Start Bootstrap](http://startbootstrap.com/template-overviews/stylish-portfolio/).

## About

Start Bootstrap is an open source library of free Bootstrap templates and themes. All of the free templates and themes on Start Bootstrap are released under the MIT license, which means you can use them for any purpose, even for commercial projects.

* https://startbootstrap.com
* https://twitter.com/SBootstrap

Start Bootstrap was created by and is maintained by **[David Miller](http://davidmiller.io/)**, Owner of [Blackrock Digital](http://blackrockdigital.io/).

* http://davidmiller.io
* https://twitter.com/davidmillerskt
* https://github.com/davidtmiller

Start Bootstrap is based on the [Bootstrap](http://getbootstrap.com/) framework created by [Mark Otto](https://twitter.com/mdo) and [Jacob Thorton](https://twitter.com/fat).

## Copyright and License

Copyright 2013-2018 Blackrock Digital LLC. Code released under the [MIT](https://github.com/BlackrockDigital/startbootstrap-stylish-portfolio/blob/gh-pages/LICENSE) license.


1. Obtener una clave API para hacer solicitudes
Antes de que pueda realizar una solicitud con la API de Flickr, necesitará una clave de API, de la que puede leer más aquí . Cuando se registra una aplicación, se le da una clave y un secreto.

2. Determine el recurso y el punto final que necesita
De la lista de métodos API de Flickr , el punto final flickr.galleries.getPhotos , que figura en la lista del recurso de galerías, es el que obtendrá fotos de una galería.

Flickr getPhotos endpoint

Uno de los argumentos que necesitamos para el getPhotospunto final es el gallery_id. gallery_idSin embargo, antes de que podamos obtener el , tenemos que usar otro punto final para recuperarlo. De manera poco intuitiva, nogallery_id es el ID que aparece en la URL de la galería.

En su lugar, usamos el flickr.urls.lookupGallerypunto final listado en la sección de recursos de URL para obtener el gallery_idURL de una galería:

Punto final de búsqueda de Flickr.

El gallery_idde color en la naturaleza es 66911286-72157647277042064. Ahora tenemos los argumentos que necesitamos para el flickr.galleries.getPhotospunto final.

Mensaje patrocinado:
Más de 40,000 desarrolladores de API utilizan SwaggerHub para diseñar y documentar API con Swagger (OpenAPI). Aprenda cómo SwaggerHub puede ayudar a mejorar el flujo de trabajo de documentación de la API de su equipo. Comience de forma gratuita .
3. Construye la solicitud
Podemos hacer la solicitud para obtener la lista de fotos para este específico gallery_id.

Flickr proporciona un explorador de API para simplificar las llamadas a los puntos finales. Si vamos al API Explorer para el galleries.getPhotospunto final , podemos conectar gallery_idy ver la respuesta, así como obtener la sintaxis de la URL para el punto final.

Usando el API Explorer de Flickr para obtener la sintaxis de la solicitud

Inserte gallery_id, seleccione JSON para la salida, seleccione No firmar llamada (solo estamos probando aquí, por lo que no necesitamos seguridad adicional), y luego haga clic en Método de llamada .

Aquí está el resultado:

Respuesta de la galería de Flickr.

La URL debajo de la respuesta muestra la sintaxis correcta para usar este método:

https://api.flickr.com/services/rest/?method=flickr.galleries.getPhotos&api_key=APIKEY&gallery_id=66911286-72157647277042064&format=json&nojsoncallback=1
He eliminado mi clave de API de los ejemplos de código para evitar posibles abusos en mis claves de API. Si lo estás siguiendo, intercambia tu propia clave API aquí. (O puedes prestarme mis llaves aquí ).

Si envía la solicitud directamente en su navegador usando la URL dada, puede ver la misma respuesta pero en el navegador en lugar de en el API Explorer:

Respuesta de Flickr en el navegador.

Estoy usando la extensión de formato JSON para Chrome para hacer que la respuesta JSON sea más legible. Sin este complemento, la respuesta JSON se comprime.

4. Analizar la respuesta.
Toda la información necesaria se incluye en esta respuesta para mostrar fotos en nuestro sitio, pero no es del todo intuitivo cómo construimos las URL de origen de la imagen a partir de la respuesta.

En otras palabras, la información que necesita un usuario para lograr un objetivo no está explícita en la documentación de referencia de la API . Los documentos de referencia solo explican lo que se devuelve en la respuesta, no cómo usar la respuesta.

La página de URL de origen de fotos en la documentación lo explica:

Puede construir la URL de origen para una foto una vez que sepa su ID, ID de servidor, ID de comunidad y secreto, tal como lo devuelven muchos métodos API. La URL toma el siguiente formato:
https: // farm {farm-id} .staticflickr.com / {server-id} / {id} _ {secret} .jpg
	o
https: // farm {farm-id} .staticflickr.com / {server-id} / {id} _ {secret} _ [mstzb] .jpg
	o
https: // farm {farm-id} .staticflickr.com / {server-id} / {id} _ {o-secret} _o. (jpg | gif | png)
Aquí es cómo se ve un elemento en la respuesta JSON:

{
  "photos": {
    "page": 1,
    "pages": 1,
    "perpage": 100,
    "total": 13,
    "photo": [
      {
      "id": "8432423659",
      "owner": "37107167@N07",
      "secret": "dd1b834ec5",
      "server": "8187",
      "farm": 9,
      "title": "Color",
      "ispublic": 1,
      "isfriend": 0,
      "isfamily": 0,
      "is_primary": 1,
      "has_comment": 0
      },
      ...
    ]
    }
}
Accedes a estos campos a través de la notación de puntos. Es una buena idea registrar todo el objeto en la consola para explorarlo mejor.

5. Saque la información que necesita
El siguiente código utiliza jQuery para recorrer cada una de las respuestas e inserta los componentes necesarios en una etiqueta de imagen para mostrar cada foto.

<html>
<style>
img {max-height:125px; margin:3px; border:1px solid #dedede;}
</style>
<body>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>


<script>

var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.flickr.com/services/rest/?method=flickr.galleries.getPhotos&api_key=APIKEY&gallery_id=66911286-72157647277042064&format=json&nojsoncallback=1",
  "method": "GET",
  "headers": {}
}

$.ajax(settings).done(function (data) {
  console.log(data);



$("#galleryTitle").append(data.photos.photo[0].title + " Gallery");
    	$.each( data.photos.photo, function( i, gp ) {

var farmId = gp.farm;
var serverId = gp.server;
var id = gp.id;
var secret = gp.secret;

console.log(farmId + ", " + serverId + ", " + id + ", " + secret);

//  https://farm{farm-id}.staticflickr.com/{server-id}/{id}_{secret}.jpg

$("#flickr").append('<img src="https://farm' + farmId + '.staticflickr.com/' + serverId + '/' + id + '_' + secret + '.jpg"/>');

});
});

</script>


<h2><div id="galleryTitle"></div></h2>
<div style="clear:both;"/>
<div id="flickr"/>


</body>
</html>
Esto es lo que hace el código:

En este código, el método ajax de jQuery obtiene la carga útil de JSON. La carga útil se asigna al dataargumento y luego se registra en la consola.
El objeto de datos contiene un objeto llamado photos, que contiene una matriz llamada photo. El titlecampo es una propiedad en un objeto en la photomatriz. El titleque se accede a través de esta notación de puntos: data.photos.photo[0].title.
Para obtener cada elemento en el objeto, jQuery cada método recorre las propiedades de un objeto. Tenga en cuenta que el eachmétodo jQuery se usa comúnmente para recorrer los resultados para obtener valores. Para el primer argumento ( data.photos.photo), identifica el objeto al que desea acceder. Para los function( i, gp )argumentos, usted lista un índice y un valor. Puedes usar cualquier nombre que quieras aquí. gpse convierte en una variable que se refiere al data.photos.photoobjeto por el que estás atravesando. iSe refiere al punto de partida a través del objeto. (No necesita referirse imás allá de la instancia aquí a menos que desee comenzar o finalizar el bucle en un punto determinado).
Para acceder a las propiedades en el objeto JSON, usamos en gp.farmlugar de data.photos.photo[0].farm, porque gpes una referencia de objeto a data.photos.photo[i].
Después de que la eachfunción se itera a través de la respuesta, agregué algunas variables para facilitar el trabajo con estos componentes (usar en serverIdlugar de gp.server, etc.). Y se console.logverifica un mensaje para garantizar que obtengamos valores para cada uno de los elementos que necesitamos.
Este comentario muestra dónde necesitamos conectar cada una de las variables:
//  https://farm{farm-id}.staticflickr.com/{server-id}/{id}_{secret}.jpg
La última línea muestra cómo insertar esas variables en el HTML:

$("#flickr").append('<img src="https://farm' + farmId + '.staticflickr.com/' + serverId + '/' + id + '_' + secret + '.jpg"/>');
Un patrón común en la programación es recorrer una respuesta. Este ejemplo de código utilizó el eachmétodo de jQuery para examinar todos los elementos de la respuesta y hacer algo con cada elemento. A veces incorporas lógica que recorre los elementos y busca ciertas condiciones presentes para decidir si realizar alguna acción. Preste atención a los métodos de bucle, ya que son escenarios comunes en la programación.



API de Flickr, solicitud JSON utilizando jquery Infinitescroll, ¿cómo saber cuándo se carga la última página?

function ajaxProcess() {

var searchTerm = $("#term").val(); // get the user-entered search term
var URL2='http://api.flickr.com/services/rest/?method=flickr.people.getPublicPhotos&user_id=57333193@N00&api_key=f290d9d56bd82fde0c87d7fd6a0e6c33&'; 
var tags="&tags="+ searchTerm;
var tagmode="&tagmode=any";
var jsonFormat = "&format=json";                    
var ajaxURL= URL2+"per_page="+perpage+"&page="+currentPage+tags+tagmode+jsonFormat;
                //var ajaxURL= URL+"?"+tags+tagmode+jsonFormat;

             $.ajax({
              url:ajaxURL,
              dataType:"jsonp",
              jsonp:"jsoncallback",
              success: function(data) {
                   // $("#photos").empty(); 
                    if(data.stat!="fail") {
                         console.log(data); 
                        //$("#photos").empty();
                        // $("figure").empty();
    $.each(data.photos.photo,   function(i,photo) {
  var photoHTML="";
 photoHTML+=" <a href='";                                   photoHTML+="http://farm"+photo.farm+".static.flickr.com/"+photo.server+"/"+photo.id+"_"+photo.secret+"_b.jpg'";
photoHTML+=">";  
photoHTML+= "<figure class=\"effeckt-caption\" data-effeckt-type=\"quarter-zoom\"> <img class=\"img-rounded\" src='";                             photoHTML+="http://farm"+photo.farm+".static.flickr.com/"+photo.server+"/"+photo.id+"_"+photo.secret+"_q.jpg'"; 
photoHTML+=" title='"+photo.title+"'" ;
photoHTML+=" >" ;
photoHTML+="<figcaption class=\"caption\"><div class=\"effeckt-figcaption-wrap\"" ;                            photoHTML+=">'"+photo.title+"'</div></figcaption></figure></a>";
                              $("#gallery").append(photoHTML).fadeIn(400);                                                        
});

}else {
$("#gallery").empty();
console.log("Error code "+data.stat);
photoHTML="Error !! Error !! "+data.stat;


}

}
});

}
 var perpage=30;
 var currentPage=1;

$('#gallery').infinitescroll({
    navSelector     : "a#next",
    nextSelector    : "a#next",
    itemSelector    : "#gallery a",
    debug           : true,
    dataType        : "json",
    speed: 'fast',
    animate: true,
    loading: {
            finishedMsg: "All Images Loaded",
            img: "res/icons/load.gif",
            msgText: "<em>Adding More Images...</em>"
},
    prefill         : true,
    behavior        : "twitter",
    errorCallback: function() {
  // fade out the error message after 2.5 seconds
  $('#infscr-loading').animate({opacity: 0.8},2500).fadeOut('normal');
   $('a#next').addClass('disabled');
}

}, function(json, opts) {
    ajaxProcess();
    currentPage++;

});
   $( "a#next" ).on( "click", function() {
            ajaxProcess();
    currentPage++;
    });