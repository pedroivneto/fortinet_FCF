# Autenticação e controle de acesso

## Aula 1 - Métodos de autenticação
### Tipos de autenticação
- Inerência - utiliza um traço físico único em que a pessoa que está tentando se autenticar tem. Existem vários traços únicos, os mais comuns são:
    - digital, retinas iris, padrões faciais e medidas das mãos
- Posse - baseado em algo que você tem, e mais ninguém. Pela lógica, se você tem algo só você tem, isso confirma quem você diz que é:
    - Assinatura digital é um exemplo, já que sua chave privada, só você tem acesso;
    - Hardware ou Software token (dispositivo que gera um OTP usando um algoritmo com chave secreta);
    - Mensagem SMS - OTP (One-time password)
- Comportamento - autenticação baseada em comportamento utiliza dados biométricos ativos. Tipos de identificação:
    - Por voz;
    - Dinâmica de digitação;
    - Características de utilização do mouse.
- Conhecimento - baseado em conhecimento (segredo):
    - Um exemplo de autenticação baseada em conhecimento é perguntas e respostas;
    - Senhas;
    - PIN (personal number identification).
### Melhoria na segurança da autenticação - MFA
- Single-Factor Authentication - pede uma forma simples de autenticação, como nome de usuário e senha. Porém, existe uma crescente movimento em que se demanda duas ou mais formas de autenticação, conhecido como MFA (Muti-Factor Authentication).
- Um exemplo de MFA são ações realizadas em caixas eletrônicos, pois você precisa do cartão (o que você tem), sua senha (o que você sabe) e da sua digital (algo inerente a você).

## Aula 2 - Single-Sign On (SSO)
- É um método de autorização que mantém a estrutura de segurança da rede e sistemas e, ao mesmo tempo, evita que o usuário realize várias autenticações em vários sistemas diferentes. Um token é gerado a partir do sucesso da autenticação, que é enviado aos sistemas que requisitarem de autenticação, podendo ser através dos cookies, por exemplo.
### Same Sign-On
- O usuário usa suas credenciais armazenadas em um servidor de diretórios (Active directory) para acessar as aplicações. Normalmente, um LDAP (lighweight directory access protocol) em acordo com as regras do servidor, são usados para esse propósito. Apesar do usuário utilizar a mesma credencial, terá que autenticar em cada aplicação.
### Aplicações atuais
- Um exemplo de SSO é o acesso a serviços, cadastros de terceiros. Por exemplo:
    1. Você quer criar uma conta no Spotify;
    2. É selecionado a opção de continuar com o Google;
        - O Google é o Provedor de Informações, se tornando o provedor de informações (IdP);
    3. Por terem uma relação de confiança, o Spotify aceita as informações e confirma que você é você
        - Por prover serviço, o Spotify é chamado de provedor de serviços (SP).
- Atualmente, essa prática é amplamente utilizada.
### Vantagens e desvantagens do SSO
- Vantagens:
    - reduz a necessidade de guardar multiplas credenciais;
    - reduz a redundância e custo administrativo da organização para guardar, proteger e manter a base de dados de credenciais;
    - facilita o compliance e o report dos usuários, atavés de um banco de dados centralizado
- Desvantagens:
    - Caso o banco de dados seja comprometido, o agressor terá acesso a todas as credenciais da organização
    - 💡 Para fortalecer a autenticação, pode-se implementar o MFA.
### Como funciona o SSO
- Para utilizar o SSO, é preciso de um usuário, um SP (provedor de serviço) e um IdP (provedor de identidade)
    1. O usuário conecta a um provedor de serviço, como um site ou aplicação (sistema);
    2. O provedor do serviço redireciona o usuário a página de login do provedor de identidade;
    3. O usuário informa suas credenciais e se autentica no provedor de identidade;
    4. O provedor de identidade gera um token de autenticação, e o usuário é enviado de volta ao site, e o token anexo prova que o usuário foi autenticado mais algum conteúdo adicional.
### Protocolos de SSO
- Protocolos para implementação de SSO
    - OAuth;
    - Security Assertion Markup Language (SAML) - é baseado na Standard Markup Language (XML);

## Aula 3 - Frameworks de autenticação, protocolos e ferramentas
Um framework de autenticação é o esquema ou plano básico para como entidades irão provar suas identidades em um sistema
Os componentes de um framework de automação são:
- Método - métodos de autenticação ou fatores de autenticação são os principais meios que as entidades provam suas identidades. Os meios podem ser baseados em:
    - conhecimento;
    - posse;
    - inerência;
    - comportamento.
