
<h1>Endereçamento IP &amp; Ferramentas de Rede</h1>

<p><strong>Módulo:</strong> Nivelamento<br>
<strong>Status:</strong> Concluído</p>

<hr>

<h2>1. Endereçamento IP</h2>

<p>O endereço IP permite identificar uma interface de rede e encaminhar pacotes até o destino correto. Para compreender como os dispositivos se comunicam, é importante conhecer os endereços públicos e privados, o gateway e o subnetting.</p>

<h3>Endereço IP público</h3>

<p>O IP público é semelhante à fachada e ao endereço externo de um prédio. Ele pode ser utilizado para identificar uma conexão ou serviço na internet, conforme a configuração da rede.</p>

<p>Normalmente, o roteador de uma residência utiliza um endereço IP público na interface voltada para a internet. Esse endereço pode ser compartilhado por vários dispositivos da rede local por meio de NAT.</p>

<h3>Endereço IP privado</h3>

<p>O IP privado é semelhante ao número de um apartamento dentro do prédio. Ele é utilizado para identificar dispositivos em redes internas e não é encaminhado diretamente pela internet pública.</p>

<p>As faixas privadas reservadas para IPv4 são:</p>

<ul>
<li><strong>10.0.0.0/8:</strong> de <code>10.0.0.0</code> a <code>10.255.255.255</code>.</li>
<li><strong>172.16.0.0/12:</strong> de <code>172.16.0.0</code> a <code>172.31.255.255</code>.</li>
<li><strong>192.168.0.0/16:</strong> de <code>192.168.0.0</code> a <code>192.168.255.255</code>.</li>
</ul>

<p>Um exemplo comum é o computador utilizando o endereço <code>192.168.1.10</code> dentro da rede doméstica.</p>

<h3>Gateway padrão</h3>

<p>O gateway padrão é o dispositivo para o qual um computador encaminha o tráfego destinado a outras redes quando não existe uma rota mais específica. Em uma residência, geralmente é o roteador.</p>

<p>Sem um gateway adequado, os dispositivos podem continuar se comunicando dentro da rede local, mas normalmente não conseguem alcançar outras redes por meio dessa rota.</p>

<h3>Subnetting (subdivisão de redes)</h3>

<p>Subnetting é a técnica de dividir uma rede IP em sub-redes menores. Isso ajuda a organizar dispositivos, controlar o tráfego e planejar a utilização dos endereços.</p>

<p>A máscara de sub-rede ou o prefixo CIDR indica qual parte do endereço corresponde à rede e qual parte pode identificar os dispositivos.</p>

<p><strong>Exemplo:</strong></p>

<pre><code>Endereço IP: 192.168.1.10
Prefixo:     /24
Máscara:     255.255.255.0
Rede:        192.168.1.0/24</code></pre>

<p>Nessa rede IPv4 convencional, os endereços de host utilizáveis vão de <code>192.168.1.1</code> a <code>192.168.1.254</code>. O endereço <code>192.168.1.0</code> identifica a rede, e <code>192.168.1.255</code> é o endereço de broadcast.</p>

<hr>

<h2>2. Ferramentas de Diagnóstico de Rede</h2>

<p>As ferramentas <code>ping</code>, <code>traceroute</code>, <code>netstat</code> e <code>nslookup</code> ajudam a investigar problemas de conectividade, identificar rotas, consultar DNS e verificar as conexões da própria máquina.</p>

<p>Elas também podem ser utilizadas em atividades de cibersegurança para reconhecimento autorizado e análise de comportamentos suspeitos.</p>

<hr>

<h2>3. PING — O destino responde?</h2>

<p>O comando <code>ping</code> testa a conectividade com um destino enviando mensagens ICMP Echo Request e aguardando possíveis respostas ICMP Echo Reply. Ele também mede o tempo de ida e volta dos pacotes.</p>

<h3>Sintaxe</h3>

<p><strong>Linux/macOS:</strong></p>

<pre><code>ping yahoo.com
ping -c 4 yahoo.com</code></pre>

<p>O primeiro comando normalmente continua enviando solicitações até ser interrompido com <code>Ctrl + C</code>. O segundo limita o teste a quatro solicitações.</p>

<p><strong>Windows:</strong></p>

<pre><code>ping yahoo.com
ping -n 4 yahoo.com</code></pre>

<h3>Exemplo de saída</h3>

<pre><code>PING yahoo.com (74.6.143.25): 56 data bytes
64 bytes from 74.6.143.25: icmp_seq=0 ttl=48 time=118.223 ms
64 bytes from 74.6.143.25: icmp_seq=1 ttl=48 time=115.891 ms

--- yahoo.com ping statistics ---
4 packets transmitted, 4 packets received, 0.0% packet loss
round-trip min/avg/max = 115.891/117.057/118.223 ms</code></pre>

<h3>Como interpretar os resultados?</h3>

