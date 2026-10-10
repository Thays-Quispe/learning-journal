<h1>Docker & Ambientes de Laboratório</h1>

<p><strong>Módulo:</strong> Nivelamento<br>
<strong>Status:</strong> Concluído</p>

<hr>

<h3> Objetivo</h3>

<p>
  Aprender a identificar e resolver problemas comuns durante a configuração
  e utilização do Docker, incluindo falhas de inicialização, conflitos de
  portas, containers que não respondem e dificuldades para acessar aplicações
  vulneráveis em laboratórios.
</p>

<hr>

<h3>1. Docker Desktop não abre ou o daemon está inativo</h3>

<p><strong>Sintomas:</strong></p>

<ul>
  <li>O Docker Desktop não abre ou não termina de iniciar.</li>
  <li>O terminal exibe uma mensagem como <code>Cannot connect to the Docker daemon</code>.</li>
  <li>Os comandos Docker não conseguem se comunicar com o serviço.</li>
</ul>

<p><strong>Soluções:</strong></p>

<p><strong>Windows:</strong></p>

<ol>
  <li>Pesquise por <strong>Docker Desktop</strong> no menu Iniciar e execute o aplicativo.</li>
  <li>Aguarde a inicialização completa e verifique se o Docker está funcionando.</li>
  <li>Se estiver utilizando o mecanismo WSL 2, confira se o WSL está atualizado.</li>
</ol>

<p><strong>Linux:</strong></p>

<p>Em instalações que utilizam o Docker Engine como serviço, verifique o status:</p>

<pre><code>sudo systemctl status docker</code></pre>

<p>Se o serviço estiver parado, inicie-o:</p>

<pre><code>sudo systemctl start docker</code></pre>

<p>Para habilitar a inicialização automática:</p>

<pre><code>sudo systemctl enable docker</code></pre>

<p>
  <strong>Atenção:</strong> esses comandos são destinados a sistemas Linux com
  Docker Engine gerenciado pelo systemd. Eles não são a solução padrão para
  iniciar o Docker Desktop no Windows ou no macOS.
</p>

<p><strong>Erro de permissão no Linux:</strong></p>

<p>
  Se aparecer <code>permission denied</code>, verifique as permissões do usuário.
  Uma opção é adicionar o usuário ao grupo Docker:
</p>

<pre><code>sudo usermod -aG docker $USER</code></pre>

<p>
  Depois, encerre e inicie novamente a sessão para aplicar a alteração.
  O acesso ao grupo <code>docker</code> concede privilégios elevados, semelhantes
  aos de administrador, portanto só faça isso em um ambiente confiável.
</p>

<hr>

<h3>2. Erro de porta já em uso</h3>

<p><strong>Sintoma:</strong></p>

<p>
  O container não inicia porque a porta solicitada já está sendo utilizada
  por outro processo, como um servidor web local.
</p>

<p><strong>Solução:</strong></p>

<p>
  Altere a porta do host para outra que esteja disponível. O formato do
  parâmetro <code>-p</code> é:
</p>

<pre><code>-p PORTA_DO_HOST:PORTA_DO_CONTAINER</code></pre>

<p><strong>Exemplo:</strong></p>

<pre><code>docker run -d --name meu-nginx -p 8080:80 nginx</code></pre>

<p>Nesse exemplo:</p>

<ul>
  <li><code>8080</code>: porta acessada no computador.</li>
  <li><code>80</code>: porta utilizada pelo Nginx dentro do container.</li>
</ul>

<p>
  Para testar, abra
  <a href="http://localhost:8080">http://localhost:8080</a>
  no navegador.
</p>

<p><strong>Dica:</strong> se a porta 8080 também estiver ocupada, escolha outra porta livre, como 8081.</p>

<hr>

<h3>3. O container não inicia ou não responde</h3>

<p><strong>Sintomas:</strong></p>

<ul>
  <li>A aplicação não carrega no navegador.</li>
  <li>O container encerra logo após ser iniciado.</li>
  <li>O comando parece funcionar, mas o serviço não responde.</li>
</ul>

<p><strong>Passo 1 — Verificar o status</strong></p>

<p>Liste todos os containers, inclusive os que já pararam:</p>

<pre><code>docker ps -a</code></pre>

<p>Observe a coluna <code>STATUS</code> para identificar se o container está ativo ou encerrado.</p>

<p><strong>Passo 2 — Consultar os logs</strong></p>

<p>Os logs ajudam a descobrir por que a aplicação falhou:</p>