- Forma - forma de autenticação são os mecanismos nos quais a entidade prova sua identidade. Exemplos de fatores do método conhecimento são PIN e perguntas e respostas;
- Protocolo - São padrões de comunicação computacionais usados para autenticar uma entidade a um autenticador. O protocolo define, especificamente, a transferência dos dados da autenticação entre duas entidades e incluem o tipo de sintaxe usada e a sequência de eventos;
- Ferramentas - São o software e hardware usado para a autenticação. O autenticador do Google é um exemplo de ferramenta de autenticação, como um token físico ou dispositivo biométrico são ferramentas de autenticação de hardwares .
### Tipos de protocolos de autenticação
- Remote authentication dial-in user service (RADIUS) - Protocolo remoto de autenticação, autorização e verificação (AAA) - O cliente solicita acesso ao servidor, o servidor busca autenticação no servidor RADIUS que libera acesso ao cliente. Pode ser habilitado o framework 802.1x, que gera criptografia única para a sessão do usuário;
- LDAP - Protocolo padrão industrial aberto para o acesso ao diretório de serviços através de uma rede IP. É um protocolo de comunicação para servidores diretórios;
- TACACS+ - é similar ao RADIUS, utiliza o protocolo AAA, onde todos os A's são encriptados e usa o protocolo de transporte TCP
### Métodos de autenticação
Definem a maneira a qual será realizada a autenticação.
Podem ser descritos como conjunto de regras para interação e verificação, que softwares endpoints ou sistemas usam para se comunicar.
- PAP (Password Authentication Protocol)
    - Pode autenticar sessões PPP;
    - Usa o processo de aperto de mão duplo:
        1. Client envia ao servidor o username e password;
        2. O servidor aceita ou rejeita a solicitação.
    - Utiliza informação de autenticação estática.
- CHAP (Challenge Handshake Authentication Protocol)
    - Pode autenticar sessões PPP;
    - Usa o processo de aperto de mão triplo:
        1. O servidor gera uma string ou hash aleatório do username;
        2. O Client envia o hash de volta, encriptado;
        3. O servidor responde autorizando ou não.
    - A versão do Microsoft é MS-CHAP
    ### Framework 802.1x
É um padrão IEEE baseado em controle de acesso baseado em porta (PNAC - Port-based Network Access Control), fazendo parte dos padrões IEEE 802.1, fornecendo um mecanismo de autenticação para dispositivos que queiram se conectar a uma LAN ou WLAN.
O padrão possui três entidades:
- Supplicant (client) - o dispositivo do cliente;
- Intermediary (autenticador) - a rede que fornece o link entre o cliente e a rede, podendo ser um switch ou um wireless access point;
- Authentication server - um servidor confiável que julga o processo de autenticação, se irá ser aceito ou não. Normalmente suportam protocolos RADIUS ou EAP.
A sequência de autenticação do protocolo 802.1x:
1. O cliente solicita uma nova conexão;
2. O intermediário pede para o cliente se identificar;
3. O cliente informa seus dados de identificação;
4. O intermediário repassa a informação para o servidor de autenticação;
5. O servidor de autenticação retorna o desafio para o intermediário;
6. O intermediário repassa o desafio para o cliente;
7. O cliente responde o desafio;
8. O intermediário repassa a resposta ao servidor de autenticação;
9. Se as credenciais estão corretas, o servidor envia uma mensagem de aceitação para o intermediário;
10. O intermediário encaminha a mensagem e permite o acesso do cliente.
O processo é dividido em dois subprocessos: identificação e verificação.
### Extensible Authentication Protocol (EAP) Framework
Não é um método, e sim um framework, que fornece alguns métodos com funções e negociações comuns, chamados EAP methods

## Aula 4 - Autenticação e controle de acesso
### Controle de acessos é métodos de controle de acesso
Controle de acesso é habilidade de restringir o acesso a locais físico ou digitais.
Um método de controle de acesso é o sistema usado para determinar quais recursos o usuário tem permissão para utilizar, baseado na autenticação e regras do sistema.
### Métodos de controle de acesso
- MAC (Mandatory Access Control) - não permite que algum participante mude os requerimentos de segurança. Exemplo:
    - Padlocks (trancas);
    - SELinux OS.
