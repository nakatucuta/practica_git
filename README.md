 git - la guía sencilla
    <link
      href="./git - la guía sencilla_files/css"
      rel="stylesheet"
      type="text/css"
    />
    <link
      rel="stylesheet"
      href="./git - la guía sencilla_files/normalize.min.css"
      type="text/css"
    />
    <link
      rel="stylesheet"
      href="./git - la guía sencilla_files/style.css"
      type="text/css"
    />
    <script
      id="twitter-wjs"
      src="./git - la guía sencilla_files/widgets.js.descarga"
    >
    <script
      type="text/javascript"
      async=""
      src="./git - la guía sencilla_files/ga.js.descarga"
    >
    
      var _gaq = _gaq || [];
      _gaq.push(["_setAccount", "UA-652147-13"]);
      _gaq.push(["_trackPageview"]);

      (function () {
        var ga = document.createElement("script");
        ga.type = "text/javascript";
        ga.async = true;
        ga.src =
          ("https:" == document.location.protocol
            ? "https://ssl"
            : "http://www") + ".google-analytics.com/ga.js";
        var s = document.getElementsByTagName("script")[0];
        s.parentNode.insertBefore(ga, s);
      })();
    
    <script
      type="text/javascript"
      async=""
      src="./git - la guía sencilla_files/embed.js.descarga"
    >
    <script
      async=""
      id="dsq_recs_scr"
      src="./git - la guía sencilla_files/recommendations.js.descarga"
    >
    <script
      charset="utf-8"
      src="./git - la guía sencilla_files/button.856debeac157d9669cf51e73a08fbc93.js.descarga"
    >
  
  
    
      # git - la guía sencilla
      una guía sencilla para comenzar con git. sin complicaciones ;)
      <iframe
        id="twitter-widget-0"
        scrolling="no"
        frameborder="0"
        allowtransparency="true"
        allowfullscreen="true"
        class="twitter-share-button twitter-share-button-rendered twitter-tweet-button"
        title="X Post Button"
        src="./git - la guía sencilla_files/tweet_button.2f70fb173b9000da126c79afe2098f02.en.html"
        style="position: static; visibility: visible; width: 72px; height: 28px"
        data-url="http://rogerdudler.github.com/git-guide"
      >
      
        !(function (d, s, id) {
          var js,
            fjs = d.getElementsByTagName(s)[0];
          if (!d.getElementById(id)) {
            js = d.createElement(s);
            js.id = id;
            js.src = "//platform.twitter.com/widgets.js";
            fjs.parentNode.insertBefore(js, fjs);
          }
        })(document, "script", "twitter-wjs");
      
      
        por
        [Roger Dudler](http://www.twitter.com/rogerdudler) (traducido
        por [@lfbarragan](http://www.twitter.com/lfbarragan) y
        [@adrimatellanes](https://twitter.com/adrimatellanes))
        créditos a [@tfnico](http://www.twitter.com/tfnico),
        [@fhd](http://www.twitter.com/fhd) y
        [Namics](http://www.namics.com/)
        disponible en
        [english](https://rogerdudler.github.io/git-guide/index.html)
      
      ![](./git - la guía sencilla_files/arrow.png)
    
    
    [](null)
    
      ## configuración
      
        [Descarga git para OSX](http://git-scm.com/download/mac)
      
      
        [Descarga git para Windows](http://msysgit.github.io/)
      
      
        <a
          href="http://git-scm.com/book/es/v1/Empezando-Instalando-Git#Instalando-en-Linux"
          >Descarga git para Linux</a
        >
      
    
    [](null)
    
      ## crea un repositorio nuevo
      
        Crea un directorio nuevo, ábrelo y ejecuta
        `git init`
        para crear un nuevo repositorio de git.
      
    
    [](null)
    
      ## hacer checkout a un repositorio
      
        Crea una copia local del repositorio ejecutando
        `git clone /path/to/repository`
        Si utilizas un servidor remoto, ejecuta
        `git clone username@host:/path/to/repository`
      
    
    [](null)
    
      ## flujo de trabajo
      
        Tu repositorio local esta compuesto por tres "árboles" administrados por
        git. El primero es tu `Directorio de trabajo` que contiene
        los archivos, el segundo es el `Index` que actua como una
        zona intermedia, y el último es el `HEAD` que apunta al
        último commit realizado.
      
      ![](./git - la guía sencilla_files/trees.png)
    
    [](null)
    
      ## add &amp; commit
      
        Puedes registrar cambios (añadirlos al Index) usando
        `git add &lt;filename&gt;`
        `git add .`
        Este es el primer paso en el flujo de trabajo básico. Para hacer commit
        a estos cambios usa
        `git commit -m "Commit message"`
        Ahora el archivo esta incluído en el HEAD, pero aún no en tu
        repositorio remoto.
      
    
    [](null)
    
      ## envío de cambios
      
        Tus cambios están ahora en el HEAD de tu copia local. Para enviar
        estos cambios a tu repositorio remoto ejecuta 
        `git push origin master`
        Reemplaza _master_ por la rama a la que quieres enviar tus cambios.
        
        Si no has clonado un repositorio ya existente y quieres conectar tu
        repositorio local a un repositorio remoto, usa
        `git remote add origin &lt;server&gt;`
        Ahora podrás subir tus cambios al repositorio remoto seleccionado.
      
    
    [](null)
    
      ## ramas
      
        Las ramas son utilizadas para desarrollar funcionalidades aisladas unas
        de otras. La rama _master_ es la rama "por defecto" cuando creas un
        repositorio. Crea nuevas ramas durante el desarrollo y fusiónalas a la
        rama principal cuando termines.
      
      ![](./git - la guía sencilla_files/branches.png)
      
        Crea una nueva rama llamada "feature_x" y cámbiate a ella usando
        `git checkout -b feature_x`
        vuelve a la rama principal
        `git checkout master`
        y borra la rama
        `git branch -d feature_x`
        Una rama nueva _no estará disponible para los demás_ a menos que
        subas (push) la rama a tu repositorio remoto
        `git push origin &lt;branch&gt;`
      
    
    [](null)
    
      ## actualiza &amp; fusiona
      
        Para actualizar tu repositorio local al commit más nuevo, ejecuta 
        `git pull`
        en tu directorio de trabajo para _bajar_ y _fusionar_ los
        cambios remotos.
        Para fusionar otra rama a tu rama activa (por ejemplo master),
        utiliza
        `git merge &lt;branch&gt;`
        en ambos casos git intentará fusionar automáticamente los cambios.
        Desafortunadamente, no siempre será posible y se podrán producir
        _conflictos_. Tú eres responsable de fusionar esos
        _conflictos_ manualmente al editar los archivos mostrados por git.
        Después de modificarlos, necesitas marcarlos como fusionados con
        `git add &lt;filename&gt;`
        Antes de fusionar los cambios, puedes revisarlos usando
        `git diff &lt;source_branch&gt; &lt;target_branch&gt;`
      
    
    [](null)
    
      ## etiquetas
      
        Se recomienda crear etiquetas para cada nueva versión publicada de un
        software. Este concepto no es nuevo, ya que estaba disponible en SVN.
        Puedes crear una nueva etiqueta llamada _1.0.0_ ejecutando
        `git tag 1.0.0 1b2e1d63ff`
        _1b2e1d63ff_ se refiere a los 10 caracteres del commit id al cual
        quieres referirte con tu etiqueta. Puedes obtener el commit id con
        
        `git log`
        también puedes usar menos caracteres que el commit id, pero debe ser un
        valor único.
      
    
    [](null)
    
      ## reemplaza cambios locales
      
        En caso de que hagas algo mal (lo que seguramente nunca suceda ;) puedes
        reemplazar cambios locales usando el comando
        `git checkout -- &lt;filename&gt;`
        Este comando reemplaza los cambios en tu directorio de trabajo con el
        último contenido de HEAD. Los cambios que ya han sido agregados al
        Index, así como también los nuevos archivos, se mantendrán sin cambio.
      
      
        Por otro lado, si quieres deshacer todos los cambios locales y commits,
        puedes traer la última versión del servidor y apuntar a tu copia local
        principal de esta forma
        `git fetch origin`
        `git reset --hard origin/master`
      
    
    [](null)
    
      ## datos útiles
      
        Interfaz gráfica por defecto
        `gitk`
        Colores especiales para la consola
        `git config color.ui true`
        Mostrar sólo una línea por cada commit en la traza
        `git config format.pretty oneline`
        Agregar archivos de forma interactiva
        `git add -i`
      
    
    [](null)
      
        /* * * CONFIGURATION VARIABLES: EDIT BEFORE PASTING INTO YOUR WEBPAGE * * */
        var disqus_shortname = "git-the-simple-guide"; // required: replace example with your forum shortname

        /* * * DON'T EDIT BELOW THIS LINE * * */
        (function () {
          var dsq = document.createElement("script");
          dsq.type = "text/javascript";
          dsq.async = true;
          dsq.src = "//" + disqus_shortname + ".disqus.com/embed.js";
          (
            document.getElementsByTagName("head")[0] ||
            document.getElementsByTagName("body")[0]
          ).appendChild(dsq);
        })();
      
      <noscript
        >Por favor habilita Javascript para ver los
        <a href="http://disqus.com/?ref_noscript"
          >comentarios - powered by Disqus.</a
        ></noscript
      >
    
    <a
      href="http://www.git-tower.com/?source=rd"
      onclick="recordOutboundLink(this, &#39;Outbound Links&#39;, &#39;git-tower.com&#39;);return false;"
      class="tower"
    >
    <a
      href="https://rogerdudler.github.io/git-guide/files/git_cheat_sheet.pdf"
      onclick="recordOutboundLink(this, &#39;Cheat Sheet&#39;, &#39;git-guide&#39;);return false;"
      class="cheatsheet"
    >

    <iframe
      scrolling="no"
      frameborder="0"
      allowtransparency="true"
      src="./git - la guía sencilla_files/widget_iframe.2f70fb173b9000da126c79afe2098f02.html"
      title="Twitter settings iframe"
      style="display: none"
    ></iframe
    ><iframe
      style="display: none"
      src="./git - la guía sencilla_files/saved_resource(12).html"
    ></iframe
    ><iframe
      style="display: none"
      src="./git - la guía sencilla_files/saved_resource(13).html"
    ></iframe
    ><iframe
      id="rufous-sandbox"
      scrolling="no"
      frameborder="0"
      allowtransparency="true"
      allowfullscreen="true"
      style="
        position: absolute;
        visibility: hidden;
        display: none;
        width: 0px;
        height: 0px;
        padding: 0px;
        border: none;
      "
      title="Twitter analytics iframe"
      src="./git - la guía sencilla_files/saved_resource(14).html"
    >