<pre><code>docker logs NOME_OU_ID_DO_CONTAINER</code></pre>

<p>Para acompanhar as mensagens em tempo real:</p>

<pre><code>docker logs -f NOME_OU_ID_DO_CONTAINER</code></pre>

<p><strong>🛠️ Passo 3 — Reiniciar o container</strong></p>

<pre><code>docker restart NOME_DO_CONTAINER</code></pre>

<p>
  Se o problema continuar, verifique os logs, as variáveis de ambiente,
  as portas configuradas e os arquivos necessários para a aplicação.
  Reiniciar não corrige, por si só, a causa do erro.
</p>

<p><strong>Comandos úteis:</strong></p>

<pre><code># Listar containers em execução
docker ps

# Listar todos os containers
docker ps -a

# Consultar logs
docker logs NOME_DO_CONTAINER

# Ver informações detalhadas
docker inspect NOME_DO_CONTAINER

# Parar um container
docker stop NOME_DO_CONTAINER</code></pre>

<hr>

<h3>4. O DVWA não aparece no navegador</h3>

<p>
  O <strong>DVWA (Damn Vulnerable Web Application)</strong> é uma aplicação web
  intencionalmente vulnerável, utilizada para praticar segurança de aplicações
  em um ambiente controlado.
</p>

<p><strong>Sintomas:</strong></p>

<ul>
  <li>A página não carrega.</li>
  <li>O navegador exibe um erro de conexão.</li>
  <li>A página retorna erro 404 ou fica em branco.</li>
</ul>

<p><strong>Passo 1 — Conferir a porta publicada</strong></p>

<p>
  A porta depende da imagem Docker e de como o container foi iniciado.
  Se a configuração publicada for <code>4280:80</code>, acesse:
</p>

<p>
  <a href="http://localhost:4280">http://localhost:4280</a>
</p>

<p>Para verificar o mapeamento de portas:</p>

<pre><code>docker ps</code></pre>

<p>
  Na coluna <code>PORTS</code>, procure uma entrada semelhante a
  <code>0.0.0.0:4280-&gt;80/tcp</code>.
</p>

<p><strong>Passo 2 — Conferir os logs do DVWA</strong></p>

<pre><code>docker logs NOME_DO_CONTAINER</code></pre>

<p>
  Confira também se o container está em execução e se a porta publicada
  corresponde à porta configurada na aplicação.
</p>

<p><strong>Passo 3 — Docker ou Linux em uma máquina virtual</strong></p>

<p>
  Se o laboratório estiver em uma máquina virtual, o endereço
  <code>localhost</code> normalmente aponta para o próprio ambiente em que
  o navegador está sendo executado.
</p>

<p>
  Para acessar a aplicação a partir do computador hospedeiro, pode ser
  necessário utilizar o IP da máquina virtual e configurar corretamente
  a rede e o encaminhamento de portas.
</p>

<p>Para consultar os endereços de rede no Linux:</p>

<pre><code>ip addr</code></pre>

<p>Se a rede e as portas permitirem, o acesso poderá seguir este formato:</p>

<pre><code>http://IP_DA_VM:4280</code></pre>

<p><strong>Passo 4 — Erro 404 em uma instalação manual</strong></p>

<p>
  Se o DVWA foi instalado diretamente em um servidor web, verifique se o
  caminho acessado corresponde ao nome real do diretório. No Linux, letras
  maiúsculas e minúsculas são diferentes.
</p>

<p>Por exemplo, se o diretório se chamar <code>DVWA</code>:</p>

<pre><code>http://localhost/DVWA</code></pre>

<p>
  Uma tela em branco pode estar relacionada a erros do PHP, configurações
  da aplicação ou problemas no servidor. Consulte os logs do Apache, do PHP
  e do próprio ambiente antes de alterar configurações.
</p>

<p><strong>Segurança:</strong> execute o DVWA somente em um laboratório controlado. Evite expor a aplicação vulnerável à internet ou a redes públicas.</p>

<hr>

<h3>5. Erros de virtualização no Windows</h3>

<p><strong>Sintomas:</strong></p>

<ul>
  <li>O Docker informa que a virtualização não está habilitada.</li>
  <li>O Docker Desktop não consegue iniciar o mecanismo baseado em WSL 2.</li>
  <li>O sistema apresenta erros relacionados ao Hyper-V ou ao WSL.</li>
</ul>

<p><strong>Passo 1 — Conferir a virtualização</strong></p>

