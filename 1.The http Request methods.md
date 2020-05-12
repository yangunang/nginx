**nginx  limit Request methods**

# 1.The http Request methods 

https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods

​        

# 2.nginx limit Request methods
A. use nginx  Directive if 

```
                add_header Allow "GET, POST, HEAD" always;
                if ($request_method ~ (POST|GET) ){

                  return 400;

                }
```

B. use nginx limit_except  module

                  add_header Allow "GET, POST, HEAD" always;
    			  limit_except GET POST {
                        deny all;
                   }
## 3.CURL command test

```
curl   --request  PUT  requestURL
     return 400   #status code

curl   --request  GET  requestURL
     return url resource
     
use curl command I parament verification the response head
curl  -I  requestURL 

```

  