<table>
<thead>
<tr>
<th>Campo</th>
<th>Significado</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>time</code></td>
<td>Tempo de ida e volta (RTT), medido em milissegundos.</td>
</tr>
<tr>
<td><code>ttl</code></td>
<td>Tempo de vida restante do pacote. O valor é reduzido pelos roteadores que o encaminham.</td>
</tr>
<tr>
<td><code>packet loss</code></td>
<td>Percentual de pacotes enviados que não receberam resposta.</td>
</tr>
</tbody>
</table>

<h3>Aplicação em cibersegurança</h3>

<p>O <em>ping sweep</em> consiste em verificar uma faixa de endereços IP para identificar possíveis hosts ativos. Essa técnica pode ser utilizada durante o reconhecimento autorizado de uma rede.</p>

<p>Se o ping falhar, mas o site abrir normalmente no navegador, isso não significa necessariamente que a conexão esteja com defeito. O destino pode bloquear ou limitar mensagens ICMP.</p>

<hr>

<h2>4. TRACEROUTE — Qual caminho os pacotes percorrem?</h2>

<p>O <code>traceroute</code> mostra os saltos da rota entre a origem e o destino, ajudando a identificar os roteadores intermediários e os tempos de resposta observados.</p>

<h3>Sintaxe</h3>

<p><strong>Linux/macOS:</strong></p>

<pre><code>traceroute yahoo.com</code></pre>

<p><strong>Windows:</strong></p>

<pre><code>tracert yahoo.com</code></pre>

<h3>Exemplo de saída</h3>

<pre><code>1  192.168.1.1       1.203 ms   1.150 ms   1.089 ms
2  10.10.0.1         8.442 ms   8.201 ms   8.150 ms
3  * * *
4  200.160.2.1      15.882 ms  15.701 ms  15.650 ms
...
9  74.6.143.25     118.220 ms 117.998 ms 118.045 ms</code></pre>

<h3>Como interpretar os resultados?</h3>

<table>
<thead>
<tr>
<th>Campo</th>
<th>Significado</th>
</tr>
</thead>
<tbody>
<tr>
<td>Número do salto</td>
<td>Posição do salto na rota investigada.</td>
</tr>
<tr>
<td>IP/nome</td>
<td>Endereço ou nome do dispositivo que respondeu naquele salto.</td>
</tr>
<tr>
<td>Tempos (ms)</td>
<td>Tempos de ida e volta observados nas sondagens.</td>
</tr>
<tr>
<td><code>* * *</code></td>
<td>As sondagens não receberam resposta dentro do tempo esperado.</td>
</tr>
</tbody>
</table>

<p>Um salto que apresenta <code>* * *</code> não significa necessariamente que a rota está interrompida. Alguns roteadores não respondem a essas sondagens, limitam as respostas ou utilizam filtros de segurança.</p>

<h3>Aplicação em cibersegurança</h3>

<p>O traceroute ajuda a compreender o caminho da comunicação e a investigar possíveis problemas de roteamento ou latência. Alterações inesperadas podem justificar uma análise adicional, mas não comprovam, isoladamente, um ataque ou redirecionamento malicioso.</p>

<hr>

<h2>5. NETSTAT — Quais conexões existem na máquina?</h2>

<p>O <code>netstat</code> apresenta informações sobre conexões de rede, portas em escuta e estatísticas de protocolos. As opções disponíveis variam conforme o sistema operacional.</p>

<h3>Sintaxe</h3>

<p><strong>Linux:</strong></p>

<pre><code>netstat -a
netstat -tupan</code></pre>

<p>O primeiro comando lista conexões e portas em escuta. O segundo combina opções para exibir conexões TCP e UDP, endereços numéricos e, quando permitido, informações dos processos associados.</p>

<p><strong>Windows:</strong></p>

<pre><code>netstat -ano</code></pre>

<p>No Windows, a opção <code>-o</code> permite visualizar o identificador do processo (PID) associado à conexão.</p>

<h3>Exemplo de saída</h3>

<pre><code>Proto  Local Address          Foreign Address        State
tcp    0.0.0.0:22             0.0.0.0:*              LISTEN
tcp    192.168.1.10:54210     172.217.29.14:443      ESTABLISHED
tcp    192.168.1.10:51022     45.33.32.156:6667      ESTABLISHED</code></pre>

<p>O formato exato da saída varia conforme o sistema operacional. O exemplo é ilustrativo.</p>

<h3>Como interpretar os resultados?</h3>

<table>
<thead>
<tr>
<th>Campo</th>
<th>Significado</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Proto</code></td>
<td>Protocolo de transporte, como TCP ou UDP.</td>
</tr>
<tr>
<td><code>Local Address</code></td>
<td>Endereço e porta locais utilizados pela conexão ou pelo serviço.</td>
</tr>
<tr>
<td><code>Foreign Address</code></td>
<td>Endereço e porta do outro lado da comunicação.</td>
</tr>
<tr>
<td><code>LISTEN</code> / <code>LISTENING</code></td>
<td>Indica que um serviço TCP está aguardando conexões.</td>
</tr>
<tr>
<td><code>ESTABLISHED</code></td>
<td>Indica que uma conexão TCP foi estabelecida.</td>
</tr>
</tbody>
</table>

