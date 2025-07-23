


Every 2.0s: curl http://127.0.0.1/nginx_status                                                                                                         poc-ade-01: Tue Jun  4 15:29:23 2024

  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
   0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0 100   117  100   117    0     0   257k      0 --:--:-- --:--:-- --:--:--  114k
Active connections: 395
server accepts handled requests
 15730 15730 1881973
Reading: 0 Writing: 239 Waiting: 156



R21-F-L7-2> stat lb vserver POC-AA-HTTP | grep conn
Current client connections                        --                  241
Current Client Est connections                    --                  241
Current server connections                        --                  239


http://eminem.cns.widerlab.io:7070/perftest/418
400 커넥션

https://view.dsp.widerlab.io/d/NT3Z0MJik/citrix-adc-stats?var-datasource_prometheus=dsp-thanos&var-nsip=All&var-lbservicegroup=All&var-lbvservers=POC-AA-HTTP&var-lbvservers=POC-PASSBACK-HTTP&from=1717485525000&to=1717486725000&orgId=1


