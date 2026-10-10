
<h1>💗 Ferramentas e Ambiente de Desenvolvimento</h1>

<p>
  Comandos, configurações e soluções práticas para Linux, WSL,
  Git, GitHub, Docker e VS Code.
</p>


<h2>1. Linux — Terminal</h2>

<p>Comandos básicos para navegar pelo sistema e manipular arquivos.</p>

<table>
  <thead>
    <tr>
      <th>Comando</th>
      <th>Função</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><code>pwd</code></td><td>Mostra o diretório atual.</td></tr>
    <tr><td><code>ls</code></td><td>Lista arquivos e pastas.</td></tr>
    <tr><td><code>ls -la</code></td><td>Lista também arquivos ocultos e detalhes.</td></tr>
    <tr><td><code>cd nome-da-pasta</code></td><td>Entra em uma pasta.</td></tr>
    <tr><td><code>cd ..</code></td><td>Volta um nível na hierarquia.</td></tr>
    <tr><td><code>cd ~</code></td><td>Vai para o diretório pessoal.</td></tr>
    <tr><td><code>mkdir nome</code></td><td>Cria uma pasta.</td></tr>
    <tr><td><code>touch arquivo.txt</code></td><td>Cria um arquivo vazio, se ele não existir.</td></tr>
    <tr><td><code>cat arquivo.txt</code></td><td>Exibe o conteúdo de um arquivo.</td></tr>
    <tr><td><code>clear</code></td><td>Limpa a tela do terminal.</td></tr>
  </tbody>
</table>

<h3>Macetes</h3>

<table>
  <thead>
    <tr><th>Situação</th><th>Dica</th></tr>
  </thead>
  <tbody>
    <tr><td>Não sabe onde está</td><td>Execute <code>pwd</code>.</td></tr>
    <tr><td>Precisa ver os arquivos</td><td>Execute <code>ls -la</code>.</td></tr>
    <tr><td>Precisa completar um caminho</td><td>Use <code>Tab</code> no terminal.</td></tr>
    <tr><td>Precisa interromper um comando</td><td>Use <code>Ctrl + C</code>, quando apropriado.</td></tr>
  </tbody>
</table>

<br>


<h2>2. WSL — Windows Subsystem for Linux</h2>

<p>
  Permite executar distribuições Linux diretamente no Windows.
  Os comandos abaixo devem ser executados no PowerShell ou CMD.
</p>

<table>
  <thead>
    <tr><th>Comando</th><th>Função</th></tr>
  </thead>
  <tbody>
    <tr><td><code>wsl --status</code></td><td>Exibe informações sobre a configuração do WSL.</td></tr>
    <tr><td><code>wsl --list --verbose</code></td><td>Lista as distribuições instaladas, o estado e a versão do WSL.</td></tr>
    <tr><td><code>wsl --update</code></td><td>Atualiza o WSL.</td></tr>
    <tr><td><code>wsl --shutdown</code></td><td>Encerra todas as distribuições em execução.</td></tr>
    <tr><td><code>wsl</code></td><td>Abre a distribuição padrão.</td></tr>
    <tr><td><code>wsl -d Ubuntu</code></td><td>Abre a distribuição Ubuntu, se estiver instalada.</td></tr>
    <tr><td><code>wsl -d kali-linux</code></td><td>Abre a distribuição Kali Linux, se esse for o nome registrado no WSL.</td></tr>
  </tbody>
</table>

<h3>Macetes</h3>

<table>
  <thead>
    <tr><th>Problema</th><th>O que verificar</th></tr>
  </thead>
  <tbody>
    <tr><td>Distribuição não abre</td><td>Consulte <code>wsl --status</code> e <code>wsl --list --verbose</code>.</td></tr>
    <tr><td>Ambiente travado</td><td>Tente <code>wsl --shutdown</code> e abra o WSL novamente.</td></tr>
    <tr><td>Comando não funciona</td><td>Confira se está no PowerShell/CMD ou dentro do terminal Linux.</td></tr>
    <tr><td>WSL 1 ou WSL 2</td><td>Consulte a coluna VERSION de <code>wsl --list --verbose</code>.</td></tr>
    <tr><td>Não sabe o nome da distribuição</td><td>Execute <code>wsl --list --verbose</code> e copie o nome exibido.</td></tr>
  </tbody>
</table>

