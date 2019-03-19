# Reproducing W-5919835

In this repository, we're trying to reproduce W-5919835, titled "CORS headers are misconfigured." That PSIRT issue describes how a web host, outside of a Force.com Site, can load resources that are stored on an authenticated Force.com Site.

Steps to reproduce:
1. Verify that the image below is broken and does **not** load. You aren't authenticated with my site and shouldn't be able to load it.
2. Click [here](https://msenn-dev-ed.lightning.force.com/) and log into my authenticated Force.com Site. Username msenn-site@example.com, password applejack.
3. Come back to this page.
4. Verify that the image now **does** load. Attacking web pages would be able to load any static resource from an authenticated Force.com Site in this way, stealing customer metadata.

![Stolen image](https://msenn-dev-ed--bigmike1020.visualforce.com/resource/1553025549000/bigmike1020__cat)

Here is a working version of the image above. All I've done is upload this image to the org as a static resource named "cat".

![Working image](cat.jpeg)

