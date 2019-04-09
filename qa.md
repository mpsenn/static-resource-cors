# QA in Steam

Trying out the bug against a steam environment.

This page attempts to load JS through an XHR to a static resource. However, it's blocked due to the presence of the [Access-Control-Allow-Credentials](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Credentials) header in the response.

Code, also include in a script tag in the page:

    var xmlhttp = new XMLHttpRequest();
    xmlhttp.open("GET", 'https://vfmetadata--c.stmfa.stm.visualforce.com/resource/1554832772000/banana/myjs.js');
    xmlhttp.withCredentials = true;
    xmlhttp.onreadystatechange = function()
    {
        if ((xmlhttp.status == 200) && (xmlhttp.readyState == 4))
        {
            eval(xmlhttp.responseText);
        }
    };
    xmlhttp.send();


<script>
    var xmlhttp = new XMLHttpRequest();
    xmlhttp.open("GET", 'https://vfmetadata--c.stmfa.stm.visualforce.com/resource/1554832772000/banana/myjs.js');
    xmlhttp.withCredentials = true;
    xmlhttp.onreadystatechange = function()
    {
        if ((xmlhttp.status == 200) && (xmlhttp.readyState == 4))
        {
            eval(xmlhttp.responseText);
        }
    };
    xmlhttp.send();
</script>