<ol>
  <li>Abra o Gerenciador de Tarefas do Windows.</li>
  <li>Acesse a seção <strong>Desempenho</strong> e selecione <strong>CPU</strong>.</li>
  <li>Procure a informação <strong>Virtualização</strong>.</li>
</ol>

<p>
  Se estiver desabilitada, pode ser necessário ativar a tecnologia de
  virtualização na BIOS/UEFI. O nome da opção varia conforme o processador
  e o fabricante.
</p>

<ul>
  <li>Intel: Intel Virtualization Technology (VT-x).</li>
  <li>AMD: SVM Mode ou AMD-V.</li>
</ul>

<p><strong>Passo 2 — Verificar o WSL</strong></p>

<p>Abra o PowerShell e execute:</p>

<pre><code>wsl --status</code></pre>

<p>Para conferir as distribuições instaladas:</p>

<pre><code>wsl --list --verbose</code></pre>

<p>Se necessário, atualize o WSL:</p>

<pre><code>wsl --update</code></pre>

<p>
  Em caso de erro de permissão, abra o PowerShell como administrador.
  Depois, reinicie o Docker Desktop e verifique se o mecanismo WSL 2 está
  habilitado nas configurações do aplicativo.
</p>

<p><strong>Passo 3 — Reiniciar o WSL</strong></p>

<p>Se o WSL estiver travado, feche os trabalhos em andamento e execute:</p>

<pre><code>wsl --shutdown</code></pre>

<p>
  Esse comando encerra as distribuições WSL em execução. Em seguida, abra
  novamente o Docker Desktop e aguarde a inicialização.
</p>

<p><strong>Atenção:</strong> não é necessário habilitar todos os recursos de virtualização indiscriminadamente. Siga os requisitos da versão do Docker Desktop instalada e do mecanismo de virtualização escolhido.</p>

<hr>

<h3>6. Checklist de troubleshooting</h3>

<ul>
  <li>☐ O Docker Desktop ou o Docker Engine está em execução?</li>
  <li>☐ O comando <code>docker ps</code> funciona sem apresentar erros?</li>
  <li>☐ O container aparece em <code>docker ps -a</code>?</li>
  <li>☐ Os logs apresentam mensagens de erro?</li>
  <li>☐ A porta do host está livre e corretamente publicada?</li>
  <li>☐ Estou acessando o endereço e a porta corretos no navegador?</li>
  <li>☐ A virtualização e o WSL 2 estão configurados, quando necessários?</li>
  <li>☐ O laboratório está isolado e não expõe aplicações vulneráveis à internet?</li>
</ul>

<hr>

<h3>Resumo dos comandos</h3>

<table>
  <thead>
    <tr>
      <th>Comando</th>
      <th>Finalidade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>docker ps</code></td>
      <td>Lista containers em execução.</td>
    </tr>
    <tr>
      <td><code>docker ps -a</code></td>
      <td>Lista todos os containers, inclusive os parados.</td>
    </tr>
    <tr>
      <td><code>docker logs NOME</code></td>
      <td>Exibe os logs de um container.</td>
    </tr>
    <tr>
      <td><code>docker inspect NOME</code></td>
      <td>Mostra informações detalhadas do container.</td>
    </tr>
    <tr>
      <td><code>docker restart NOME</code></td>
      <td>Reinicia um container.</td>
    </tr>
    <tr>
      <td><code>docker run -p 8080:80 nginx</code></td>
      <td>Publica a porta 80 do container na porta 8080 do host.</td>
    </tr>
    <tr>
      <td><code>wsl --status</code></td>
      <td>Consulta o estado e as informações do WSL.</td>
    </tr>
    <tr>
      <td><code>wsl --update</code></td>
      <td>Atualiza o WSL.</td>
    </tr>
    <tr>
      <td><code>wsl --shutdown</code></td>
      <td>Encerra as distribuições WSL em execução.</td>
    </tr>
  </tbody>
</table>

<hr>

<h3>O que aprendi</h3>

<ul>
  <li>Identificar problemas de inicialização do Docker.</li>
  <li>Investigar containers parados por meio dos logs e do status.</li>
  <li>Resolver conflitos de portas alterando o mapeamento.</li>
  <li>Verificar configurações de rede e acesso ao DVWA.</li>
  <li>Entender a relação entre Docker Desktop, virtualização e WSL 2.</li>
  <li>Aplicar boas práticas de isolamento em laboratórios de cibersegurança.</li>
</ul>

<br>

  <a href="https://github.com/Thays-Quispe/learning-journal/blob/main/cursos/kodie/README.md">
    Voltar ao Nivelamento
  </a>
</p>
