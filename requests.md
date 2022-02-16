|   Command	|   Description	|  
|---	|---	|
| curl http:/SERVER_IP:PORT/ | cURL GET request |
| curl -s http:/SERVER_IP:PORT/ -X POST | cURL POST request	|
| curl -s http:/SERVER_IP:PORT/ -X POST -d "param1=sample" | cURL POST request with data	|

# Post request
```buildoutcfg
curl -s http://SERVER_IP:PORT/ -X POST
```
`-s` flag to reduce cluttering the response with unnecessary data.

## Send data:
```buildoutcfg
curl -s http://SERVER_IP:PORT/ -X POST -d "param1=sample"
```