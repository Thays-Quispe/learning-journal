<h1>Introdução ao Terminal e Ambiente Linux</h1>

<p><strong>Módulo:</strong> Nivelamento<br>
<strong>Status:</strong> Concluído</p>

<hr>

<h2>1. Terminal e Linha de Comando</h2>

<p>O terminal permite interagir com o sistema operacional por meio de comandos digitados. Também é conhecido como linha de comando (CLI) e pode ser utilizado para navegar por arquivos, executar programas e administrar sistemas.</p>

<p>Essa ferramenta é bastante utilizada em desenvolvimento de software, administração de sistemas e cibersegurança.</p>

<hr>

<h2>2. WSL2 — Linux no Windows</h2>

<p>O WSL2 permite executar um ambiente Linux diretamente no Windows, utilizando um kernel Linux real em uma máquina virtual leve integrada ao Hyper-V.</p>

<h3>Como funciona</h3>

<ul>
  <li>Permite executar comandos Linux sem instalar outro sistema operacional em uma partição separada.</li>
  <li>Utiliza virtualização para executar o ambiente Linux dentro do Windows.</li>
  <li>Facilita o acesso a ferramentas utilizadas em desenvolvimento e cibersegurança.</li>
</ul>

<h3>Comando de instalação</h3>

<p>O comando abaixo pode ser executado no PowerShell como administrador:</p>

<pre><code>wsl --install</code></pre>

<p>Ele instala o WSL e uma distribuição Linux padrão. Pode ser necessário reiniciar o computador.</p>

<hr>

<h2>3. Kali Linux</h2>

<p>O Kali Linux é uma distribuição baseada no Debian, desenvolvida para atividades de cibersegurança, como testes de segurança, análise de redes e perícia digital.</p>

<h3>Principais utilizações</h3>

<ul>
  <li><strong>Pentest:</strong> testes autorizados para identificar vulnerabilidades.</li>
  <li><strong>Análise de redes:</strong> investigação da comunicação entre dispositivos.</li>
  <li><strong>Perícia digital:</strong> análise de informações e evidências digitais.</li>
  <li><strong>CTF:</strong> resolução de desafios práticos de segurança.</li>
</ul>

<p>O Kali Linux pode ser instalado diretamente no computador, executado pelo WSL ou iniciado por um pendrive USB.</p>

<h3>Exemplos de ferramentas</h3>

<ul>
  <li><strong>Nmap:</strong> identifica dispositivos e serviços disponíveis em uma rede.</li>
  <li><strong>Metasploit:</strong> auxilia nos testes de exploração de vulnerabilidades.</li>
  <li><strong>Wireshark:</strong> permite analisar pacotes e tráfego de rede.</li>
</ul>

<hr>

<h2>4. Sistema de Arquivos Linux</h2>

<p>O Linux organiza arquivos e diretórios em uma estrutura hierárquica que começa na raiz <code>/</code>. Diferentemente do Windows, que utiliza letras como <code>C:\</code>, o Linux organiza seus diretórios a partir de um único ponto inicial.</p>

<h3>Principais diretórios</h3>

<ul>
  <li><strong><code>/home</code>:</strong> armazena os arquivos pessoais dos usuários.</li>
  <li><strong><code>/etc</code>:</strong> contém arquivos de configuração do sistema.</li>
  <li><strong><code>/var</code>:</strong> armazena dados variáveis, como logs.</li>
  <li><strong><code>/usr</code>:</strong> reúne programas, bibliotecas e arquivos compartilhados.</li>
  <li><strong><code>/bin</code>:</strong> contém comandos básicos do sistema.</li>
  <li><strong><code>/sbin</code>:</strong> reúne ferramentas administrativas.</li>
  <li><strong><code>/tmp</code>:</strong> armazena arquivos temporários.</li>
  <li><strong><code>/proc</code>:</strong> disponibiliza informações sobre processos e o kernel.</li>
  <li><strong><code>/dev</code>:</strong> contém arquivos que representam dispositivos.</li>
  <li><strong><code>/mnt</code>:</strong> pode ser utilizado como ponto de montagem de outros sistemas de arquivos.</li>
</ul>

<p>No WSL, os arquivos do Windows podem ser acessados por caminhos como <code>/mnt/c/</code>.</p>

<hr>

<h2>5. Comandos Básicos do Linux</h2>

<p>Os comandos básicos permitem navegar pelos diretórios e consultar arquivos utilizando o terminal.</p>

<ul>
  <li><strong><code>pwd</code>:</strong> exibe o caminho do diretório atual.</li>
  <li><strong><code>ls</code>:</strong> lista arquivos e diretórios.</li>
  <li><strong><code>cd</code>:</strong> permite navegar entre diretórios.</li>
  <li><strong><code>cd ..</code>:</strong> retorna um nível na hierarquia.</li>
  <li><strong><code>cd /</code>:</strong> acessa o diretório raiz.</li>
  <li><strong><code>cd ~</code>:</strong> acessa o diretório pessoal do usuário.</li>
  <li><strong><code>ls -l</code>:</strong> exibe os arquivos em formato detalhado.</li>
  <li><strong><code>ls -A</code>:</strong> também exibe arquivos ocultos, exceto <code>.</code> e <code>..</code>.</li>
</ul>

<h3>Exemplos práticos</h3>

<p>Consultar o diretório atual:</p>

<pre><code>pwd</code></pre>

<p>Listar arquivos e diretórios:</p>

<pre><code>ls</code></pre>

<p>Acessar o diretório Downloads:</p>

<pre><code>cd Downloads</code></pre>

<p>Voltar um nível na hierarquia:</p>

<pre><code>cd ..</code></pre>

<p>Acessar a raiz do sistema:</p>

<pre><code>cd /</code></pre>

<p>Listar arquivos, incluindo os ocultos:</p>

<pre><code>ls -A</code></pre>

<hr>

<p><a href="https://github.com/Thays-Quispe/learning-journal/blob/main/cursos/kodie/README.md">Voltar ao Nivelamento</a></p>
