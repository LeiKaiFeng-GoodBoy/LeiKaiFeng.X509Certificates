生成一个CA证书


`X509Certificate2 ca = TLSCertificate.CreateCA("LeiKaiFeng", 2048, 365);`


返回的X509Certificate2包含私钥
注意keySize过小会导致浏览器不信任
有了CA证书签发TLS证书


`X509Certificate2 tlsX509Certificate2 = TLSCertificate.CreateTlsCertificate("pornhub.com", ca, 2048, 365, "pornhub.com", "*.pornhub.com");`


返回的X509Certificate2包含私钥
注意keySize过小会导致浏览器不信任
非常非常重要的可选参数是DNS的名称,如果不添Chrome会不信任

