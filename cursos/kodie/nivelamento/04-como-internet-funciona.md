
<h1>Como a Internet Funciona</h1>

<p><strong>Módulo:</strong> Nivelamento<br>
<strong>Tema:</strong> Fundamentos de Redes e Internet</p>

<hr>

<h2>1. O que é a Internet?</h2>

<p>A internet é uma enorme rede de computadores e dispositivos conectados entre si, que permite a troca de informações em todo o mundo.</p>

<p>Quando digitamos o endereço de um site e pressionamos <strong>Enter</strong>, várias etapas acontecem nos bastidores para que o navegador encontre o servidor correto, solicite os dados e exiba a página na tela.</p>

<p>Essa comunicação acontece por meio de endereços, equipamentos e protocolos que permitem que os dispositivos troquem informações.</p>

<hr>

<h2>2. Modelo Cliente-Servidor</h2>

<p>A navegação na internet funciona frequentemente com base no modelo <strong>cliente-servidor</strong>.</p>

<p>Imagine um restaurante:</p>

<ul>
<li><strong>Cliente:</strong> é quem faz o pedido. Na internet, pode ser o seu celular ou computador, por meio do navegador.</li>
<li><strong>Servidor:</strong> é como a cozinha do restaurante. Ele recebe a solicitação, processa o pedido e envia os dados solicitados.</li>
</ul>

<p>Por exemplo, quando você acessa um site, o navegador solicita os arquivos necessários, e o servidor responde enviando os dados para que a página seja exibida.</p>

<hr>

<h2>3. Os 10 Termos Essenciais da Internet</h2>

<h3>1. IP (Internet Protocol)</h3>

<p>O endereço IP identifica uma interface de rede e permite direcionar os dados ao destino correto. É semelhante a um endereço usado para localizar um dispositivo em uma rede.</p>

<p>Existem duas versões principais:</p>

<ul>
<li><strong>IPv4:</strong> utiliza endereços como <code>192.168.1.10</code>.</li>
<li><strong>IPv6:</strong> utiliza endereços maiores, como <code>2001:db8::1</code>.</li>
</ul>

<h3>2. DNS (Domain Name System)</h3>

<p>O DNS funciona como uma lista telefônica da internet. Ele permite encontrar informações associadas a um nome de domínio, incluindo os endereços IP necessários para acessar um serviço.</p>

<p><strong>Exemplo:</strong> ao acessar <code>www.exemplo.com</code>, o navegador pode consultar o DNS para descobrir para qual endereço IP deve direcionar a conexão.</p>

<h3>3. HTTP (Hypertext Transfer Protocol)</h3>

<p>O HTTP é um protocolo utilizado para a comunicação entre clientes e servidores web. Ele define como as requisições são enviadas e como as respostas são transmitidas.</p>

<h3>4. HTTPS (HTTP Secure)</h3>

<p>O HTTPS utiliza o HTTP protegido por uma conexão criptografada com TLS. Isso ajuda a proteger os dados trocados entre o navegador e o servidor contra leitura ou alteração durante o transporte.</p>

<p>É especialmente importante para proteger informações como senhas e dados pessoais. Entretanto, o uso de HTTPS, por si só, não garante que um site seja confiável.</p>

<h3>5. URL (Uniform Resource Locator)</h3>

<p>A URL é o endereço utilizado para localizar um recurso na internet, como uma página, uma imagem ou um documento.</p>

<p><strong>Exemplo:</strong></p>

<pre><code>https://www.exemplo.com.br/cursos/aula1</code></pre>

<p>Uma URL pode conter o protocolo, o domínio, o caminho do recurso e, opcionalmente, outros componentes, como parâmetros de consulta.</p>

<h3>6. Domínio</h3>

<p>O domínio é o nome legível utilizado para identificar um serviço ou recurso na internet.</p>

<p><strong>Exemplo:</strong> em <code>www.exemplo.com.br</code>, o nome de domínio é <code>exemplo.com.br</code>, enquanto <code>www</code> é um subdomínio.</p>

<p>Os domínios facilitam o acesso aos serviços sem que seja necessário memorizar seus endereços IP.</p>

<h3>7. Servidor</h3>

<p>Um servidor é um computador ou sistema que disponibiliza serviços, dados ou recursos para outros dispositivos.</p>

<p>Um servidor web, por exemplo, pode armazenar arquivos de um site, processar requisições e enviar respostas aos navegadores.</p>

