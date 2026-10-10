
<h1>VS Code, Git &amp; Organização Técnica</h1>

<p><strong>Módulo:</strong> Nivelamento<br>
<strong>Status:</strong> Concluído</p>

<hr>

<h2>1. O que é o VS Code?</h2>

<p>O Visual Studio Code (VS Code) é um editor de código-fonte utilizado para escrever, editar e organizar arquivos de diferentes linguagens de programação.</p>

<p>Ele oferece recursos como:</p>

<ul>
<li>Realce de sintaxe para facilitar a leitura do código.</li>
<li>Terminal integrado para executar comandos.</li>
<li>Extensões para diferentes linguagens e ferramentas.</li>
<li>Integração com Git para acompanhar alterações nos arquivos.</li>
<li>Depuração de aplicações com ferramentas e extensões compatíveis.</li>
</ul>

<hr>

<h2>2. O que é Git?</h2>

<p>O Git é um sistema de controle de versão distribuído que registra as alterações feitas nos arquivos de um projeto ao longo do tempo.</p>

<p>Ele permite acompanhar o histórico, comparar versões, criar ramificações e colaborar com outras pessoas no desenvolvimento de software.</p>

<h3>Git vs. GitHub</h3>

<ul>
<li><strong>Git:</strong> ferramenta de controle de versão que pode funcionar localmente no computador.</li>
<li><strong>GitHub:</strong> plataforma que hospeda repositórios Git e oferece recursos de colaboração, como pull requests e revisão de código.</li>
</ul>

<p>O Git pode ser utilizado sem o GitHub, mas conectar um repositório local a uma plataforma remota facilita o backup e a colaboração.</p>

<hr>

<h2>3. Os principais comandos do Git</h2>

<h3>1. git config — Configurar a identidade</h3>

<p><strong>O que faz:</strong> configura preferências do Git, incluindo o nome e o e-mail associados aos commits.</p>

<p><strong>Configurar o nome:</strong></p>

<pre><code>git config --global user.name "Seu Nome"</code></pre>

<p><strong>Configurar o e-mail:</strong></p>

<pre><code>git config --global user.email "seuemail@exemplo.com"</code></pre>

<p>A opção <code>--global</code> aplica a configuração ao usuário do sistema. Um repositório específico também pode ter suas próprias configurações.</p>

<h3>2. git clone — Clonar um repositório</h3>

<p><strong>O que faz:</strong> cria uma cópia local de um repositório remoto, incluindo seu histórico de versões.</p>

<pre><code>git clone https://github.com/username/meu-projeto.git</code></pre>

<p>Esse comando é útil quando você deseja baixar para o computador um projeto que já existe no GitHub.</p>

<h3>3. git add — Preparar alterações</h3>

<p><strong>O que faz:</strong> adiciona alterações à área de preparação, chamada <em>staging area</em> ou <em>stage</em>, para que possam fazer parte do próximo commit.</p>

<pre><code>git add README.md</code></pre>

<p>Para preparar todas as alterações existentes no diretório atual e em seus subdiretórios:</p>

<pre><code>git add .</code></pre>

<p>O comando <code>git add</code> não cria um commit. Ele apenas prepara as alterações que serão registradas posteriormente.</p>

<h3>4. git commit — Registrar alterações</h3>

<p><strong>O que faz:</strong> cria um registro das alterações preparadas no histórico do repositório local.</p>

<pre><code>git commit -m "Adicionar novo recurso"</code></pre>

<p>Utilize mensagens curtas e descritivas para facilitar a compreensão do histórico do projeto.</p>

<h3>5. git push — Enviar commits</h3>

<p><strong>O que faz:</strong> envia commits do repositório local para um repositório remoto, como o GitHub.</p>

<pre><code>git push origin main</code></pre>

<p>Nesse exemplo:</p>

<ul>
<li><code>origin</code> é o nome convencional do repositório remoto.</li>
<li><code>main</code> é o nome da branch que será enviada.</li>
</ul>

<p>O nome da branch pode ser diferente, como <code>master</code> ou <code>develop</code>, dependendo do projeto.</p>

<h3>6. git status — Verificar o estado do repositório</h3>

<p><strong>O que faz:</strong> mostra quais arquivos foram modificados, quais são novos e quais alterações estão preparadas para commit.</p>

<pre><code>git status</code></pre>

