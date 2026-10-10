# 💗 Linux

<h2>1. Navegação no terminal</h2>

<pre><code>pwd                 # Mostra o diretório atual
ls                  # Lista arquivos
ls -la              # Inclui arquivos ocultos e detalhes
cd pasta            # Entra em um diretório
cd ..               # Volta um nível
cd ~                # Vai para a pasta pessoal
clear               # Limpa a tela do terminal</code></pre>

<h2>2. Arquivos e diretórios</h2>

<pre><code>mkdir projetos              # Cria um diretório
touch notas.txt             # Cria um arquivo vazio
cat notas.txt               # Exibe o conteúdo
less notas.txt              # Exibe o conteúdo por páginas
cp arquivo.txt copia.txt    # Copia um arquivo
mv antigo.txt novo.txt      # Move ou renomeia
rm arquivo.txt              # Remove um arquivo
find . -name "notas.txt"    # Procura pelo nome
grep "erro" arquivo.log     # Procura um texto no arquivo</code></pre>

<p><strong>Cuidado:</strong> confira o caminho antes de executar comandos de remoção. O comando <code>rm -r</code> remove diretórios e seus conteúdos; evite executá-lo sem verificar exatamente o alvo.</p>

<h2>3. Permissões e usuários</h2>

<pre><code>whoami                   # Usuário atual
id                       # UID, GID e grupos
ls -l                    # Exibe permissões
chmod +x script.sh       # Permite executar o arquivo
sudo comando             # Executa um comando com privilégios elevados
sudo -l                  # Consulta comandos permitidos via sudo</code></pre>

<p><strong>Macete:</strong> não use <code>sudo</code> automaticamente. Entenda por que o comando precisa de privilégios administrativos.</p>

<h2>4. Processos e serviços</h2>

<pre><code>ps aux                   # Lista processos
top                      # Monitora processos
kill PID                 # Envia sinal para um processo
systemctl status docker  # Consulta um serviço
sudo systemctl start docker
sudo systemctl stop docker
journalctl -u docker     # Consulta logs do serviço</code></pre>

<h2>5. Rede no Linux</h2>

<pre><code>ip addr
ip route
ip neigh
ss -tuln
ping -c 4 8.8.8.8
getent hosts google.com
curl -I https://example.com</code></pre>

<h2>6. Compactação e leitura de logs</h2>

<pre><code>tar -czf backup.tar.gz pasta/
tar -xzf backup.tar.gz
head -n 20 arquivo.log
tail -n 50 arquivo.log
tail -f arquivo.log
grep -i "error" arquivo.log</code></pre>

<h2>7. Macetes de terminal</h2>

<ul>
  <li><code>Tab</code>: completa nomes de arquivos e comandos.</li>
  <li><code>↑</code>: recupera comandos anteriores.</li>
  <li><code>Ctrl + C</code>: interrompe um processo em primeiro plano.</li>
  <li><code>man comando</code>: abre o manual de um comando.</li>
  <li><code>comando --help</code>: consulta opções disponíveis.</li>
  <li><code>history</code>: exibe o histórico do terminal.</li>
  <li><code>|</code>: encaminha a saída de um comando para outro.</li>
  <li><code>&gt;</code>: redireciona a saída, sobrescrevendo o arquivo de destino.</li>
  <li><code>&gt;&gt;</code>: acrescenta a saída ao final do arquivo.</li>
</ul>

<h2>8. WSL e Docker no Windows</h2>

<pre><code>wsl --status
wsl --list --verbose
wsl --update
wsl --shutdown
docker ps
docker ps -a
docker logs NOME_DO_CONTAINER</code></pre>

<p><strong>Macete:</strong> no WSL, o Linux funciona dentro do Windows. O comando <code>wsl --shutdown</code> encerra as distribuições em execução; ele não apaga os arquivos delas.</p>
