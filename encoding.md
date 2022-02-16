|   Command	|   Description	|  
|---	|---	|
| echo hackthebox &#124; base64 | base64 encode |
| echo ENCODED_B64 &#124; base64 -d | base64 decode	|
| echo hackthebox &#124; xxd -p | hex encode	|
| echo ENCODED_HEX &#124; xxd -p -r | hex decode |
| echo hackthebox &#124; tr 'A-Za-z' 'N-ZA-Mn-za-m' | rot13 encode |
| echo ENCODED_ROT13 &#124; tr 'A-Za-z' 'N-ZA-Mn-za-m' | rot13 decode |

https://rot13.com/  
https://www.boxentriq.com/code-breaking/cipher-identifier
