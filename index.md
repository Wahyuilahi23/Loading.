<html lang = "en">
   <head>
      <meta charset = "utf-8">
      <title>Login</title>
      <link href = "https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
         rel = "stylesheet">
      <script src = "https://code.jquery.com/jquery-1.10.2.js"></script>
      <script src = "https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>

      <style>
         .ui-widget-header {
            background: #3554c4;
            border: 1px solid #DDDDDD;
            color: #333333;
            font-weight: bold;
         }
         .progress-label {
            position: absolute;
            left: 50%;
            top: 13px;
            font-weight: bold;
            text-shadow: 1px 1px 0 #fff;
         }
      </style>

      <script>
          function click_me() {
              var hidden = false;
              hidden = !hidden;
              if (hidden) {
                  document.getElementById('togglee').style.visibility = 'hidden';
              } else {
                  document.getElementById('togglee').style.visibility = 'visible';
              }

         $(function() {
            var progressbar = $( "#progressbar-5" );
            progressLabel = $( ".progress-label" );
            $( "#progressbar-5" ).progressbar({
               value: false,
               change: function() {
                  progressLabel.text(
                     progressbar.progressbar( "value" ) + "%" );
               },
               complete: function() {
                  progressLabel.text( "Loading Completed!" );
                  window.open("https://www.itk.ac.id","_self");
               }
            });
            function progress() {
               var val = progressbar.progressbar( "value" ) || 0;
               progressbar.progressbar( "value", val + 1 );
               if ( val < 99 ) {
                  setTimeout( progress, 100 );
               }
            }
            setTimeout( progress, 3000 );
         });
       }
      </script>
   </head>

   <body>
      <div id = "progressbar-5">
         <div class = "progress-label">
            Loading...
         </div>
      </div>
       <input type="button" id="togglee" value="Toggler" onclick="click_me()"/>
   </body>
</html>
