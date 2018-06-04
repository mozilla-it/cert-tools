# cert-tools
collection of for dealing with ssl|tls certificates

## ssl-inspect and friends

### ssl-inspect

The ssl-inpsect script can be run on local files (x509, req, rsa) or cat the
contents of one of these files into it.  Hostnames and optional port can be
specified to grab the x509 on a remote host.

$ ssl-inspect google.com
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number: 4911984191192767955 (0x442adf98da611dd3)
    Signature Algorithm: sha256WithRSAEncryption
        Issuer: C=US, O=Google Trust Services, CN=Google Internet Authority G3
        Validity
            Not Before: May 15 21:06:06 2018 GMT
            Not After : Aug  7 19:53:00 2018 GMT
        Subject: C=US, ST=California, L=Mountain View, O=Google LLC, CN=*.google.com
        Subject Public Key Info:
            Public Key Algorithm: id-ecPublicKey
                Public-Key: (256 bit)
                pub:
                    04:e1:d4:41:ae:82:6c:4e:bb:9f:63:78:8d:28:39:
                    c5:7e:f1:4d:45:3d:f2:c7:55:45:7e:cc:e3:a7:01:
                    e8:8f:bb:05:b6:de:93:19:e0:59:0b:03:c9:da:6c:
                    ab:bd:f5:9f:5d:ea:78:d2:35:ec:72:bd:2f:0b:aa:
                    ec:c0:ed:95:20
                ASN1 OID: prime256v1
                NIST CURVE: P-256
        X509v3 extensions:
            X509v3 Extended Key Usage:
                TLS Web Server Authentication
            X509v3 Key Usage: critical
                Digital Signature
            X509v3 Subject Alternative Name:
                DNS:*.google.com, DNS:*.android.com, DNS:*.appengine.google.com, DNS:*.cloud.google.com, DNS:*.db833953.google.cn, DNS:*.g.co, DNS:*.gcp.gvt2.com, DNS:*.google-analytics.com, DNS:*.google.ca, DNS:*.google.cl, DNS:*.google.co.in, DNS:*.google.co.jp, DNS:*.google.co.uk, DNS:*.google.com.ar, DNS:*.google.com.au, DNS:*.google.com.br, DNS:*.google.com.co, DNS:*.google.com.mx, DNS:*.google.com.tr, DNS:*.google.com.vn, DNS:*.google.de, DNS:*.google.es, DNS:*.google.fr, DNS:*.google.hu, DNS:*.google.it, DNS:*.google.nl, DNS:*.google.pl, DNS:*.google.pt, DNS:*.googleadapis.com, DNS:*.googleapis.cn, DNS:*.googlecommerce.com, DNS:*.googlevideo.com, DNS:*.gstatic.cn, DNS:*.gstatic.com, DNS:*.gvt1.com, DNS:*.gvt2.com, DNS:*.metric.gstatic.com, DNS:*.urchin.com, DNS:*.url.google.com, DNS:*.youtube-nocookie.com, DNS:*.youtube.com, DNS:*.youtubeeducation.com, DNS:*.yt.be, DNS:*.ytimg.com, DNS:android.clients.google.com, DNS:android.com, DNS:developer.android.google.cn, DNS:developers.android.google.cn, DNS:g.co, DNS:goo.gl, DNS:google-analytics.com, DNS:google.com, DNS:googlecommerce.com, DNS:source.android.google.cn, DNS:urchin.com, DNS:www.goo.gl, DNS:youtu.be, DNS:youtube.com, DNS:youtubeeducation.com, DNS:yt.be
            Authority Information Access:
                CA Issuers - URI:http://pki.goog/gsr2/GTSGIAG3.crt
                OCSP - URI:http://ocsp.pki.goog/GTSGIAG3

            X509v3 Subject Key Identifier:
                4B:12:FC:1A:8F:76:25:43:55:5B:6A:72:00:E4:5D:E9:B2:42:A7:3F
            X509v3 Basic Constraints: critical
                CA:FALSE
            X509v3 Authority Key Identifier:
                keyid:77:C2:B8:50:9A:67:76:76:B1:2D:C2:86:D0:83:A0:7E:A6:7E:BA:4B

            X509v3 Certificate Policies:
                Policy: 1.3.6.1.4.1.11129.2.5.3
                Policy: 2.23.140.1.2.2

            X509v3 CRL Distribution Points:

                Full Name:
                  URI:http://crl.pki.goog/GTSGIAG3.crl

    Signature Algorithm: sha256WithRSAEncryption
         81:da:d5:ab:df:e5:35:33:9d:e2:22:d4:47:9a:3c:18:00:3c:
         2f:61:1b:ac:b9:56:b8:06:b4:aa:da:4a:16:7f:6b:52:5a:15:
         9a:0e:d1:83:fe:a2:92:16:1a:84:38:d3:56:8e:b0:03:d1:18:
         f8:f7:66:12:46:6f:93:43:da:2e:f8:da:a1:fb:53:eb:22:5a:
         46:ce:68:02:91:db:53:51:5e:0b:45:82:55:6e:3c:14:36:c3:
         98:06:3b:f2:3f:4e:af:d2:65:3b:66:b4:44:5a:fb:e5:9b:77:
         4b:eb:3c:1f:3e:ff:fa:14:6d:b0:0a:d8:38:b5:67:88:3e:35:
         3f:b1:ad:6b:d1:b2:74:52:19:e2:53:09:9d:69:99:ee:38:46:
         46:b4:1a:73:4e:bd:80:c5:cf:42:4b:22:f0:6b:33:db:ca:b0:
         2f:2e:7e:ee:84:ae:7e:f3:f7:6d:50:e6:c6:68:78:21:c7:f3:
         54:50:fc:48:2b:e0:b6:6f:19:c1:5e:07:f5:b6:48:65:da:85:
         93:5a:68:a4:aa:9e:03:63:d4:bb:d2:02:da:3d:17:0d:3b:57:
         28:c8:56:70:20:bf:10:18:82:17:8f:84:83:b4:7b:09:79:97:
         76:15:f4:8a:3b:a8:76:8b:38:da:ce:f0:7b:5e:b5:75:0b:56:
         1d:c7:58:bd

