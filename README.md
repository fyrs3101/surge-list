```

[General]
loglevel = notify
allow-wifi-access = true
dns-server = system, 183.221.253.100, 223.5.5.5, 1.1.1.1, 1.0.0.1, 9.9.9.9, 8.8.8.8
skip-proxy = 192.168.0.0/16, 10.0.0.0/8, 172.16.0.0/12, 100.64.0.0/10, 127.0.0.1, localhost, *.local
ipv6 = true
port = 8887
socks-port = 8888
external-controller-access = password@0.0.0.0:6170
bypass-system = true
interface = 0.0.0.0
socks-interface = 0.0.0.0
exclude-simple-hostnames = true
enhanced-mode-by-rule = false
show-error-page-for-reject = true

[Replica]
hide-apple-request = false
hide-crashlytics-request = true
use-keyword-filter = false

[Proxy]
Direct = direct


[Proxy Group]
Proxy = select, Direct, Auto, CN, HK, JP, US
Apple = select, Direct, CN, HK
nProxy = select, Direct, CN, HK


[Rule]
PROCESS-NAME,ss-local,Direct
PROCESS-NAME,Speedtest,nProxy

USER-AGENT,WeChat*,Direct
USER-AGENT,MicroMessenger*,Direct

DOMAIN-SUFFIX,lastpass.com,Direct
DOMAIN-SUFFIX,zaihua.io,Direct
DOMAIN-SUFFIX,netgear.com,Direct
DOMAIN-SUFFIX,evernote.com,Proxy
DOMAIN-SUFFIX,yinxiang.com,nProxy
DOMAIN-SUFFIX,sublimetext.com,REJECT
DOMAIN-SUFFIX,sublimehq.com,REJECT

# Rulesets
RULE-SET,SYSTEM,Direct
RULE-SET,https://github.com/congcong0806/surge-list/raw/master/congcong.list, Proxy
RULE-SET,https://github.com/congcong0806/surge-list/raw/master/apple.list, Apple

#scomper
RULE-SET,https://github.com/scomper/surge-list/raw/master/adblock.list, REJECT
RULE-SET,https://github.com/scomper/surge-list/raw/master/reject.list, REJECT-TINYGIF
RULE-SET,https://github.com/scomper/surge-list/raw/master/cn.list, nProxy
RULE-SET,https://github.com/scomper/surge-list/raw/master/video.list, Proxy
RULE-SET,https://github.com/scomper/surge-list/raw/master/blocked.list, Proxy
RULE-SET,https://github.com/scomper/surge-list/raw/master/telegram.list, Proxy

# lhie1
RULE-SET,https://github.com/lhie1/Rules/raw/master/Auto_New/reject.list, REJECT
RULE-SET,https://github.com/lhie1/Rules/raw/master/Auto_New/domestic.list, nProxy
RULE-SET,https://github.com/lhie1/Rules/raw/master/Auto_New/media.list, Proxy
RULE-SET,https://github.com/lhie1/Rules/raw/master/Auto_New/proxy.list, Proxy

RULE-SET,LAN,Direct
GEOIP,CN,nProxy
FINAL,Proxy,dns-failed

[Host]
*.taobao.com = server:223.5.5.5
*.jd.com = server:223.5.5.5
*.tmall.com = server:223.5.5.5

[URL Rewrite]
^http://www\.google\.cn http://www.google.com.hk header
^http://bbsanalytics\.weiphone\.net _ reject
^http://capi\.douyucdn\.cn/lapi/sign/appapi/ _ reject
^http://www\.inoreader\.com/adv/ _ reject
^http://api\.mobile\.youku\.com/adv/ _ reject
^http://mp\.weixin\.qq\.com/mp/report _ reject
^http://g\.tbcdn\.cn/mtb/ _ reject
^http://wbapp\.mobile\.sina\.cn/interface/win/winad\.php _ reject
^http://wbapp\.mobile\.sina\.cn/interface/f/ttt/v3/freshguidad\.php _ reject
^http://wbapp\.mobile\.sina\.cn/wbapplua/wbpullad\.lua _ reject
^http://sdkapp\.mobile\.sina\.cn/interface/sdk/actionad\.php _ reject
^http://sdkapp\.mobile\.sina\.cn/interface/sdk/sdkad\.php _ reject
^http://u1\.img\.mobile\.sina\.cn/public/files/image/750x120_ _ reject

[Header Rewrite]
^http://www\.biquge\.com\.tw header-del Cookie
^https?://www\.zhihu\.com header-replace User-Agent Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_4) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/11.1 Safari/605.1.15
