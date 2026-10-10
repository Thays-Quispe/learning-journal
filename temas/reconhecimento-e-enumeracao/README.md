# 💗 Reconhecimento e Enumeração

<p>Etapas para descobrir informações sobre um alvo autorizado e identificar serviços disponíveis.</p>

<h2>1. Reconhecimento inicial</h2>

<pre><code>whois example.com
dig example.com
nslookup example.com
host example.com</code></pre>

<p>Esses comandos podem ajudar a consultar informações de domínio e DNS. Os resultados dependem dos registros disponíveis e das restrições do ambiente.</p>

<h2>2. Nmap — descoberta de serviços</h2>

<p>Utilize apenas em sistemas próprios ou com autorização explícita.</p>

<pre><code># Descobrir portas comuns
nmap 192.0.2.10

# Identificar versões de serviços
nmap -sV 192.0.2.10

# Verificar scripts padrão e versões
nmap -sC -sV 192.0.2.10

# Examinar portas específicas
nmap -p 22,80,443 192.0.2.10

# Salvar resultados em arquivo
nmap -sV -oN resultado.txt 192.0.2.10</code></pre>

<p><strong>Macete:</strong> não confunda uma porta aberta com uma vulnerabilidade confirmada. Primeiro identifique o serviço, a versão e o contexto.</p>

<h2>3. Enumeração de serviços em laboratório</h2>

<pre><code># Compartilhamentos SMB, em ambientes autorizados
enum4linux -a 192.0.2.10

# Consultar informações SNMP
snmpwalk -v2c -c public 192.0.2.10

# Consultar o serviço LDAP
ldapsearch -x -H ldap://192.0.2.10 -s base</code></pre>

<p><strong>Atenção:</strong> <code>public</code> é uma comunidade SNMP frequentemente usada em exemplos, mas não deve ser presumida como válida. Use somente credenciais e configurações fornecidas para o laboratório.</p>

<h2>4. Como interpretar os resultados</h2>

<ul>
  <li><strong>Porta aberta:</strong> há um serviço aceitando conexões naquela porta.</li>
  <li><strong>Porta fechada:</strong> o host respondeu, mas não há serviço escutando ali, conforme o teste.</li>
  <li><strong>Filtrada:</strong> um firewall ou outro mecanismo pode impedir determinar o estado.</li>
  <li><strong>Versão detectada:</strong> pista para investigar o software e sua configuração.</li>
  <li><strong>Enumeração:</strong> coleta de informações específicas de um serviço.</li>
</ul>

<h2>5. Fluxo de trabalho</h2>

<ol>
  <li>Definir o escopo autorizado.</li>
  <li>Identificar o alvo e confirmar conectividade.</li>
  <li>Descobrir portas e serviços.</li>
  <li>Enumerar os serviços relevantes.</li>
  <li>Registrar evidências e hipóteses.</li>
  <li>Validar achados sem ultrapassar o escopo.</li>
</ol>

<p><strong>Macete:</strong> mantenha anotações com IP, porta, serviço, versão, comando utilizado, resultado e próximo passo. Isso evita repetir testes sem necessidade.</p>