- DAC (Discretionary Access Control) - permique que fatores externos alterem restrições de controle de acesso. Exemplo:
    - Segurança de prédios;
    - Microsoft User Access Control (UAC);
    - permissões do sistema de arquivos do Linux.
Os métodos de controle de acesso podem ser mandatórios ou discrecionário, mas não ambos.
- LBAC (Lattice-based access control) - Modelo de acesso de controle que garante permissões a locais ou materiais baseado no nível de segurança atribuido, podendo acessar dados e locais do seu nível ou abaixo dele. Exemplos:
    - Classificação de documento.
- RSBAC (Rule-set-based access control) - reforça o acesso através de uma lista de regras, e são validadas de cima para baixo, e quando uma correspondência acontece, o acesso é permitido ou negado baseado naquela regra. Normalmente usadoem firewalls. Exemplos:
    - Conjunto de regras dos roteadores;
    - iptables;
    - trancas por tempo das portas de hotel;
    - crachás de identificação para acesso a áreas restritas.
- RBAC (Role-based access control) - controla o acesso a informações baseado no papel de cada colaborador, gerenciado por um administrador e  asignado para usuários e dispositivos. Benefício do método é a flexibilidade de garantir acesso a novos usuários ou dispositivos. A disvantagem é o tempo gasto configurando a estrutura de acesso. Exemplos:
    - Segurança de grupo Microsoft Active Directory;
    - Gerenciador funções em diversos sistemas e dispositivos de segurança;
    - Política de segurança da empresa baseado em sua posição no trabalho.
- ABAC (Attribute-base access control) - pode considerar vários atributos para determinar se o acesso deveria ser permitido. Garante dinamicamente o acesso e temc consumo intenso de recursos e tempo. De difícil implantação, é necessário um grande tempo para planejar e implementar o motor de regras. Exemplos:
    - Checagem envolve multiplos atributos;
    - Microsoft Dynamic Access Control (DAC);
    - Modelos de segurança de banco de dados;
    - Next-generation firewall policies.

## Aula 5 - Melhores práticas
### Ciclo de vida do gerenciamento de identidade e acesso
Ciclo de vida do gerenciamento de identidade e acesso é quando um usuário ou dispositivo tem suas permissões provisionadas, e permanece até o momento de seu desprovisionamento, quando o ciclo reinicia.
A governança sobre o ciclo de vida possui 5 características:
- Provisionamento - criação da conta do usuário ou dispositivo e asignação das funções ou grupos;
- Autenticação - validação da identidade;
- Autorização - determina se o usuário tem permissões válidas e audita suas conexões;
- Self-service - serviços que o próprio usuário pode realizar, tais como mudança de senha, atualização de informações, requerer acesso a informações proibidas e reportar atividades suspeitas;
- Desprovisionamento - a retirada das permissões, regras de controle de acesso, funções e grupos.
O sistema de governança, normalmente um time, controla os métodos de controle de acesso e políticas e revisa e modifica esses processos.
### Desafios do controle de acesso
- Configurar os controles de acesso:
    - Várias funções, grupos e políticas atraves de múltiplos departamentos e dispositivos;
    - Complexidade das regreas;
    - Entendimento das inconsistências do controle de acesso de dispositivos;
    - Má configuração ou regras não utilizadas podem comprometer a configuração correta.
-  Consistência:
    - Exige flexibilidade para criar políticas de controle de acesso apropriadas;
    - Criar multiplas políticas de controle de acesso e regras através de múltiplas plataformas.
- Experiência do usuário:
    - Mudança de senha;
    - Lidar com senhas expiradas;
    - Garantir acesso adicional a recursos com facilidade;
    - Normalmente a fase self-service do ciclo.
- Auditoria:
    - Criar uma trilha para autorizações e autenticações;
    - Lidar com filiais dispersas geograficamente e controlar o acesso aos locais;
    - Consolidar multiplos tipos de dispositivos e logins.
### Administração e permissões
- Administradores e governança:
    - Controla a postura da segurança e cria políticas de controle de acesso;
    - Define políticas de escalonamento importante para desastres, contratações e desligamentos;
    - Comunica as políticas através dos planos e políticas de segurança;
    - Audita periodicamente as contas de usuários e as políticas de controle de acesso;
- Separação de deveres:
    - Mantem a separação entre usuários e administradores com contas e políticas de controle de acesso;
    - Separa o controle de acesso de diferentes departamentos que precisam ter diferentes requisitos para permitir um controle de acesso mais seguro e granular;
    - Reforços a nivel de SO usando características de segurança como UAC no Windows e superuser no Linux;
    - Separação de controle de acesso através de divisões que fazem sentido, como departamentos, hierarquia organizacional ou localização geográfica;
    - Minimizar sobrecarga operacional, degradação de regras e escalonamento de privilégios.
