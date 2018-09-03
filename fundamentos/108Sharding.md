# Sharding

O Sharding é um tipo de particionamento de banco de dados que separa os bancos de dados muito grandes em partes menores, mais rápidas e mais facilmente gerenciadas, chamadas de shards. A palavra shard significa _uma pequena parte de um todo_.

No sentido mais simples, dividir seu banco de dados envolve dividir seu grande banco de dados em muitos banco de dados muito menores que não compartilham nada e podem ser distribuídos por vários servidores.

Tecnicamente, sharding é um sinônimo de particionamento horizontal. Na prática, o termo é frequentemente usado para se referir a qualquer particiona mento de banco de dados que tenho como objetivo tornar um banco de dados muito grande mais gerenciável,

O conceito de governança por trás do sharding é baseado na ideia de que como o tamanho de um banco de dados e o número de transações por unidade de tempo feita no banco de dados aumentam linearmente, o tempo de resposta para consultar o banco de dados aumenta exponencialmente.

Além disso os custos de criação e manutenção de um banco de dados muito grande em um só lugar pode aumentar exponencialmente porque o banco de dados exigirá computadores de última geração. Em contraste, os fragmentos de dados podem ser distribuídos em vários servidores de mercadorias muito mais baratos. Os fragmentos de dados têm comparativamente pouca restrição no que se refere aos requisitos de hardware e software.

Em alguns casos, o sharding de banco de dados pode ser feito de forma bastante simples. Um exemplo comum é dividir um banco de dados de clientes geograficamente. Os clientes localizados na costa leste podem ser colocados em um servidor, enquanto os clientes na costa oeste podem ser colocados em um segundo servidor. Supondo que não haja clientes com vários locais, a divisão é fácil de manter e criar regras.

O particionamento de dados pode ser um processo mais complexo em alguns cenários, no entanto. A fragmentação de um banco de dados que contém dados menos estruturados, por exemplo, pode ser muito complicada e os fragmentos resultantes podem ser difíceis de manter. Em bancos de dados ela é tradicionalmente implementada através da criação de uma estrutura master-slave. O banco master é aquele onde são efetuados as alterações, que são então replicadas para o slave.
