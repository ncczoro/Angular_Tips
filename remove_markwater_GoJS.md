# remove watermark GoJS
![truoc khi xoa][gojsWaterMark]

Vao nodeModule\gojs\release\go.js sua code 
``` js
function Sa(a){for(var b=[],c=0;256>c;c++)b["0123456789abcdef".charAt(c>>4)+"0123456789abcdef".charAt(c&15)]=String.fromCharCode(c);a.length%2&&(a="0"+a);c=[];for(var d=0,e=0;e<a.length;e+=2)c[d++]=b[a.substr(e,2)];a=c.join("");a=""===a?"0":a;b=[];for(c=0;256>c;c++)b[c]=c;for(c=d=0;256>c;c++)d=(d+b[c]+119)%256,e=b[c],b[c]=b[d],b[d]=e;d=c=0;for(var f="",g=0;g<a.length;g++)c=(c+1)%256,d=(d+b[c])%256,e=b[c],b[c]=b[d],b[d]=e,f+=String.fromCharCode(a.charCodeAt(g)^b[(b[c]+b[d])%256]);if(f=='GoJS 2.1 evaluation'){f='';}if(f=='(c) 1998-2021 Northwoods Software'){f='';}if(f=='Not for distribution or production use'){f='';}if(f=='gojs.net'){f=' ';}return f;}
```
 

sau khi sua

![sau khi sua][gojsRemoveWaterMark]

[gojsWaterMark]: assset/goJSwaterMark.png
[gojsRemoveWaterMark]: assset/removeMark.png