### ssl-sans

The ssl-sans symlink allows for extracting the [S]ubject [A]lternative [N]ames.
It can be run on local x509 files or on remote hosts.

$ ssl-sans google.com
*.google.com
*.android.com
*.appengine.google.com
*.cloud.google.com
*.db833953.google.cn
*.g.co
*.gcp.gvt2.com
*.google-analytics.com
*.google.ca
*.google.cl
*.google.co.in
*.google.co.jp
*.google.co.uk
*.google.com.ar
*.google.com.au
*.google.com.br
*.google.com.co
*.google.com.mx
*.google.com.tr
*.google.com.vn
*.google.de
*.google.es
*.google.fr
*.google.hu
*.google.it
*.google.nl
*.google.pl
*.google.pt
*.googleadapis.com
*.googleapis.cn
*.googlecommerce.com
*.googlevideo.com
*.gstatic.cn
*.gstatic.com
*.gvt1.com
*.gvt2.com
*.metric.gstatic.com
*.urchin.com
*.url.google.com
*.youtube-nocookie.com
*.youtube.com
*.youtubeeducation.com
*.yt.be
*.ytimg.com
android.clients.google.com
android.com
developer.android.google.cn
developers.android.google.cn
g.co
goo.gl
google-analytics.com
google.com
googlecommerce.com
source.android.google.cn
urchin.com
www.goo.gl
youtu.be
youtube.com
youtubeeducation.com
yt.be

### ssl-validity

The ssl-validity symlink allows for checking the Validity section of an x509
certificate either local or remote.

$ ssl-validity google.com
Not Before: May 15 21:06:06 2018 GMT
Not After : Aug  7 19:53:00 2018 GMT

### ssl-compare

The ssl-compare symlink allows for comparing two x509 certificates, usually
between a local cert file and a remote one provided by a webserver.  The return
code will indicate if the diff was exact or different.

$ ssl-compare www.srihash.org.crt www.srihash.org
$
