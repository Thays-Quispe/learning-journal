# 💗 Redes

<p align="center">Endereçamento IP, conectividade, portas e diagnóstico de rede.</p>

<h2>1. Conceitos essenciais</h2>

<ul>
  <li><strong>IP:</strong> identifica um dispositivo em uma rede.</li>
  <li><strong>DNS:</strong> traduz nomes de domínio em endereços IP.</li>
  <li><strong>DHCP:</strong> distribui configurações de rede automaticamente.</li>
  <li><strong>Gateway:</strong> caminho de saída para outras redes.</li>
  <li><strong>TCP:</strong> comunicação orientada à conexão.</li>
  <li><strong>UDP:</strong> comunicação sem estabelecimento de conexão.</li>
  <li><strong>Porta:</strong> identifica um serviço ou aplicação no dispositivo.</li>
</ul>

<h2>2. Comandos para diagnóstico</h2>

<h3>Windows</h3>

<pre><code>ipconfig
ipconfig /all
ipconfig /release
ipconfig /renew
ipconfig /flushdns
ping 8.8.8.8
tracert google.com
nslookup google.com
netstat -ano</code></pre>

<h3>Linux</h3>

<pre><code>ip addr
ip route
ip neigh
ping -c 4 8.8.8.8
traceroute google.com
getent hosts google.com
ss -tuln</code></pre>

<h2>3. Para que serve cada comando?</h2>

<table>
  <thead>
    <tr><th>Comando</th><th>Finalidade</th></tr>
  </thead>
  <tbody>
    <tr><td><code>ipconfig /all</code></td><td>Exibe IP, gateway, DNS e outras configurações no Windows.</td></tr>
    <tr><td><code>ip addr</code></td><td>Exibe interfaces e endereços IP no Linux.</td></tr>
    <tr><td><code>ip route</code></td><td>Exibe a tabela de rotas.</td></tr>
    <tr><td><code>ping</code></td><td>Testa a conectividade usando ICMP.</td></tr>
    <tr><td><code>tracert</code> / <code>traceroute</code></td><td>Investiga o caminho até um destino.</td></tr>
    <tr><td><code>nslookup</code></td><td>Consulta informações de DNS.</td></tr>
    <tr><td><code>netstat -ano</code></td><td>Exibe conexões e portas no Windows.</td></tr>
    <tr><td><code>ss -tuln</code></td><td>Exibe sockets TCP/UDP em escuta no Linux.</td></tr>
  </tbody>
</table>

<h2>4. Macetes de troubleshooting</h2>

<ol>
  <li>Confira se a interface de rede está ativa.</li>
  <li>Verifique se o dispositivo recebeu um IP válido.</li>
  <li>Teste o gateway local.</li>
  <li>Teste um IP externo, como <code>8.8.8.8</code>.</li>
  <li>Teste um domínio, como <code>google.com</code>.</li>
  <li>Investigue DNS, rotas, firewall e portas conforme os resultados.</li>
</ol>

<p><strong>Macete:</strong> se um IP externo responde, mas um domínio não, investigue o DNS. Se nem o IP externo responde, isso pode indicar um problema de conectividade, rota ou bloqueio de ICMP — não necessariamente falta de internet.</p>

<h2>5. Portas comuns</h2>

<table>
  <thead><tr><th>Porta</th><th>Serviço</th></tr></thead>
  <tbody>
    <tr><td>22</td><td>SSH</td></tr>
    <tr><td>53</td><td>DNS</td></tr>
    <tr><td>80</td><td>HTTP</td></tr>
    <tr><td>443</td><td>HTTPS</td></tr>
    <tr><td>445</td><td>SMB</td></tr>
    <tr><td>3306</td><td>MySQL</td></tr>
    <tr><td>3389</td><td>RDP</td></tr>
    <tr><td>5432</td><td>PostgreSQL</td></tr>
    <tr><td>8080</td><td>HTTP alternativo, frequentemente usado em desenvolvimento</td></tr>
  </tbody>
</table>

<p><strong>Atenção:</strong> uma porta conhecida não garante que o serviço esteja ativo nela. Confirme por meio de testes autorizados.</p>