<p>O endereço <code>0.0.0.0</code>, quando aparece como endereço local de escuta IPv4, geralmente indica que o serviço está associado a todas as interfaces IPv4 locais.</p>

<h3>Aplicação em cibersegurança</h3>

<p>Uma conexão com um IP desconhecido ou uma porta incomum pode justificar uma investigação. Entretanto, é necessário verificar o processo responsável, o destino, o contexto e o comportamento observado antes de concluir que existe comprometimento.</p>

<p>A porta <code>6667</code> é historicamente associada ao IRC, mas também pode ser utilizada por outros serviços. O número da porta, sozinho, não comprova atividade maliciosa.</p>

<hr>

<h2>6. NSLOOKUP — Qual IP corresponde ao domínio?</h2>

<p>O <code>nslookup</code> é uma ferramenta de consulta DNS. Ela permite investigar informações associadas a nomes de domínio, como os endereços IP retornados pelo servidor DNS.</p>

<h3>Sintaxe</h3>

<pre><code>nslookup yahoo.com</code></pre>

<h3>Exemplo de saída</h3>

<pre><code>Server:   192.168.1.1
Address:  192.168.1.1#53

Non-authoritative answer:
Name:    yahoo.com
Address: 74.6.143.25</code></pre>

<h3>Como interpretar os resultados?</h3>

<table>
<thead>
<tr>
<th>Campo</th>
<th>Significado</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Server</code></td>
<td>Nome do servidor DNS consultado, quando disponível.</td>
</tr>
<tr>
<td><code>Address</code> no topo</td>
<td>Endereço do servidor DNS que respondeu à consulta.</td>
</tr>
<tr>
<td><code>Name</code></td>
<td>Nome de domínio consultado ou retornado.</td>
</tr>
<tr>
<td><code>Address</code> na resposta</td>
<td>Endereço IP retornado para o nome consultado.</td>
</tr>
<tr>
<td><code>Non-authoritative answer</code></td>
<td>Indica que a resposta não veio diretamente de um servidor autoritativo para aquele nome. É comum em consultas recursivas e não representa, por si só, um erro.</td>
</tr>
</tbody>
</table>

<h3>Aplicação em cibersegurança</h3>

<p>O DNS é importante para compreender como os domínios são associados a serviços. Respostas inesperadas podem justificar verificações adicionais, mas um endereço IP diferente do esperado não comprova, sozinho, DNS spoofing ou comprometimento.</p>

<hr>

<h2>7. Quadro-Resumo das Ferramentas</h2>

<table>
<thead>
<tr>
<th>Ferramenta</th>
<th>Pergunta principal</th>
<th>Uso</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>ping</code></td>
<td>O destino responde às solicitações ICMP?</td>
<td>Teste básico de conectividade e latência.</td>
</tr>
<tr>
<td><code>traceroute</code> / <code>tracert</code></td>
<td>Quais saltos aparecem no caminho?</td>
<td>Investigação de rotas e latência.</td>
</tr>
<tr>
<td><code>nslookup</code></td>
<td>Quais informações DNS são retornadas para o domínio?</td>
<td>Diagnóstico de resolução de nomes.</td>
</tr>
<tr>
<td><code>netstat</code></td>
<td>Quais conexões e portas aparecem na máquina local?</td>
<td>Análise das conexões e serviços locais.</td>
</tr>
</tbody>
</table>

<h3>Ordem prática de investigação</h3>

<ol>
<li><strong>ping:</strong> teste se o destino responde às solicitações ICMP.</li>
<li><strong>traceroute:</strong> investigue os saltos e os tempos de resposta da rota.</li>
<li><strong>nslookup:</strong> confira as informações DNS do domínio.</li>
<li><strong>netstat:</strong> examine as conexões e portas da própria máquina.</li>
</ol>

<p>Essa ordem é um ponto de partida, não uma regra obrigatória. Se a suspeita inicial for um problema de DNS, por exemplo, faz sentido começar pelo <code>nslookup</code>.</p>

<hr>

<h2>8. Resumo para Revisão</h2>

<ul>
<li><strong>IP público:</strong> endereço utilizado para comunicação com redes externas, conforme a configuração da conexão.</li>
<li><strong>IP privado:</strong> endereço utilizado em redes internas IPv4.</li>
<li><strong>Gateway:</strong> próximo salto utilizado para alcançar outras redes quando não existe uma rota mais específica.</li>
<li><strong>Subnetting:</strong> divisão de uma rede em sub-redes menores.</li>
<li><strong>Ping:</strong> testa respostas ICMP e mede o tempo de ida e volta.</li>
<li><strong>Traceroute:</strong> investiga os saltos observados no caminho até o destino.</li>
<li><strong>Netstat:</strong> mostra informações de conexões e portas locais.</li>
<li><strong>Nslookup:</strong> consulta informações DNS.</li>
</ul>

<hr>

<p><a href="https://github.com/Thays-Quispe/learning-journal/blob/main/cursos/kodie/README.md">Voltar ao Nivelamento</a></p>
