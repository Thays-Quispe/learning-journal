
<h1>Fundamentos de Redes e Protocolos</h1>

<p><strong>Módulo:</strong> Nivelamento<br>
<strong>Parte:</strong> 5<br>
<strong>Tema:</strong> Redes de Computadores e Comunicação</p>

<hr>

<h2>1. Introdução aos Fundamentos de Redes</h2>

<p>Para compreender a cibersegurança, primeiro precisamos entender como os computadores se comunicam. Os dispositivos conectados a uma rede trocam informações por meio de endereços, portas e protocolos.</p>

<p>Esses conhecimentos ajudam a entender como os dados chegam ao destino, como os serviços funcionam e como os profissionais de segurança identificam e protegem possíveis pontos de entrada.</p>

<h3>Como os dados chegam ao destino?</h3>

<p>Imagine que você deseja enviar uma encomenda para um prédio:</p>

<ul>
<li><strong>Endereço IP:</strong> identifica o destino na rede, como o endereço do prédio.</li>
<li><strong>Porta de rede:</strong> identifica o serviço que deve receber a comunicação, como o apartamento de destino.</li>
<li><strong>Protocolo:</strong> define as regras utilizadas para a comunicação.</li>
<li><strong>Pacotes:</strong> são unidades de dados transportadas pela rede.</li>
</ul>

<p>Na prática, os dados são divididos e encapsulados conforme os protocolos utilizados. Os dispositivos de rede encaminham essas informações até o destino correto.</p>

<hr>

<h2>2. Modelo OSI</h2>

<p>O modelo OSI (<em>Open Systems Interconnection</em>) é um modelo de referência que divide a comunicação de rede em <strong>sete camadas</strong>. Ele ajuda a entender como os dados são transmitidos entre dispositivos e facilita a identificação de problemas de conectividade.</p>

<h3>As 7 camadas do modelo OSI</h3>

<table>
<thead>
<tr>
<th>Camada</th>
<th>Nome</th>
<th>Função</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr>
<td>7</td>
<td>Aplicação</td>
<td>Oferece serviços de rede às aplicações utilizadas pelo usuário.</td>
<td>HTTP, DNS, SMTP</td>
</tr>
<tr>
<td>6</td>
<td>Apresentação</td>
<td>Trata a representação dos dados, incluindo codificação, compressão e criptografia quando aplicável.</td>
<td>Formatos de dados e codificação</td>
</tr>
<tr>
<td>5</td>
<td>Sessão</td>
<td>Organiza o estabelecimento, o gerenciamento e o encerramento de sessões de comunicação.</td>
<td>Controle de sessões</td>
</tr>
<tr>
<td>4</td>
<td>Transporte</td>
<td>Gerencia a comunicação entre aplicações, incluindo portas e mecanismos de transporte.</td>
<td>TCP, UDP</td>
</tr>
<tr>
<td>3</td>
<td>Rede</td>
<td>Realiza o endereçamento lógico e o encaminhamento de pacotes entre redes.</td>
<td>IP, roteadores</td>
</tr>
<tr>
<td>2</td>
<td>Enlace de Dados</td>
<td>Organiza a comunicação dentro do enlace local e utiliza endereços físicos quando aplicável.</td>
<td>Ethernet, Wi-Fi, switches</td>
</tr>
<tr>
<td>1</td>
<td>Física</td>
<td>Transmite sinais e bits pelo meio físico ou sem fio.</td>
<td>Cabos, conectores, sinais de rádio</td>
</tr>
</tbody>
</table>

<h3>Analogia para memorizar</h3>

<p>Imagine que você está enviando uma encomenda:</p>

