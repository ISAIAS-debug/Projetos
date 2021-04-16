# Resolvendo Problemas de Suporte com Linux

#   :robot:

Bem, vamos lá, irei demonstrar diversos procedimentos simples no terminal Linux que me ajuram a solucionar 
problemas durante minha atividade no suporte ao usuario:

# Situação 1 :
Você se depara com uma Estação de trabalho usando Linux que não esta conectada a rede por algum motivo, sem equipamentos para saber se o
problema é o cabo (em uma conexão cabeada), ou a placa de rede, o que fazer?

- Comando :
#watch ip addr show

- Solução:
O comando watch combinado com o ip addr show pode ti mostrar a mudança do campo  state(UP/DOWN) da placa de rede, o que é util para saber se esta havendo o up do link quando colocamos ou DOWN quando retiramos o cabo.

watch = mostra a saida atualizando a cada 2s
ip addr show = mostra status da placa de rede 


Exemplo da saida do "watch ip addr show" , para duas placas de redes "PLACA DE REDE" e "PLACA DE REDE1"

OBS: Repare que a PLACA DE REDE  possui state DOWN e a PLACA DE REDE1 possui state UP

 - PLACA DE REDE: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc fq_codel state DOWN group default qlen 1000
 
 
 - PLACA DE REDE1 : <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000