<p>É uma boa prática executar esse comando antes de preparar alterações e antes de criar um commit.</p>

<h3>7. git log — Consultar o histórico</h3>

<p><strong>O que faz:</strong> exibe o histórico de commits do repositório.</p>

<pre><code>git log</code></pre>

<p>Para visualizar o histórico de forma resumida:</p>

<pre><code>git log --oneline</code></pre>

<p>Esses comandos ajudam a identificar o que foi registrado e quando cada versão foi criada.</p>

<hr>

<h2>4. Fluxo básico de trabalho com Git</h2>

<p>Em um projeto já configurado, o fluxo mais comum para registrar e enviar alterações é:</p>

<ol>
<li><strong>Verificar:</strong> conferir as alterações com <code>git status</code>.</li>
<li><strong>Preparar:</strong> adicionar os arquivos com <code>git add</code>.</li>
<li><strong>Registrar:</strong> criar um commit com <code>git commit</code>.</li>
<li><strong>Enviar:</strong> compartilhar os commits com <code>git push</code>.</li>
</ol>

<h3>Exemplo completo</h3>

<pre><code>git status
git add README.md
git commit -m "Atualizar documentação"
git push origin main</code></pre>

<p>Esse exemplo pressupõe que o repositório já esteja configurado com um remoto chamado <code>origin</code> e que a branch atual seja <code>main</code>.</p>

<hr>

<h2>5. Erros comuns do Git e como resolvê-los</h2>

<h3>Erro 1 — Tentar fazer commit sem adicionar arquivos novos</h3>

<p><strong>Problema:</strong> você criou um arquivo, mas ainda não o adicionou à área de preparação. O Git não o inclui automaticamente no commit.</p>

<p>O <code>git status</code> pode apresentar uma mensagem semelhante a:</p>

<pre><code>nothing added to commit but untracked files present
(use "git add" to track)</code></pre>

<p><strong>Como resolver:</strong></p>

<pre><code>git add README.md
git commit -m "Adicionar README"</code></pre>

<p>Substitua <code>README.md</code> pelo nome do arquivo que deseja preparar.</p>

<h3>Erro 2 — Esquecer um arquivo no último commit</h3>

<p><strong>Problema:</strong> você criou um commit e percebeu que deixou de incluir um arquivo importante.</p>

<p><strong>Como resolver:</strong> se deseja incorporar o arquivo ao último commit, adicione-o ao stage e utilize:</p>

<pre><code>git add arquivo.txt
git commit --amend</code></pre>

<p>O Git permitirá editar a mensagem do commit. Para reutilizar a mensagem atual sem abrir o editor:</p>

<pre><code>git commit --amend --no-edit</code></pre>

<p><strong>Atenção:</strong> o <code>--amend</code> substitui o commit anterior por outro. Evite alterar commits que já foram compartilhados, pois isso pode causar divergências no histórico dos colaboradores.</p>

<h3>Erro 3 — Precisar desfazer um commit</h3>

<p><strong>Problema:</strong> você registrou alterações incorretas e precisa corrigir o histórico.</p>

<p><strong>Opção A — Desfazer o último commit mantendo as alterações preparadas:</strong></p>

<pre><code>git reset --soft HEAD~1</code></pre>

<p>O commit deixa de ser o último registro da branch, mas as alterações permanecem na área de preparação.</p>

<p><strong>Opção B — Desfazer o último commit e descartar as alterações correspondentes:</strong></p>

<pre><code>git reset --hard HEAD~1</code></pre>

<p><strong>Atenção:</strong> o <code>git reset --hard</code> pode descartar alterações locais e causar perda de trabalho. Antes de utilizá-lo, verifique o estado do repositório e faça uma cópia de segurança quando necessário.</p>

<p>Se o commit já foi enviado ao GitHub ou compartilhado com outras pessoas, avalie utilizar <code>git revert</code>, que cria um novo commit para desfazer as alterações anteriores sem reescrever o histórico compartilhado.</p>

<pre><code>git revert HEAD</code></pre>

<h3>Erro 4 — Conflitos ao juntar alterações (Merge Conflicts)</h3>

<p><strong>Problema:</strong> duas alterações incompatíveis foram feitas na mesma parte de um arquivo, e o Git não consegue decidir automaticamente qual versão manter.</p>

<p>Isso pode acontecer durante operações como <code>git merge</code> ou <code>git pull</code>.</p>

<p><strong>Como resolver:</strong></p>

