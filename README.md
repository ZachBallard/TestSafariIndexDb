# ImageBlobDemo

This is a demo on storing the images as Blob object in indexed DB using [JsStore][l_jsstore].

It would be very easy to understand if you are familiar with Jquery and JsStore. 
In case you need, you can go through [Jquery Tutorial][l_jquery_w3] and [JsStore Tutorial][l_jsstore_tutorial].

We are just storing the Image Blob object in the Indexed DB and using createObjectURL method to generate a url, and set that url to image src to display the image.

In this demo,code is written only for storing the image uploaded from your local machine but we can also download the image and keep it in local indexed DB using the code below

```sh

var xhr = new XMLHttpRequest();
xhr.open("GET", yourImageUrl);
xhr.responseType = "blob";
xhr.onload = function response(e) {
   var urlCreator = window.URL || window.webkitURL;
   // this.response is your downloaded image Blob object
   var imageUrl = urlCreator.createObjectURL(this.response);
   document.querySelector("#yourImageId").src = imageUrl; 
};
xhr.send();

```
**Note:** The above code will only work if the requested server allow CORS

[l_jsstore]: <www.jsstore.net>
[l_jquery_w3]: <https://www.w3schools.com/jquery/>
[l_jsstore_tutorial]: <www.jsstore.net/Tutorial>
