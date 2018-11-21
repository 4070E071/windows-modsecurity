# windows-modsecurity
## download
https://www.apachelounge.com/download/

https://github.com/SpiderLabs/owasp-modsecurity-crs
# install step
https://thk.kanzae.net/net/itc/t7194/

https://stackoverflow.com/questions/41056361/installing-mod-security2-so-on-apache-2-4-23-on-windows-7
```
將"libcurl.dll"和"yajl.dll"放到"/xampp/apache/bin/"
將"modsecurity.conf"放入"/xampp/apache/conf/"
新增"unicode.mappin"g到"/xampp/apache/conf/"
新增"modsecurity資料夾"到"/xampp/apache/conf/"
將"crs-setup.conf.example" rename "crs-setup.conf"並複製到"/xampp/apache/conf/modsecurity/"
將"rules資料夾"複製到"/xampp/apache/conf/modsecurity/"
將"mod_security2.so"複製到"/xampp/apache/modules/"
```
# edit .conf file
## edit httpd.conf
### join
```
LoadModule security2_module modules/mod_security2.so

<IfModule security2_module>
Include conf/modsecurity.conf
Include conf/modsecurity/crs-setup.conf
Include conf/modsecurity/rules/*.conf
</IfModule>
```
## edit modsecurity.conf
### modify
```
"#SecRuleEngine DetectionOnly" to "SecRuleEngine On"
"#SecRequestBodyAccess On" to "SecRequestBodyAccess Off"
```
# restart xampp-apache