<p>
  <strong>Importante:</strong> os comandos <code>wsl</code> são executados
  no Windows. Comandos como <code>pwd</code>, <code>ls</code> e
  <code>cd</code> são executados dentro do Linux.
</p>

<br>

<h2>3. Git e GitHub</h2>

<p>O Git controla o histórico de alterações. O GitHub hospeda repositórios remotos.</p>

<h3>3.1. Configuração</h3>

<pre><code>git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"

# Conferir as configurações
git config --list</code></pre>

<h3>3.2. Comandos principais</h3>

<table>
  <thead>
    <tr><th>Comando</th><th>Função</th></tr>
  </thead>
  <tbody>
    <tr><td><code>git clone URL</code></td><td>Clona um repositório.</td></tr>
    <tr><td><code>git status</code></td><td>Mostra o estado das alterações.</td></tr>
    <tr><td><code>git add .</code></td><td>Prepara as alterações para o commit.</td></tr>
    <tr><td><code>git commit -m "Mensagem"</code></td><td>Registra as alterações no histórico local.</td></tr>
    <tr><td><code>git push</code></td><td>Envia commits para o repositório remoto configurado.</td></tr>
    <tr><td><code>git log</code></td><td>Exibe o histórico de commits.</td></tr>
    <tr><td><code>git log --oneline</code></td><td>Exibe o histórico em formato resumido.</td></tr>
    <tr><td><code>git remote -v</code></td><td>Mostra os repositórios remotos configurados.</td></tr>
  </tbody>
</table>

<h3>3.3. Fluxo de trabalho</h3>

<pre><code># 1. Conferir as alterações
git status

# 2. Preparar os arquivos
git add .

# 3. Criar um commit
git commit -m "Atualiza anotações"

# 4. Enviar para o GitHub
git push</code></pre>

<h3>3.4. Correções e recuperação</h3>

<table>
  <thead>
    <tr><th>Comando</th><th>Quando usar</th></tr>
  </thead>
  <tbody>
    <tr><td><code>git remote -v</code></td><td>Verificar se o remoto está configurado.</td></tr>
    <tr><td><code>git remote add origin URL</code></td><td>Adicionar um remoto chamado origin.</td></tr>
    <tr><td><code>git push -u origin main</code></td><td>Enviar a branch main e configurar seu upstream.</td></tr>
    <tr><td><code>git reset --soft HEAD~1</code></td><td>Desfazer o último commit, mantendo as alterações preparadas.</td></tr>
    <tr><td><code>git revert HEAD</code></td><td>Criar um novo commit que reverte o último commit.</td></tr>
  </tbody>
</table>

<h3>Macetes</h3>

<table>
  <thead>
    <tr><th>Comando</th><th>O que lembrar</th></tr>
  </thead>
  <tbody>
    <tr><td><code>git status</code></td><td>Ajuda a identificar o que mudou e o que ainda precisa ser enviado.</td></tr>
    <tr><td><code>git add .</code></td><td>Prepara alterações; não cria commit nem envia arquivos.</td></tr>
    <tr><td><code>git commit</code></td><td>Registra as alterações localmente.</td></tr>
    <tr><td><code>git push</code></td><td>Envia os commits ao remoto.</td></tr>
    <tr><td><code>git reset --hard</code></td><td>Pode descartar alterações locais. Não use sem entender as consequências.</td></tr>
  </tbody>
</table>

<br>


<h2>4. Docker</h2>

<p>
  O Docker executa aplicações em containers. Nos laboratórios,
  ajuda a iniciar serviços e ambientes de prática.
</p>

<h3>4.1. Verificação e consulta</h3>

<table>
  <thead>
    <tr><th>Comando</th><th>Função</th></tr>
  </thead>
  <tbody>
    <tr><td><code>docker --version</code></td><td>Mostra a versão do Docker CLI.</td></tr>
    <tr><td><code>docker info</code></td><td>Exibe informações do ambiente Docker.</td></tr>
    <tr><td><code>docker ps</code></td><td>Lista containers em execução.</td></tr>
    <tr><td><code>docker ps -a</code></td><td>Lista containers em qualquer estado.</td></tr>
    <tr><td><code>docker images</code></td><td>Lista imagens disponíveis localmente.</td></tr>
  </tbody>
</table>

<h3>4.2. Executar um container</h3>

<pre><code># Executar o Nginx em segundo plano
docker run -d --name meu-nginx -p 8080:80 nginx

