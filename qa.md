# QA in Steam

Trying out the bug against a steam environment.

This page attempts to load JS through an XHR to a static resource. However, it's blocked due to the presence of the [Access-Control-Allow-Credentials](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Credentials) header in the response.

Steps to reproduce:

1. Login to my [steam org](https://vfmetadata.my.stmfa.stm.salesforce.com/?un=vfmetadata@example.com&pw=123456)
2. Come back to this page.
3. Expect the JS to execute, and print "mikesenn" in the console. However, it does not execute. This error is shown in the console.

> Access to XMLHttpRequest at 'https://vfmetadata--c.stmfa.stm.visualforce.com/resource/1554832772000/banana/myjs.js' from origin 'https://mpsenn.github.io' has been blocked by CORS policy: The value of the 'Access-Control-Allow-Credentials' header in the response is 'false' which must be 'true' when the request's credentials mode is 'include'. The credentials mode of requests initiated by the XMLHttpRequest is controlled by the withCredentials attribute.

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