<ul>
<li><strong>Aplicação:</strong> o conteúdo da encomenda.</li>
<li><strong>Apresentação:</strong> a forma como o conteúdo é organizado ou protegido.</li>
<li><strong>Sessão:</strong> a organização da comunicação entre as partes.</li>
<li><strong>Transporte:</strong> como os dados serão entregues à aplicação de destino.</li>
<li><strong>Rede:</strong> o endereço e a rota até o destino.</li>
<li><strong>Enlace:</strong> o transporte da encomenda pelo trecho local.</li>
<li><strong>Física:</strong> o meio pelo qual a informação é transmitida.</li>
</ul>

<p><strong>Importante:</strong> o modelo OSI é uma referência conceitual. Na internet real, os protocolos não correspondem sempre de maneira exata a uma única camada OSI.</p>

<hr>

<h2>3. Endereços IP e Portas de Rede</h2>

<h3>O que é um endereço IP?</h3>

<p>O IP (<em>Internet Protocol</em>) permite identificar interfaces de rede e encaminhar pacotes até seus destinos.</p>

<p>Existem duas versões principais:</p>

<ul>
<li><strong>IPv4:</strong> exemplo <code>192.168.1.10</code>.</li>
<li><strong>IPv6:</strong> exemplo <code>2001:db8::1</code>.</li>
</ul>

<h3>O que são portas de rede?</h3>

<p>As portas identificam os serviços ou processos aos quais os dados devem ser entregues em um dispositivo. Se o IP é o endereço do prédio, a porta é como o número do apartamento.</p>

<p>As portas TCP e UDP utilizam números de <strong>0 a 65535</strong>. A porta utilizada depende do protocolo de transporte e do serviço em execução.</p>

<h3>Portas importantes para memorizar</h3>

<table>
<thead>
<tr>
<th>Porta</th>
<th>Protocolo/serviço</th>
<th>Utilização</th>
</tr>
</thead>
<tbody>
<tr>
<td>20 e 21</td>
<td>FTP</td>
<td>Transferência de arquivos; a porta 21 é usada para controle no FTP tradicional.</td>
</tr>
<tr>
<td>22</td>
<td>SSH</td>
<td>Acesso remoto seguro e administração de sistemas.</td>
</tr>
<tr>
<td>25</td>
<td>SMTP</td>
<td>Envio e retransmissão de e-mails.</td>
</tr>
<tr>
<td>53</td>
<td>DNS</td>
<td>Consultas de nomes de domínio, normalmente por UDP ou TCP.</td>
</tr>
<tr>
<td>80</td>
<td>HTTP</td>
<td>Comunicação web sem TLS por padrão.</td>
</tr>
<tr>
<td>443</td>
<td>HTTPS</td>
<td>Comunicação web protegida por TLS.</td>
</tr>
<tr>
<td>3389</td>
<td>RDP</td>
<td>Acesso remoto a ambientes Windows.</td>
</tr>
</tbody>
</table>

<p><strong>Atenção:</strong> uma porta não é, por si só, um serviço. Ela é um número usado na comunicação. Um serviço pode utilizar outra porta, e uma porta aberta não significa automaticamente que existe uma vulnerabilidade.</p>

<hr>

<h2>4. Protocolo TCP</h2>

<p>O TCP (<em>Transmission Control Protocol</em>) é um protocolo de transporte que fornece um fluxo de dados confiável e ordenado entre aplicações.</p>

<h3>Analogia: uma ligação telefônica</h3>

<p>Imagine que você liga para alguém. Primeiro, a outra pessoa atende e vocês confirmam que podem conversar. Depois, a conversa começa. O TCP utiliza um processo semelhante para estabelecer uma conexão.</p>

<h3>Handshake TCP: estabelecimento da conexão</h3>

<ol>
<li><strong>SYN:</strong> o cliente solicita o início da conexão.</li>
<li><strong>SYN-ACK:</strong> o servidor responde reconhecendo a solicitação e indicando que está pronto para continuar.</li>
<li><strong>ACK:</strong> o cliente confirma a resposta e a conexão é estabelecida.</li>
<li><strong>Dados:</strong> as aplicações podem trocar dados pela conexão.</li>
</ol>

