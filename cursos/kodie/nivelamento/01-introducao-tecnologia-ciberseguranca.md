<h1>Introdução ao Mundo da Tecnologia e Cibersegurança</h1>

<p><strong>Módulo:</strong> Nivelamento<br>
<strong>Status:</strong> Concluído</p>

<hr>

<h2>1. Sistemas Operacionais</h2>

<p>O sistema operacional (SO) é o software responsável por gerenciar os recursos do computador, como processador, memória e armazenamento, além de permitir a execução de aplicativos.</p>

<p>Sua atuação pode ser compreendida por duas perspectivas: a <em>top-down</em>, que aproxima os recursos do hardware do usuário por meio de interfaces, e a <em>bottom-up</em>, que considera o gerenciamento dos recursos do sistema.</p>

<h3>Principais funções</h3>

<ul>
<li><strong>Gerenciamento de processos:</strong> organiza a execução dos programas.</li>
<li><strong>Gerenciamento de memória:</strong> controla o uso da memória RAM e da memória virtual.</li>
<li><strong>Gerenciamento de recursos:</strong> coordena o uso do hardware pelos aplicativos.</li>
<li><strong>Sistema de arquivos:</strong> organiza o armazenamento e a recuperação de dados.</li>
</ul>

<h3>Tipos e exemplos</h3>

<ul>
<li><strong>Arquitetura monolítica:</strong> concentra diversos serviços essenciais no núcleo do sistema, como ocorre no Linux.</li>
<li><strong>Micronúcleo:</strong> mantém o núcleo reduzido e executa outros serviços separadamente, como na arquitetura utilizada pelo GNU Hurd.</li>
</ul>

<p>Principais sistemas operacionais:</p>

<ul>
<li><strong>Windows:</strong> muito utilizado em computadores pessoais e empresas.</li>
<li><strong>macOS:</strong> sistema da Apple, integrado ao seu hardware.</li>
<li><strong>Linux:</strong> sistema de código aberto bastante utilizado em servidores e na área de tecnologia.</li>
<li><strong>Android:</strong> sistema operacional móvel baseado no kernel Linux.</li>
<li><strong>iOS:</strong> sistema móvel da Apple.</li>
<li><strong>ChromeOS:</strong> sistema da Google com foco em serviços e aplicações web.</li>
</ul>

<hr>

<h2>2. Redes de Computadores</h2>

<p>As redes conectam dispositivos para permitir a comunicação, a troca de informações e o compartilhamento de recursos.</p>

<h3>Modelo TCP/IP</h3>

<p>O modelo TCP/IP organiza a comunicação em quatro camadas:</p>

<ol>
<li><strong>Aplicação:</strong> permite a comunicação entre aplicações por meio de protocolos como HTTP, FTP e SMTP.</li>
<li><strong>Transporte:</strong> controla a comunicação entre aplicações. O TCP oferece entrega confiável, enquanto o UDP prioriza uma comunicação mais simples, sem garantir a entrega dos dados.</li>
<li><strong>Internet:</strong> cuida do endereçamento IP e do roteamento dos pacotes.</li>
<li><strong>Acesso à rede:</strong> envolve a comunicação na rede local e a transmissão dos dados pelo meio físico ou sem fio.</li>
</ol>

<h3>Topologias de rede</h3>

<ul>
<li><strong>Estrela:</strong> os dispositivos se conectam a um ponto central, como um switch.</li>
<li><strong>Malha (Mesh):</strong> possui múltiplas conexões entre os dispositivos, oferecendo caminhos alternativos.</li>
<li><strong>Barramento:</strong> os dispositivos compartilham um canal de comunicação.</li>
<li><strong>Anel:</strong> os dispositivos formam uma estrutura circular, cuja tolerância a falhas depende da tecnologia utilizada.</li>
</ul>

<hr>

<h2>3. Servidores Web</h2>

<p>Um servidor web pode ser tanto o computador que disponibiliza um serviço quanto o software responsável por receber requisições e enviar respostas aos clientes.</p>

