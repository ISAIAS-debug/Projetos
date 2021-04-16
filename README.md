# Resolvendo Problemas com Linux

#   :robot:

Bem, vamos lá, irei demonstrar diversos procedimentos simples no terminal Linux que me ajuram a solucionar 
problemas durante minha atividade no suporte ao usuario:

# Situação 1 :
Você se depara com uma Estação de trabalho usando Linux que não esta conectada a rede por algum motivo, sem equipamentos para saber se o
problema é o cabo (em uma conexão cabeada), ou a placa de rede, o que fazer?

- Comando :
#watch ip addr show

- Solução:
O comando watch combinado com o ip addr show pode ti mostrar a mudança do campo  state(UP/DOWN) da placa de rede, o que é util para saber se esta havendo o up do link quando colocamos ou retiramos o cabo.

watch = mostra a saida atualizando a cada 2s
ip addr show = mostra status da placa de rede 


EXEMPLO DE SAIDA DO COMANDO : ip addr show 

OBS: Repare que a PLACA DE REDE  possui state DOWN e a PLACA DE REDE1 possui state UP

- PLACA DE REDE LOOPBACK: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
-   link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
-    inet 127.0.0.1/8 scope host lo
-       valid_lft forever preferred_lft forever
-   inet6 ::1/128 scope host 
-       valid_lft forever preferred_lft forever
- PLACA DE REDE: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc fq_codel state DOWN group default qlen 1000
-    link/ether ENDEREÇO MAC brd ff:ff:ff:ff:ff:ff
- PLACA DE REDE1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
-    link/ether ENDEREÇO  MAC  brd ff:ff:ff:ff:ff:ff
-    inet 172.20.10.4/28 brd 172.20.10.15 scope global dynamic noprefixroute wlp9s0
-       valid_lft 84286sec preferred_lft 84286sec
-    inet6 2804:214:8197:213e:355f:6212:868e:b02e/64 scope global temporary dynamic 
-       valid_lft 603553sec preferred_lft 84763sec
-    inet6 2804:214:8197:213e:c4a1:c6ea:36b1:572/64 scope global mngtmpaddr noprefixroute 
-       valid_lft forever preferred_lft forever
-    inet6 fe80::26ee:450:5650:88d8/64 scope link noprefixroute 
-      valid_lft forever preferred_lft forever