<pre><code>Cliente                    Servidor
   |                          |
   |-------- SYN ------------>|
   |<----- SYN-ACK ------------|
   |-------- ACK ------------>|
   |                          |
   |<==== Troca de dados ====>|</code></pre>

<h3>Principais características do TCP</h3>

<ul>
<li>Confirma o recebimento de dados por meio de reconhecimentos.</li>
<li>Reenvia segmentos perdidos quando necessário.</li>
<li>Entrega os dados em ordem à aplicação.</li>
<li>Utiliza mecanismos de controle de fluxo e congestionamento.</li>
<li>É adequado quando a integridade e a entrega ordenada são importantes.</li>
</ul>

<h3>Onde o TCP é utilizado?</h3>

<ul>
<li>Navegação web com HTTP/1.1 e HTTP/2.</li>
<li>Conexões SSH.</li>
<li>Transferência de arquivos.</li>
<li>Envio e recebimento de e-mails por muitos protocolos tradicionais.</li>
</ul>

<p><strong>Importante:</strong> o TCP fornece confiabilidade no transporte, mas não garante, sozinho, que uma aplicação funcionará corretamente ou que os dados estejam criptografados.</p>

<hr>

<h2>5. Protocolo UDP</h2>

<p>O UDP (<em>User Datagram Protocol</em>) é um protocolo de transporte simples que envia datagramas sem estabelecer uma conexão como a do TCP.</p>

<h3>Analogia: um cartão-postal</h3>

<p>Imagine que você envia um cartão-postal sem aviso de recebimento. A mensagem é despachada, mas você não recebe, pelo próprio protocolo, uma confirmação de que chegou ao destino.</p>

<h3>Principais características do UDP</h3>

<ul>
<li>Não estabelece uma conexão antes de enviar os datagramas.</li>
<li>Não confirma automaticamente o recebimento.</li>
<li>Não garante a entrega nem a ordem dos datagramas.</li>
<li>Possui cabeçalho simples e baixa sobrecarga.</li>
<li>Pode ser útil em aplicações sensíveis à latência.</li>
</ul>

<h3>Onde o UDP é utilizado?</h3>

<ul>
<li>Chamadas de voz e vídeo em tempo real.</li>
<li>Jogos online.</li>
<li>Consultas DNS tradicionais.</li>
<li>Transmissão de mídia e aplicações que priorizam baixa latência.</li>
<li>QUIC, utilizado pelo HTTP/3.</li>
</ul>

<p>Se um pacote de um jogo se perder, a aplicação pode continuar recebendo atualizações mais recentes em vez de esperar pela retransmissão de cada dado perdido.</p>

<p><strong>Importante:</strong> UDP não significa necessariamente que os dados serão mais rápidos em todas as situações. O desempenho depende da rede e da aplicação. Serviços que usam UDP também podem implementar seus próprios mecanismos de confiabilidade.</p>

<hr>

<h2>6. TCP vs. UDP</h2>

<table>
<thead>
<tr>
<th>Característica</th>
<th>TCP</th>
<th>UDP</th>
</tr>
</thead>
<tbody>
<tr>
<td>Estabelece conexão</td>
<td>Sim</td>
<td>Não</td>
</tr>
<tr>
<td>Confirma recebimento no protocolo</td>
<td>Sim</td>
<td>Não</td>
</tr>
<tr>
<td>Entrega confiável e ordenada</td>
<td>Sim, no fluxo de dados</td>
<td>Não é garantida pelo protocolo</td>
</tr>
<tr>
<td>Sobrecarga</td>
<td>Maior</td>
<td>Menor</td>
</tr>
<tr>
<td>Usos comuns</td>
<td>Web tradicional, SSH, transferência de arquivos</td>
<td>DNS, jogos, voz e vídeo em tempo real</td>
</tr>
</tbody>
</table>

