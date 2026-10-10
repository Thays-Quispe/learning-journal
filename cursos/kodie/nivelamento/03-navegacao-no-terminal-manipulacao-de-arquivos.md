<h1>Navegação no Terminal &amp; Manipulação de Arquivos</h1>

<p><strong>Módulo:</strong> Nivelamento<br>
<strong>Status:</strong> Concluído</p>

<hr>

<h2>1. Terminal e Linha de Comando</h2>

<p>O terminal permite interagir com o sistema operacional por meio de comandos digitados. Também é conhecido como console, prompt de comando ou CLI (<em>Command-Line Interface</em>).</p>

<p>Antigamente, os terminais eram dispositivos físicos utilizados para acessar computadores. Hoje, são principalmente programas que permitem enviar instruções diretamente ao sistema operacional.</p>

<p>A linha de comando pode tornar algumas tarefas mais rápidas e é muito utilizada na administração de servidores, no desenvolvimento de software e na cibersegurança.</p>

<h3>Bash</h3>

<p>O Bash é um interpretador de comandos bastante utilizado em sistemas GNU/Linux. Ele permite executar comandos, navegar por diretórios e automatizar tarefas.</p>

<hr>

<h2>2. Navegação no Sistema de Arquivos Linux</h2>

<p>O Linux organiza seus arquivos em uma estrutura de árvore que começa no diretório raiz, representado por <code>/</code>. Diferentemente do Windows, que utiliza letras como <code>C:\</code>, o Linux utiliza um único ponto de partida para seus diretórios.</p>

<h3>Principais diretórios</h3>

<ul>
<li><strong><code>/home</code>:</strong> armazena os arquivos pessoais dos usuários.</li>
<li><strong><code>/etc</code>:</strong> contém arquivos de configuração do sistema.</li>
<li><strong><code>/var</code>:</strong> armazena dados variáveis, como logs.</li>
<li><strong><code>/bin</code>:</strong> contém comandos e utilitários básicos do sistema.</li>
<li><strong><code>/tmp</code>:</strong> armazena arquivos temporários, que podem ser removidos pelo sistema.</li>
</ul>

<h3>Comandos essenciais</h3>

<table>
<thead>
<tr>
<th>Comando</th>
<th>Função</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>pwd</code></td>
<td>Exibe o caminho do diretório atual.</td>
</tr>
<tr>
<td><code>ls</code></td>
<td>Lista arquivos e diretórios.</td>
</tr>
<tr>
<td><code>ls -l</code></td>
<td>Exibe detalhes dos arquivos, como permissões, proprietário e tamanho.</td>
</tr>
<tr>
<td><code>ls -a</code></td>
<td>Exibe também os arquivos ocultos.</td>
</tr>
<tr>
<td><code>ls -h</code></td>
<td>Exibe tamanhos em formato legível quando combinado com opções como <code>-l</code>.</td>
</tr>
<tr>
<td><code>cd</code></td>
<td>Permite mudar de diretório.</td>
</tr>
<tr>
<td><code>cd ..</code></td>
<td>Sobe um nível na hierarquia de diretórios.</td>
</tr>
<tr>
<td><code>cd ../..</code></td>
<td>Sobe dois níveis na hierarquia.</td>
</tr>
<tr>
<td><code>cd /</code></td>
<td>Acessa o diretório raiz.</td>
</tr>
<tr>
<td><code>echo</code></td>
<td>Exibe um texto ou o valor de uma variável no terminal.</td>
</tr>
<tr>
<td><code>grep</code></td>
<td>Busca palavras ou padrões em textos e arquivos.</td>
</tr>
</tbody>
</table>

<h3>Exemplos práticos</h3>

<p>Verificar o diretório atual:</p>

<pre><code>pwd</code></pre>

<p>Listar arquivos e diretórios:</p>

<pre><code>ls</code></pre>

<p>Exibir detalhes dos arquivos:</p>

<pre><code>ls -l</code></pre>

<p>Voltar um nível:</p>

<pre><code>cd ..</code></pre>

<p>Exibir uma mensagem no terminal:</p>

<pre><code>echo "Olá, Linux!"</code></pre>

<p>Buscar uma palavra em um arquivo:</p>

<pre><code>grep "erro" sistema.log</code></pre>

<hr>

<h2>3. Permissões e Acesso</h2>

<p>O Linux utiliza permissões para controlar quais ações os usuários podem realizar sobre arquivos e diretórios.</p>

<ul>
<li><strong>r (Read):</strong> permissão de leitura.</li>
<li><strong>w (Write):</strong> permissão de escrita ou alteração.</li>
<li><strong>x (Execute):</strong> permissão de execução.</li>
</ul>

<p>Em alguns terminais, o caractere <code>#</code> no prompt pode indicar que a sessão está sendo executada como <code>root</code>, o usuário administrador do sistema. O significado exato depende da configuração do terminal.</p>

<hr>

<h2>4. Função Hash</h2>

<p>Uma função hash transforma dados de qualquer tamanho em um resultado de comprimento definido, chamado hash. Esse resultado funciona como uma espécie de impressão digital dos dados.</p>

<p>Se um arquivo sofrer uma pequena alteração, o hash gerado por um algoritmo criptográfico adequado, como SHA-256, normalmente será completamente diferente.</p>

<p>As funções hash são utilizadas para verificar a integridade de arquivos, comparar dados e apoiar mecanismos de segurança digital. Elas não são um método de criptografia reversível.</p>

<hr>

<h2>5. WSL2 — Linux no Windows</h2>

<p>O WSL permite executar ambientes Linux diretamente no Windows, sem a necessidade de configurar um sistema em dual boot.</p>

<p>O WSL2 utiliza um kernel Linux real em uma máquina virtual leve baseada em tecnologias de virtualização do Windows, oferecendo ampla compatibilidade com ferramentas e aplicações Linux.</p>

<h3>Comando de instalação</h3>

<p>No PowerShell, executado como administrador, utilize:</p>

<pre><code>wsl --install</code></pre>

<p>O comando instala os componentes necessários do WSL e uma distribuição Linux padrão, geralmente o Ubuntu. Pode ser necessário reiniciar o computador.</p>

<hr>

<h2>6. Kali Linux e Segurança Ofensiva</h2>

<p>O Kali Linux é uma distribuição baseada no Debian, mantida pela Offensive Security e desenvolvida para testes de segurança e perícia digital.</p>

<h3>Principais ferramentas</h3>

<ul>
<li><strong>Nmap:</strong> identifica dispositivos e serviços em uma rede.</li>
<li><strong>Metasploit:</strong> auxilia na realização de testes de exploração de vulnerabilidades.</li>
<li><strong>Wireshark:</strong> permite analisar pacotes e tráfego de rede.</li>
</ul>

<p>O Kali Linux pode ser executado diretamente no computador, pelo WSL, em dispositivos compatíveis ou por um pendrive no modo Live Boot.</p>

<p>É utilizado em laboratórios de estudo, desafios CTF (<em>Capture The Flag</em>), auditorias e testes de intrusão autorizados.</p>

<hr>

<p><a href="https://github.com/Thays-Quispe/learning-journal/blob/main/cursos/kodie/README.md">Voltar ao Nivelamento</a></p>