- Controle de acesso, criação de política e recertificação:
    - Criar e documentar a criação de políticas de controle de acesso para o administrador ver o quadro geral;
    - Revisar periodicamente (pelo menos anualmente) todas as políticas, para verificar se ainda estão relevantes ou precisam ser atualizadas ou deletadas;
    - Reavaliar as políticas quando uma grande mudança na rede ou infraestrutura acontecer, sem assumir que as políticas existentes irão conseguir lidar com os novos equipamentos ou situações;
- Educação do usuário:
    - Conhecimento das políticas de controle de acesso e de segurança da empresa;
    - Abilidade de criar senhas fortes e usar formulários de mudança;
    - Abilidade de identificar e reportar atividades suspeitas ou desconfiguração das políticas.
- Inclusão de usuário, recertificação e exclusão de usuário:
    - Métodos claros e fáceis de usar para criar perfis de controle de acesso;
    - Recertificação periódica para garantir que os usuários tem as políticas corretas asignadas;
    - Políticas compreensivas de exclusão para garantir a remoção de todos os acessos do usuário e deletar contas antigas.
- Escalonamento e plano de recuperação de desastres:
    - Publicar planos para situações de recuperação de desastres;
    - Estragégias claras e de fácil utilização para permitir que os usuários reportem atividades suspeitas e desconfigurações de políticas de acesso.

## Aula 6 - Controle de acesso a rede
### Network Access Control (NAC)
É uma aplicação ou máquina virtual que controla o acesso a rede, tem uma visão completa dos perfis de rede e categoriza os dispositivos automaticamente.
O NAC avalia e classifica da seguinte forma:
- Usuários;
- Dispositivos;
- Localização;
- Sistema operacional;
- Outras formas de classificação.
Muitas soluções NAC tem arquitetura centralizada e implementa o controle de acesso de dispositivos em grandes redes multi-filiais.
NAC utiliza o padrão IEEE 802.1x para autenticação e autorização, que tem 3 entidades envolvidas:
- O dispositivo do cliente:
    - User name e senha;
    - Certificado digital.
- O autenticador:
    - Switch de rede;
    - Acesso wireless
- Servidor de autenticação

**Portal Captive** - utilizado especialmente em redes sem fio públicas, como se conectar a rede de um coffee shop, onde antes de obter acesso a rede, você tem que interagir com uma página web que pede para você cumprir algumas tarefas.
### Desafios para NAC
- BYOD (Bring your own device / traga seu próprio dispositivo): dispositivos que tentam conectar a rede são pessoais, onde o departamento de segurança não tem controle sobre o que roda nesses dispositivos;
- IoT (Internet of Things): esses dispositivos transmitem informações de um local ao outro, através da internet, aumentando a superfície de ataque. Dispositivos IoT são tolerados por economizarem tempo e dinheiro.
### Capacidades atuais do NAC
As políticas do NAC possuem perfis que são confrontados com as solicitações de acesso.
Garante acesso a informações sensíveis e a aplicações baseado no que o sistema sabe.
Um exemplo é a liberação de acesso de uma câmera de segurança IP a um servidor de gravação de vídeo mas não ao servidor financeiro, já que a câmera IP não tem negócios a tratar com o servidor financeiro, redirecionando a requisição a VLAN correta, e o firewall realiza o restante da operação.
Com isso, se realiza a segmentação da rede por software.
### A importância do NAC
- Segurança melhorada - provê uma visão total de todos os dispositivos da empresa:
    - Melhora a segurança;
    - Autentica usuários.
- Economia de custos - gera economia pois é necessário menos recursos de IT;
- Automação - por conta do aumento de dispositivos, a segurança da informação não consegue autenticar manualmente todos os dispositivos, logo, a automação do NAC oferece uma grande eficiencia em autenticar e autorizar dispositivos;
- Experiẽncia em IT melhorada - Acesso sem interrupções oferece uma experiência de usuário sem atritos ao se conectar à rede.
- Controle fácil - É de grande ajuda não somente quando a equipe precisa determinar quais endpoints ou usuários tiveram acesso liberado a rede, mas também no gerenciamento do ciclo de vida, quando dispositivos precisam ser atualizados ou repostos.