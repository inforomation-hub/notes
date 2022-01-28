# General

## Apply proxy
```
proxies = { 'https' : 'https://user:password@proxyip:port' } 
r = requests.get('https://url', proxies=proxies)
```

## Apply proxy on session
```
proxies = {'http': 'http://10.11.4.254:3128'}
s = requests.session()
s.proxies.update(proxies)
s.get("http://www.example.com")
```
