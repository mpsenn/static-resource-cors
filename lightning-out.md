# Lightning Out QA

Trying out the bug against a steam environment.

This page attempts to load JS in a static resource through Lightning Out.



<script src="https://vfmetadata.my.stmfa.stm.salesforce.com/lightning/lightning.out.js"></script>
  
    <div id="lightning" />

    <script>

    var lightningEndPointURI = 'https://vfmetadata.lightning.stmfa.stm.force.com';

    function doIt(authToken) {

        $Lightning.use("c:BananaDepApp", function() {
          $Lightning.createComponent("c:Banana",
              {  },
              "lightning",
              function(cmp) {
                console.log("Banana was created");
                // do some stuff
              }
          );
        }, lightningEndPointURI, authToken);
    }
    </script>