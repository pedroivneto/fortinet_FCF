# Rede segura
## Aula 1 - Segurança de perímetro
- Cria um limite seguro onde 

## Aula 3 - Rede zero-trust (confiança zero)
- Não é um software ou infraestrutura de hardware, mas um conceito que se baseia em 3 pontos principais:
    1. Nunca confie, sempre verifique: Autentique e autorize;
    2. Implemente poucos privilégios;
    3. Assuma que a segurança da sua rede foi quebrada: Reduza a superfície de ataque.
- O princípio do "nunca confie": a confiança é explicitamente derivada de um mix de identificações e aspectos contextualizados:
    - Processo de identificação: MFA (autenticador multi-fator) é um método de autenticação no qual utiliza um computador e um dispositivo autorizado para garantir o acesso, apresentando duas ou mais peças de evidência (fatores);
    - Aspecto baseado em contexto:
        - Data e hora: um exemplo é a utilização somente em horário comercial, ou a utilização de OTP (one-time password / senha de uma utilização);
        - Geolocalização: são gatilhos que podem disparar restrições a um recurso dependendo da geolocalização do requerente;
        - Postura segura: são impostas restrições a dispositivos que não atendem a determinados requisitos, como sistema desatualizado ou ausência de anti-vírus.
#### Princípios de poucos privilégios
- PAM (manutenção de acesso ao privilégio): é um mecanismo de segurança que guarda identidades com privilégios especiais de acesso ou capacidade maior que os usuários normais;
- Definir a superfície de proteção: processo de identificação dos recursos de rede, verificando os graus de confidencialidade e determinando quais papéis querem acesso a elas.
- O Kipling Method (Método de Kipling) no contexto de Zero Trust Architecture (ZTA) e Zero Trust Segmentation (ZTS) é uma metodologia de criação de políticas de segurança baseada em seis perguntas fundamentais: Who (Quem), What (O quê), When (Quando), Where (Onde), Why (Por quê) e How (Como).
#### Princípios de invasão da rede
- Preparar para o pior: ter pronto planos de contigência para, quando a invasão acontecer, o plano é posto em ação para mitigar a invasão;
- Microsegmentação: Realizar a quebra da rede em vários microsegmentos, para que a infecção não se alastre lateralmente.
#### Acesso Zero Confiança (ZTA)
- É baseado em 2 principais pontos:
    - Role-based access control (controle de acesso baseado em papéis): o acesso tem diferentes tipos de liberações, de acordo com o tipo de acesso:
        - Empregado;
        - Convidado;
        - Contratado;
        - Gerente de RH;
        - Analista de TI;
        - Gerente de contas...
    - Endpoint agent: software que visa maior visibilidade e controle do dispositivo, como:
        - Sistema operacional;
        - Patch level;
        - Softwares instalados;
        - Analisa os riscos...
#### Outros métodos Zero Trust
- NAC (Network access controle / controle de acesso a rede): para dispositivos embarcados, como os IoT:
    - Identifica o dispositivo;
    - Mais visibilidade;
- ZTNA (Zero trust network access / confiança zero ao acesso a rede):
    - estabelece uma sessão segura automaticamente...

- Befeníficos do ZTS:
    - Sem confiança: precisa provar a identidade através de:
        - MFA;
        - Medição do risco através da avaliação baseada em contexto.
    - Menos privilégios: o acesso evolui a medida do cargo em que o colaborador evolui também;
    - Rever acessos para ativos perguntando "quem, o que, porque, quando, onde e como";
    - Microsegmentação da rede.

## Aula 4 - Gerenciamento de segurança de rede centralizado
- Ação de reunir dados relacionados a segurança de várias aplicações em um local central.
- Os dados podem ser enviados através de:
    - Logs;
    - SNMP (protoloco simples de gerenciamento de rede);
    - API (interface de aplicação programável)
- O objetivo é fornecer uma visualização de ações de gerenciamento típicas. como:
    - Configuração;
    - Controle;
    - Operação;
    - Diagnóstico
#### Arquitetura de fábrica de dados
- Provê a possibilidade de monitorar e gerenciar dados e aplicações onde quer que estejam enquando permanecem governados centralmente.
- Os benefícios do gerenciamento centralizado da seguraça da rede são:
    - Alto grau de visualização e ampla visibilidade;
        - Evita problemas de segurança;
        - Reduz o tempo de resposta a incidentes;
        - Minimiza interrupções.
    - Integração de dispositivos: centraliza as definições de configurações e orquestramento de políticas.
    -  Redução do número de tarefas manuais / repetitivas:
        - Fácil manutenção;
        - Melhora na capacidade e performance de predictibilidade;
        - Fácil auditoria.
## Aula 5 - Segmentação de rede
- Processo de segmentar uma grande rede em redes menores e isoladas, ajudando a proteger de brechas de segurança e mau funcionamento. As redes são separadas por funções similares, para evitar o vazamento de informações confidenciais;
- Dispositivos que possuem conexão como mundo exterios (conexão com a internet), ficam em uma segmentação chamada DMZ (Zona Desmilitarizada), onde as informações que saem dessa zona para a internet são classificadas como tráfego norte-sul. Os dispositivos podem se comunicar entre si, já que eles são segmentados novamente, dentro da segmentação, em microsegmentos, chamado de tráfego leste-oeste. Todos os dispositivos estão sob a regra de Zero trust;
#### Tipos de segmento
- Físico: Utiliza firewalls e routers, gerando diferentes redes físicas;
    - A segmentação ocorre na camada física da rede, dividindo a rede principal em subredes;
    - A segurança das redes é feita por políticas de firewall, ACL (Lista de Cotrole de Acesso) e roteadores (routers);