# Verificar se está em execução
docker ps

# Acessar pelo navegador
http://localhost:8080</code></pre>

<p>
  No exemplo, a porta 8080 do computador é direcionada para a porta 80
  do container.
</p>

<h3>4.3. Parar, iniciar e excluir containers</h3>

<table>
  <thead>
    <tr><th>Comando</th><th>Função</th></tr>
  </thead>
  <tbody>
    <tr><td><code>docker stop meu-nginx</code></td><td>Para o container em execução.</td></tr>
    <tr><td><code>docker start meu-nginx</code></td><td>Inicia novamente um container parado.</td></tr>
    <tr><td><code>docker restart meu-nginx</code></td><td>Reinicia o container.</td></tr>
    <tr><td><code>docker rm meu-nginx</code></td><td>Remove um container parado.</td></tr>
    <tr><td><code>docker rm -f meu-nginx</code></td><td>Força a remoção do container, inclusive se estiver em execução.</td></tr>
    <tr><td><code>docker container prune</code></td><td>Remove todos os containers parados após confirmação.</td></tr>
  </tbody>
</table>

<h3>4.4. Logs e diagnóstico</h3>

<table>
  <thead>
    <tr><th>Comando</th><th>Função</th></tr>
  </thead>
  <tbody>
    <tr><td><code>docker logs meu-nginx</code></td><td>Exibe os logs do container.</td></tr>
    <tr><td><code>docker logs -f meu-nginx</code></td><td>Acompanha os logs em tempo real; use Ctrl + C para sair da visualização.</td></tr>
    <tr><td><code>docker inspect meu-nginx</code></td><td>Exibe configurações e detalhes do container.</td></tr>
    <tr><td><code>docker top meu-nginx</code></td><td>Exibe os processos do container.</td></tr>
    <tr><td><code>docker ps -a</code></td><td>Ajuda a encontrar containers parados ou com falha.</td></tr>
  </tbody>
</table>

<h3>Macetes</h3>

<table>
  <thead>
    <tr><th>Situação</th><th>O que fazer</th></tr>
  </thead>
  <tbody>
    <tr><td>Quero parar o laboratório</td><td>Use <code>docker stop NOME</code>.</td></tr>
    <tr><td>Quero continuar de onde parei</td><td>Use <code>docker start NOME</code>.</td></tr>
    <tr><td>Quero apagar o container</td><td>Use <code>docker stop NOME</code> e depois <code>docker rm NOME</code>.</td></tr>
    <tr><td>O container não aparece no <code>docker ps</code></td><td>Confira <code>docker ps -a</code>.</td></tr>
    <tr><td>O container iniciou e parou</td><td>Consulte <code>docker logs NOME</code>.</td></tr>
    <tr><td>A porta já está ocupada</td><td>Verifique o processo que utiliza a porta ou escolha outra porta local livre.</td></tr>
    <tr><td>O laboratório não abre no navegador</td><td>Confira o estado do container, o mapeamento de portas e o endereço utilizado.</td></tr>
  </tbody>
</table>

<p>
  <strong>Atenção:</strong> parar um container não o exclui.
  Remover um container também não exclui automaticamente a imagem
  utilizada para criá-lo.
</p>

<p>
  Se o mapeamento for <code>-p 4280:80</code>, o endereço local será
  <code>http://localhost:4280</code>.
</p>

<h2>5. Diagnóstico rápido</h2>

<table>
  <thead>
    <tr><th>Erro ou situação</th><th>Primeiro passo</th></tr>
  </thead>
  <tbody>
    <tr><td>Comando não encontrado</td><td>Confira a grafia, a instalação e o ambiente atual.</td></tr>
    <tr><td>Permissão negada</td><td>Verifique as permissões do arquivo ou recurso.</td></tr>
    <tr><td>Docker não inicia</td><td>Confira o serviço e consulte <code>docker ps -a</code>.</td></tr>
    <tr><td>Site do laboratório não abre</td><td>Verifique o container, a porta mapeada e o endereço acessado.</td></tr>
    <tr><td>Git não envia alterações</td><td>Confira <code>git status</code>, <code>git remote -v</code> e a branch atual.</td></tr>
    <tr><td>WSL apresenta problemas</td><td>Consulte <code>wsl --status</code> e <code>wsl --list --verbose</code>.</td></tr>
  </tbody>
</table>

<br>


