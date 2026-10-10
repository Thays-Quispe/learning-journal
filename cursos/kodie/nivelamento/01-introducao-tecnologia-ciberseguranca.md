
# Introdução ao Mundo da Tecnologia e Cibersegurança

**Módulo:** Nivelamento  
**Status:** Concluído  

---

## 1. Sistemas Operacionais

O sistema operacional (SO) é o software responsável por gerenciar os recursos do computador, como processador, memória e armazenamento, além de permitir a execução de aplicativos.

Sua atuação pode ser compreendida por duas perspectivas: a *top-down*, que aproxima os recursos do hardware do usuário por meio de interfaces, e a *bottom-up*, que considera o gerenciamento dos recursos do sistema.

### Principais funções

- **Gerenciamento de processos:** organiza a execução dos programas.
- **Gerenciamento de memória:** controla o uso da memória RAM e da memória virtual.
- **Gerenciamento de recursos:** coordena o uso do hardware pelos aplicativos.
- **Sistema de arquivos:** organiza o armazenamento e a recuperação de dados.

### Tipos e exemplos

- **Arquitetura monolítica:** concentra diversos serviços essenciais no núcleo do sistema, como ocorre no Linux.
- **Micronúcleo:** mantém o núcleo reduzido e executa outros serviços separadamente, como na arquitetura utilizada pelo GNU Hurd.

Principais sistemas operacionais:

- **Windows:** muito utilizado em computadores pessoais e empresas.
- **macOS:** sistema da Apple, integrado ao seu hardware.
- **Linux:** sistema de código aberto bastante utilizado em servidores e na área de tecnologia.
- **Android:** sistema operacional móvel baseado no kernel Linux.
- **iOS:** sistema móvel da Apple.
- **ChromeOS:** sistema da Google com foco em serviços e aplicações web.

---

## 2. Redes de Computadores

As redes conectam dispositivos para permitir a comunicação, a troca de informações e o compartilhamento de recursos.

### Modelo TCP/IP

O modelo TCP/IP organiza a comunicação em quatro camadas:

1. **Aplicação:** permite a comunicação entre aplicações por meio de protocolos como HTTP, FTP e SMTP.
2. **Transporte:** controla a comunicação entre aplicações. O TCP oferece entrega confiável, enquanto o UDP prioriza uma comunicação mais simples, sem garantir a entrega dos dados.
3. **Internet:** cuida do endereçamento IP e do roteamento dos pacotes.
4. **Acesso à rede:** envolve a comunicação na rede local e a transmissão dos dados pelo meio físico ou sem fio.

### Topologias de rede

- **Estrela:** os dispositivos se conectam a um ponto central, como um switch.
- **Malha (Mesh):** possui múltiplas conexões entre os dispositivos, oferecendo caminhos alternativos.
- **Barramento:** os dispositivos compartilham um canal de comunicação.
- **Anel:** os dispositivos formam uma estrutura circular, cuja tolerância a falhas depende da tecnologia utilizada.

---

## 3. Servidores Web

Um servidor web pode ser tanto o computador que disponibiliza um serviço quanto o software responsável por receber requisições e enviar respostas aos clientes.

Existem dois tipos principais de conteúdo:

- **Estático:** entrega arquivos já armazenados, como páginas HTML e imagens.
- **Dinâmico:** gera conteúdo conforme a requisição, podendo utilizar aplicações e bancos de dados.

### Protocolo HTTP

O HTTP é utilizado na comunicação entre navegadores e servidores web.

Ele é considerado *stateless*, ou seja, o protocolo não mantém automaticamente o estado das interações anteriores. Aplicações podem utilizar mecanismos como cookies e sessões para manter informações entre requisições.

---

## 4. Áreas da Cibersegurança

A cibersegurança busca proteger sistemas, redes, aplicações e dados contra ameaças digitais.

### Blue Team — Defesa

Responsável por monitorar sistemas, identificar ameaças, prevenir ataques e responder a incidentes. Também pode atuar em SOC, análise de logs, perícia digital e controle de acessos.

### Red Team — Ofensiva

Realiza testes autorizados para identificar vulnerabilidades e avaliar a segurança dos sistemas. Inclui atividades como testes de intrusão (*Pentest*) e simulações de ataques.

### Purple Team — Integração

Promove a colaboração entre as equipes ofensivas e defensivas para melhorar os mecanismos de proteção e detecção.

### GRC — Governança, Risco e Conformidade

Busca garantir que a segurança esteja alinhada às normas, às leis e aos objetivos da organização. Alguns exemplos são a LGPD e a ISO 27001.

### Outras áreas de atuação

- **DevSecOps:** integração da segurança ao desenvolvimento de software.
- **Segurança em nuvem:** proteção de sistemas, dados e serviços hospedados na nuvem.
- **Threat Intelligence:** coleta e análise de informações sobre ameaças digitais.

---

## 5. Ameaças e desafios da Cibersegurança

A segurança digital enfrenta desafios relacionados à falta de profissionais especializados, à proteção de credenciais e aos riscos envolvendo fornecedores.

A falta de especialistas pode sobrecarregar as equipes e dificultar a prevenção e a resposta a incidentes. Além disso, falhas de segurança em empresas terceirizadas podem comprometer outras organizações, caracterizando riscos na cadeia de suprimentos (*Supply Chain*).

### Caso de ataque relacionado ao sistema Pix

O material da aula apresenta um caso envolvendo a empresa C&M Software, relacionado a fraudes financeiras e ao uso indevido de credenciais de acesso.

O caso destaca a importância de:

- Proteger credenciais e contas privilegiadas.
- Utilizar autenticação multifator.
- Monitorar acessos e atividades suspeitas.
- Controlar os privilégios dos usuários.
- Avaliar os riscos associados a fornecedores.

### Medidas de prevenção

- **MDR:** serviço gerenciado de detecção e resposta a ameaças.
- **Autenticação multifator:** adiciona uma camada de proteção ao acesso às contas.
- **Monitoramento de fornecedores:** ajuda a identificar riscos externos.
- **Capacitação contínua:** prepara profissionais e usuários para reconhecer e prevenir ameaças.

[Voltar ao Nivelamento](../README.md)
