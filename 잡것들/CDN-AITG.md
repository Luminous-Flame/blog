
akamai
cdn-aitg.widerplanet.com

aitg.widerplanet.com

onthefly native Image Content
/native, /native/*, /resize, /resize/*

wp_Static .js Content
/images/wp/*


아카마이에 cdn-aitg.widerplanet.com 78번 버전으로 활성화가 되어있고, cdn-aitg.widerplanet.com.edgekey.net이 Edge Host로 등록이 되어있습니다. AWS에 cdn-aitg.widerplanet.com 이 해당 Edge Host로 CNAME  등록되어 있고 오리진 서버 도메인은 aitg.widerplanet.com 로 되어있습니다.

'+' cp code는 이렇게 등록되어있네요
343404 — aitg.widerplanet.com
1100814 — cdn-aitg.widerplanet.com - /images/img/*
1100815 — cdn-aitg.widerplanet.com - gc-tg-images
1290024 — cdn-aitg.widerplanet.com - /native/*
1325270 — cdn-aitg.widerplanet.com - /resize/*
1503993 — cdn-aitg.widerplanet.com - /onsite/*

aitg.widerplanet.com 은 AWS Route 53에 103.105.156.227 ip로 등록 되어있습니다. 해당 IP는 Citrix의 ADE-AITG-HTTP/SSL 이름으로 등록되어있으며, 해당되는 멤버로는 aitg-01 ~ 04가 있습니다. 윤복님이 주신 이슈를 보면 aitg-01:/srv/widerplanet/gstorage/TS_508_new_info 위치에 인포마크 가 들어있을것이나, 제대로 된 반영을 위해서는 01~04 서버 전부 이미지 등록을 해드려야 하며, 해당 서버의 nginx 설정을 보면 


    location /images/ {
        if ($uri = /images/) {
            return 204;
        }
        if ($uri ~* "^/images/internal/") {
            return 403;
        }
        alias /srv/widerplanet/gstorage/;
        try_files $uri $uri/ @fallback;
        add_header Cache-Control "public";
        expires 1y;
    }

인포마크 경로인 [cdn-aitg.widerplanet.com/images/tgad_information_kakao.png](http://cdn-aitg.widerplanet.com/images/tgad_information_kakao.png 
는 웹서버의 /images 경로를 찾아야 하기 때문에 실제로는 경로 /srv/widerplanet/gstorage/ 안에 tgad_information_kakao_small.png 이미지를 추가 해드리면 됩니다. (이름이 같다면 대체)