<h3>8. Cliente</h3>

<p>O cliente é o dispositivo ou programa que solicita um serviço. Um navegador, como Firefox ou Chrome, atua como cliente quando acessa um site.</p>

<p>O cliente envia requisições e recebe respostas do servidor.</p>

<h3>9. Protocolo</h3>

<p>Um protocolo é um conjunto de regras que define como os dispositivos se comunicam e trocam informações.</p>

<p>Alguns exemplos importantes são:</p>

<ul>
<li><strong>IP:</strong> ajuda a encaminhar pacotes entre redes.</li>
<li><strong>TCP:</strong> fornece transporte confiável e ordenado de dados.</li>
<li><strong>UDP:</strong> permite o envio de datagramas sem estabelecer as mesmas garantias de entrega do TCP.</li>
<li><strong>HTTP/HTTPS:</strong> permitem a comunicação utilizada na web.</li>
<li><strong>DNS:</strong> permite consultar informações sobre nomes de domínio.</li>
</ul>

<h3>10. Requisição (Request)</h3>

<p>Uma requisição é uma mensagem enviada por um cliente a um servidor para solicitar uma ação ou um recurso.</p>

<p>Por exemplo, ao abrir uma página, o navegador pode enviar uma requisição HTTP para obter o conteúdo do site.</p>

<p>O servidor processa a solicitação e retorna uma resposta, que pode incluir o conteúdo pedido ou um código de status indicando o resultado.</p>

<hr>

<h2>4. O que acontece quando você acessa um site?</h2>

<ol>
<li><strong>Você digita a URL:</strong> informa ao navegador qual endereço deseja acessar.</li>
<li><strong>O navegador identifica o domínio:</strong> verifica se já possui informações úteis em cache e, quando necessário, consulta o DNS.</li>
<li><strong>O endereço IP é obtido:</strong> o navegador utiliza as informações disponíveis para localizar o servidor.</li>
<li><strong>A conexão é estabelecida:</strong> o dispositivo se comunica com o servidor usando os protocolos adequados.</li>
<li><strong>Uma requisição é enviada:</strong> o navegador solicita a página ou outro recurso.</li>
<li><strong>O servidor responde:</strong> envia os dados solicitados ou uma resposta de erro.</li>
<li><strong>O navegador exibe a página:</strong> interpreta os arquivos recebidos e apresenta o conteúdo na tela.</li>
</ol>

<hr>

<h2>5. Resumo para Revisão</h2>

<table>
<thead>
<tr>
<th>Termo</th>
<th>Função principal</th>
</tr>
</thead>
<tbody>
<tr>
<td>IP</td>
<td>Identifica uma interface de rede e ajuda a direcionar os dados.</td>
</tr>
<tr>
<td>DNS</td>
<td>Consulta informações associadas aos nomes de domínio.</td>
</tr>
<tr>
<td>HTTP</td>
<td>Define a comunicação entre clientes e servidores web.</td>
</tr>
<tr>
<td>HTTPS</td>
<td>Protege a comunicação HTTP com criptografia TLS.</td>
</tr>
<tr>
<td>URL</td>
<td>Localiza um recurso na internet.</td>
</tr>
<tr>
<td>Domínio</td>
<td>Fornece um nome legível para identificar um serviço ou recurso.</td>
</tr>
<tr>
<td>Servidor</td>
<td>Disponibiliza serviços e responde às solicitações.</td>
</tr>
<tr>
<td>Cliente</td>
<td>Solicita e utiliza os serviços disponíveis na rede.</td>
</tr>
<tr>
<td>Protocolo</td>
<td>Define regras para a comunicação entre dispositivos.</td>
</tr>
<tr>
<td>Requisição</td>
<td>Solicita uma ação ou um recurso ao servidor.</td>
</tr>
</tbody>
</table>

<hr>

<h2>6. Relação com a Cibersegurança</h2>

<p>Compreender como a internet funciona é essencial para estudar segurança de redes, análise de tráfego, testes de intrusão e segurança web.</p>

<p>Esses conceitos ajudam a entender como funcionam ferramentas como Wireshark e Nmap, além de facilitar o estudo de vulnerabilidades relacionadas a protocolos, serviços e aplicações web.</p>

<hr>

<p><a href="https://github.com/Thays-Quispe/learning-journal/blob/main/cursos/kodie/README.md">Voltar ao Nivelamento</a></p>
