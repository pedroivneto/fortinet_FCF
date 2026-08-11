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