<p>Existem dois tipos principais de conteúdo:</p>

<ul>
<li><strong>Estático:</strong> entrega arquivos já armazenados, como páginas HTML e imagens.</li>
<li><strong>Dinâmico:</strong> gera conteúdo conforme a requisição, podendo utilizar aplicações e bancos de dados.</li>
</ul>

<h3>Protocolo HTTP</h3>

<p>O HTTP é utilizado na comunicação entre navegadores e servidores web.</p>

<p>Ele é considerado <em>stateless</em>, ou seja, o protocolo não mantém automaticamente o estado das interações anteriores. Aplicações podem utilizar mecanismos como cookies e sessões para manter informações entre requisições.</p>

<hr>

<h2>4. Áreas da Cibersegurança</h2>

<p>A cibersegurança busca proteger sistemas, redes, aplicações e dados contra ameaças digitais.</p>

<h3>Blue Team — Defesa</h3>

<p>Responsável por monitorar sistemas, identificar ameaças, prevenir ataques e responder a incidentes. Também pode atuar em SOC, análise de logs, perícia digital e controle de acessos.</p>

<h3>Red Team — Ofensiva</h3>

<p>Realiza testes autorizados para identificar vulnerabilidades e avaliar a segurança dos sistemas. Inclui atividades como testes de intrusão (<em>Pentest</em>) e simulações de ataques.</p>

<h3>Purple Team — Integração</h3>

<p>Promove a colaboração entre as equipes ofensivas e defensivas para melhorar os mecanismos de proteção e detecção.</p>

<h3>GRC — Governança, Risco e Conformidade</h3>

<p>Busca garantir que a segurança esteja alinhada às normas, às leis e aos objetivos da organização. Alguns exemplos são a LGPD e a ISO 27001.</p>

<h3>Outras áreas de atuação</h3>

<ul>
<li><strong>DevSecOps:</strong> integração da segurança ao desenvolvimento de software.</li>
<li><strong>Segurança em nuvem:</strong> proteção de sistemas, dados e serviços hospedados na nuvem.</li>
<li><strong>Threat Intelligence:</strong> coleta e análise de informações sobre ameaças digitais.</li>
</ul>

<hr>

<h2>5. Ameaças e desafios da Cibersegurança</h2>

<p>A segurança digital enfrenta desafios relacionados à falta de profissionais especializados, à proteção de credenciais e aos riscos envolvendo fornecedores.</p>

<p>A falta de especialistas pode sobrecarregar as equipes e dificultar a prevenção e a resposta a incidentes. Além disso, falhas de segurança em empresas terceirizadas podem comprometer outras organizações, caracterizando riscos na cadeia de suprimentos (<em>Supply Chain</em>).</p>

<h3>Caso de ataque relacionado ao sistema Pix</h3>

<p>O material da aula apresenta um caso envolvendo a empresa C&amp;M Software, relacionado a fraudes financeiras e ao uso indevido de credenciais de acesso.</p>

<p>O caso destaca a importância de:</p>

<ul>
<li>Proteger credenciais e contas privilegiadas.</li>
<li>Utilizar autenticação multifator.</li>
<li>Monitorar acessos e atividades suspeitas.</li>
<li>Controlar os privilégios dos usuários.</li>
<li>Avaliar os riscos associados a fornecedores.</li>
</ul>

<h3>Medidas de prevenção</h3>

<ul>
<li><strong>MDR:</strong> serviço gerenciado de detecção e resposta a ameaças.</li>
<li><strong>Autenticação multifator:</strong> adiciona uma camada de proteção ao acesso às contas.</li>
<li><strong>Monitoramento de fornecedores:</strong> ajuda a identificar riscos externos.</li>
<li><strong>Capacitação contínua:</strong> prepara profissionais e usuários para reconhecer e prevenir ameaças.</li>
</ul>

<hr>

<p><a href="https://github.com/Thays-Quispe/learning-journal/blob/main/cursos/kodie/README.md">Voltar ao Nivelamento</a></p>