<ol>
<li>Execute <code>git status</code> para identificar os arquivos em conflito.</li>
<li>Abra os arquivos no VS Code.</li>
<li>Analise as opções apresentadas pelo editor: manter a alteração atual, aceitar a recebida ou combinar as duas.</li>
<li>Revise o conteúdo final e remova os marcadores de conflito.</li>
<li>Adicione os arquivos resolvidos ao stage e finalize a operação conforme o Git solicitar.</li>
</ol>

<pre><code>git status
git add arquivo-em-conflito.txt
git commit</code></pre>

<p>O último comando é aplicável quando a operação de merge precisa ser concluída com um commit. Em outras operações, siga as instruções exibidas pelo Git.</p>

<p>Também existe o comando <code>git mergetool</code>, que pode abrir uma ferramenta visual de resolução de conflitos, desde que esteja configurada.</p>

<h3>Erro 5 — Tentar fazer push sem configurar um repositório remoto</h3>

<p><strong>Problema:</strong> você criou um repositório local com <code>git init</code>, mas não informou para onde os commits devem ser enviados.</p>

<p><strong>Como resolver:</strong> adicione o endereço do repositório remoto:</p>

<pre><code>git remote add origin https://github.com/username/meu-projeto.git</code></pre>

<p>Depois, confira o nome da branch atual:</p>

<pre><code>git branch --show-current</code></pre>

<p>Se a branch se chamar <code>main</code>, envie os commits com:</p>

<pre><code>git push -u origin main</code></pre>

<p>A opção <code>-u</code> configura a branch remota como referência padrão para os próximos comandos de push e pull.</p>

<p>Se o repositório remoto já tiver arquivos ou commits que não existem localmente, pode ser necessário sincronizar os históricos antes do primeiro envio. Não force o push sem compreender a situação, pois isso pode sobrescrever histórico compartilhado.</p>

<hr>

<h2>6. Organização Técnica dos Projetos</h2>

<p>Organizar um projeto facilita sua manutenção, a colaboração e a apresentação do trabalho em um portfólio.</p>

<h3>Boas práticas</h3>

<ul>
<li>Utilize nomes de arquivos e pastas claros.</li>
<li>Organize o código, a documentação e os testes em locais apropriados.</li>
<li>Escreva mensagens de commit objetivas.</li>
<li>Atualize o README com a descrição e as instruções de execução do projeto.</li>
<li>Evite enviar senhas, tokens, chaves privadas ou outras informações secretas para o GitHub.</li>
<li>Utilize um arquivo <code>.gitignore</code> para excluir arquivos que não devem ser versionados.</li>
<li>Faça commits pequenos e coerentes sempre que possível.</li>
</ul>

<h3>Exemplo de estrutura</h3>

<pre><code>meu-projeto/
├── README.md
├── .gitignore
├── src/
├── tests/
└── docs/</code></pre>

<p>Essa é apenas uma estrutura ilustrativa. A organização ideal depende da linguagem, do framework e das necessidades do projeto.</p>

<hr>

<h2>7. Resumo para Revisão</h2>

<table>
<thead>
<tr>
<th>Comando</th>
<th>Função</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>git config</code></td>
<td>Configura preferências e identidade do Git.</td>
</tr>
<tr>
<td><code>git clone</code></td>
<td>Clona um repositório remoto.</td>
</tr>
<tr>
<td><code>git add</code></td>
<td>Prepara alterações para o próximo commit.</td>
</tr>
<tr>
<td><code>git commit</code></td>
<td>Registra alterações no histórico local.</td>
</tr>
<tr>
<td><code>git push</code></td>
<td>Envia commits para um repositório remoto.</td>
</tr>
<tr>
<td><code>git status</code></td>
<td>Mostra o estado atual do repositório.</td>
</tr>
<tr>
<td><code>git log</code></td>
<td>Exibe o histórico de commits.</td>
</tr>
<tr>
<td><code>git revert</code></td>
<td>Cria um novo commit que desfaz alterações anteriores.</td>
</tr>
<tr>
<td><code>git reset</code></td>
<td>Move a referência da branch para outro commit; o efeito depende da opção utilizada.</td>
</tr>
</tbody>
</table>

<hr>

<p><a href="https://github.com/Thays-Quispe/learning-journal/blob/main/cursos/kodie/README.md">Voltar ao Nivelamento</a></p>