<p><strong>Resumo para memorizar:</strong></p>

<ul>
<li><strong>TCP:</strong> prioriza a entrega confiável e ordenada.</li>
<li><strong>UDP:</strong> envia datagramas sem as garantias de entrega do TCP.</li>
</ul>

<hr>

<h2>7. Firewalls e Segurança de Redes</h2>

<p>Um firewall é um mecanismo de segurança que monitora e controla o tráfego de rede conforme regras definidas.</p>

<p>Imagine um segurança na entrada de um prédio. Ele verifica quem pode entrar e quais acessos devem ser bloqueados.</p>

<p>Um firewall pode considerar informações como endereços IP, protocolos, portas e, dependendo do tipo, o estado das conexões ou o conteúdo do tráfego.</p>

<h3>Exemplo de regra</h3>

<ul>
<li>Permitir conexões HTTPS destinadas à porta 443 de um servidor web.</li>
<li>Bloquear conexões externas à porta de administração que não precisam estar expostas à internet.</li>
<li>Permitir SSH apenas a partir de endereços autorizados.</li>
</ul>

<p>As regras corretas dependem da finalidade do sistema. Uma porta não deve ser liberada indiscriminadamente apenas porque um serviço utiliza aquele número.</p>

<hr>

<h2>8. Visão de Cibersegurança</h2>

<p>Profissionais de cibersegurança analisam endereços IP, portas, protocolos e serviços para identificar riscos e proteger redes.</p>

<h3>O que é o escaneamento de portas?</h3>

<p>O escaneamento de portas é uma técnica utilizada para verificar quais portas respondem em um dispositivo ou endereço de rede. Ele ajuda a identificar serviços acessíveis e possíveis pontos de exposição.</p>

<p>Ferramentas como o <strong>Nmap</strong> podem auxiliar nessa análise.</p>

<p>Uma porta aberta não é necessariamente vulnerável. A avaliação depende do serviço, da configuração, das atualizações e das regras de acesso.</p>

<h3>O que é um ataque DDoS?</h3>

<p>Um ataque DDoS (<em>Distributed Denial of Service</em>) tenta tornar um serviço indisponível ao sobrecarregá-lo com tráfego ou solicitações provenientes de múltiplas fontes.</p>

<p>Alguns ataques exploram tráfego UDP, mas ataques DDoS também podem utilizar TCP, HTTP e outras técnicas. O UDP, por si só, não é malicioso.</p>

<h3>Como se proteger?</h3>

<ul>
<li>Manter os sistemas e serviços atualizados.</li>
<li>Fechar ou restringir portas desnecessárias.</li>
<li>Utilizar firewalls e regras de acesso adequadas.</li>
<li>Monitorar conexões e tráfego suspeito.</li>
<li>Realizar testes somente em redes e sistemas próprios ou com autorização explícita.</li>
</ul>

<hr>

<h2>9. Resumo para Revisão</h2>

<ul>
<li><strong>Modelo OSI:</strong> divide a comunicação em sete camadas conceituais.</li>
<li><strong>IP:</strong> ajuda a identificar interfaces e encaminhar pacotes.</li>
<li><strong>Portas:</strong> identificam os serviços ou processos de destino.</li>
<li><strong>TCP:</strong> fornece transporte confiável e ordenado.</li>
<li><strong>UDP:</strong> envia datagramas sem garantir entrega ou ordem.</li>
<li><strong>Firewall:</strong> controla o tráfego com base em regras.</li>
<li><strong>Nmap:</strong> auxilia na descoberta de dispositivos, portas e serviços.</li>
<li><strong>DDoS:</strong> busca prejudicar a disponibilidade de um serviço.</li>
</ul>

<hr>

<p><a href="https://github.com/Thays-Quispe/learning-journal/blob/main/cursos/kodie/README.md">Voltar ao Nivelamento</a></p>

