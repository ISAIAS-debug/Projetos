# Resolvendo Problemas de Suporte com Linux

#   :robot:

Bem, vamos lá, irei demonstrar diversos procedimentos simples no terminal Linux que me ajuram a solucionar 
problemas durante minha atividade no suporte ao usuario:

# COMANDO WATCH:

Para começo vou usar combinações de comandos com o watch, ele na forma padrão atualiza a saida a cada 2 segundos de outro comando mostrando uma mudança 
de status do sistema.


# Situação 1 :
Você se depara com uma Estação de trabalho usando Linux que não esta conectada a rede por algum motivo, sem equipamentos para saber se o
problema é o cabo (em uma conexão cabeada), ou se a  placa de rede não esta subindo o link, o que fazer?

- Comando :
#watch ip addr show

- Solução:
O comando watch combinado com o ip addr show pode ti mostrar a mudança do campo  state(UP/DOWN) da placa de rede, o que é util para saber se esta havendo o up do link quando colocamos ou DOWN quando retiramos o cabo.

- watch = mostra a saida atualizando a cada 2s
- ip addr show = mostra status da placa de rede 


Exemplo da saida do "watch ip addr show" , para duas placas de redes "PLACA DE REDE" e "PLACA DE REDE1"

OBS: Repare que a PLACA DE REDE  possui state DOWN e a PLACA DE REDE1 possui state UP

 - PLACA DE REDE: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc fq_codel state DOWN group default qlen 1000
 
 
 - PLACA DE REDE1 : <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000


# Situação 2 :
Você quer saber como vai o uso da sua memoria RAM e SWAP para tomar uma  decisão sobre como melhor configurar a prioridade de quando usar SWAP ou se o PC
precisa de mais memoria RAM ?

- Comnado :
- #watch free -h

- Solução :
Esse comando vai mostrar durante o uso do PC como esta o consumo da memoria, na medidade que você abri novos programas os status da memoria em USO e memoria 
LIVRE vai alterando e tambem em qual momento o PC começa a usar SWAP.

- watch = Mostra o comando atualizando a cada 2s
- free -h = Status da memoria RAM e a opção "-h" deixa a coisa toda mais legivel.