- Lógico: Segmentação da rede em diferentes níveis do modelo OSI. Uma forma de segmentação lógica é a criação de redes virtuais, que permite a comunicação dos dispositivos entre si através de switches;
    - SD-WAN (Software-Defined WAN): trabalha na camada lógica do padrão OSI, e permite a comunicação com a internet utilizando túneis overlays encriptados;
    - Rede overlay: é uma rede virtualzada construida em cima da uma rede underlay;
    - Rede underlay: se refere a estrutura física da rede.
#### Gerenciando segmentos de rede
- Jumpbox: Dispositivo com acesso controlado avançado, autorização limitada que age como um proxy para os as comunicações entre as segmentações internas. A jumpbox tem monitoramento e registro de log adicional, que envia um alerta para o gerente de TI, informando que foi comprometido;
- Bastion host: Um computador ou servidor que o propósito é prover acesso da rede privada a uma rede externa. É configurado para se manter contra ataques enquanto permte que usuários acessem subredes, através de uma aplicação.
#### Benefícios da segmentação
- Fácil manutenção e configuração;
- Redução do número de transmissões de broadcast de rede;
- Minimização de congestionamento de rede;
- Limita ataques a um segmento específicos;
- Maior proteção dos dispositivos vulneráveis;
- Redução do escopo de dispositivos afetados por compliance.

## Aula 6
- Com o crescimento das redes, houve evolução na proteção das redes, consequentemente, as evoluções dos firewalls, que possuem 4 gerações:
    - Packet filter/stateless firewall: Examina as informações de rotas e da camada de protocolo, através de políticas de firewall, para fazer verificações de atributos, onde o pacote pode seguir ou não:
        - Firewall policies podem ser
            - Implícitas: é uma política aplicada se nenhuma correspondência for encontrada na lista de políticas do firewall;
            - Explícita: é uma política criada para especificar se o tráfego é permitido ou negado.
        - Atributos do firewall:
            - Fonte e endereço de destino da rede;
            -  Protocolos e números das portas;

    - Stateful firewall: Criado mitigando as falhas da primeira geração, desenvolvendo um critário adicional para bloquear ou permitir o tráfego. Supervisiona a todo momento as conexões, através do estado da conexão e das 5 tuplas.
        - 5 tuplas:
            - Endereço de IP e número da porta da fonte;
            - Endereço de IP e número da porta do destino;

    - Third-generation firewall (3ª geração): Para mitigar a brecha que o protocolo HTTP promove na 2ª geração, a 3ª verifica a carga dos dados, o estado mais uma aplicação de filtro de camada, e combina com a proteção de antivírus, antispam, IPS (Intrusion Preventiion System - Sistema de Prevenção de Intrusão) e VPN (Virtual Private Network - Rede Virtual Privada). As camadas filtradas podem ser:
        - FTP;
        - DNS;
        - HTTP:
            - tráfego do navegador;
            - blog;
            - compartilhamento de arquivo;
            - e-commerce;;
            - rede social;
            - VoIP;
            - e-mail.

    - Next-generetion firewall (NGFW): A 4ª geração de firewalls funcionam como a seguraça de um aeroporto, onde o pacote para por diversos pontos de checagem antes de continuar.
        - Primeira linha de defesa: checa pacotes e usa decisões baseadas em regras para determinar a permissão ou não do tráfego;
        - Segunda linha de defesa: Deep Packet Inspection (DPI - inspeção detalhada de pacote): verifica por códigos maliciosos e uso da rede. Também é confirmado se o formato da informação está correto, e dependendo da inspeção, pode ser tomado 4 ações, alerta, bloqueio, alterar rota ou guardar no log;
        - Terceira linha de defesa: Caso algum código malicioso seja achado, ele é enviado para a caixa de areia (sandbox), para ser analisado futuramente.

## Aula 7 - Portas e Switches
- Switches são dispositivos da camada de enlace de dados, encaminha pacotes para VLANs baseado na fonte do endereço MAC do pacote. Switches tem uma tabela com as portas, os endereços MAC e as VLANs.

#### Ataque MAC flooding
- É um ataque com o objetivo de inundar a tabela CAM de switches, causando um potencial DoS (Denial of Service) e vazamento de informações sensíveis.
- Mac-spoofing é a alteração do endereço MAC de fábrica por outro.
- Para evitar ataques de MAC flooding é limitar o número de entradas por porta para um.
- MAC estático: é configurado a uma porta do switch e não é removido automaticamente;
- Sticky MAC - após o switch identificar o 
endereço MAC, ele se torna permanente na CAM table, e só é removido se o switch for reiniciado;
- Autenticação 802.1x - é o padrão designado para autenticar dispositivos que desejam acessar a rede.
#### Melhores práticas para proteger switches e portas
- Proteger os switches físicos localmente, e proteger o acesso com:
    - Autenticação;
    - Autorização;
    - Protocolo seguro.
- Separar os switches para melhor segmentação, como switches de rede interna e externa, previnindo que ambos sejam atacados ao mesmo tempo;
- Limitar os ataques por inundação limitando a quantidade de MACs permitidos por porta;
- Configurar MAC estático ou sticky, evitando ataques por MAC spoofing;
- Usar ACLs (lista de controle de acesso) para endereços não verificados;
- Adicionar autenticação de porta, IEEE 802.1x;
- Implementar espelhamento de portas para monitorar suas atividades.