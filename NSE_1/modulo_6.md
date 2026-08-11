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

## Aula 8 - Protocolos de segurança
- São protocolos usados para assegurar uma transação segura de informações. Antes usava-se clear text para a comunicação, hoje existem protocolos de segurança para realizar essas tarefas.
    - E-mails -  Multipurpose Internet Mail Extentions (MIME) / S/MIME (Secure MIME):
        - O remetente criptografa a mensagem com a chave pública do destinatário, que utiliza sua chave pública para descriptografar a mensagem;
        - A assinatura digital provê:
            - Segurança: por autenticação, não-repudiação e integridade de dados;
            - Confidencialidade, com o sistema end-to-end.
    - Navegadores web -  HTTP/HTTPS: Funciona com o TLS (segurança da camada de transporte), que encripta os dados enviados por redes não seguras, como a internet. O processo é feito da seguinte forma:
        - O servidor web envia sua chave pública após a requisição de conexão, O cliente gera uma chave aleatória e encripta a chave pública recebida e envia ao servidor. O servidor decripta com sua chave privada. A conexão então é assegurada com essa chave simétrica.
        - MITM (homem do meio / Men in The Middle) é um mecanismo que permite um dispositivo interceptar a comunicação entre o usuário e o servidor, logo a comunicação deixa de ser direta e passa por um dispositivo intermediário.
    - Controle remoto - Telnet / SSH: É realizado de forma parecida com o TLS, porém o usuário envia sua chave pública, que consta no servidor, que encripta uma mensagem e envia para o cliente, que decripta com sua chave privada e envia a mensagem novamente para o servidor. Se a mensagem for a mesma que foi enviada anteriormente, o link é autorizado. SSH usa:
        - Diffie-Hellman (DH): permite a troca segura de chaves simétricas através da comunicação usando chaves assimétricas (a chave privada se mantém salva local, enquanto a pública é enviada);
        - MAC (Message Authentication Code): o algoritmo MAC gera um hash que é anexado a mensagem, para garantir sua integridade e autenticidade.
    - Acesso remoto - L2TP /IPsec: é um conjunto de protocolos e padrões abertos projetado pela IETF para garantir a segurança, privacidade e integridade das comunicações na camada de rede (Camada 3 do modelo OSI):
        1. Gatilho: O tráfego de dados chega ao dispositivo de borda (ex: FortiGate/Router) e é identificado como tráfego que deve ser protegido.
        2. Fase 1 (IKE): Os dispositivos negociam autenticação e criam o canal de controle seguro.

        3. Fase 2 (IKE): Os dispositivos negociam as chaves e políticas para os dados do usuário.

        4. Transferência Segura: Os dados reais são criptografados pelo ESP e transmitidos através do túnel.
## Aula 9 - Sandbox
- No contexto de segurança da computação, é um ambiente virtual controlado e a parte da rede, que permite confinar ações de aplicações, como abrir um arquivo Word ou um navegador, evitando a diseminação da ameaça, caso a aplicação esteja infectada
- Foi criada para a defesa contra ataques do tipo zero-day (dia zero).
- Existem 3 gerações de sandboxes:
    - 1ª geração: Era incapaz de compartilhar dados de inteligência com outros dispositivos devido a arquitetura de standalone solutions (se manter por si só), consequentemente, o processo de consolidação e análise da ameaça era desafiadora e com alto consumo de tempo;
    - 2ª geração: melhora a integração com outros dispositivos de segurança, permitindo o compartilhamento de dados de inteligência;
    - 3ª geração: é baseado na análise de ameaças padrão da Mitre ATT&CK, linguagem comum usada para identificar, descrever e categorizar ameaças, que podem ser compartilhadas e rapidamente entendidas dispositivos de segurança de outros fabricantes.

## Aula 10 - Ameaças a redes comuns
- São atividades fora da lei ou maliciosas com a intenção de se aproveitar das vulnerabilidades de uma rede. As ameaças comuns são:
    - Spoofing: É quando o ator do ataque imita um dispositivo autorizado para roubar dados, espalhar malwares ou passar por sistemas de controle de acesso. Normalmente se troca o endereço MAC ou endereço IP;
    - Hijacking (sequestro): o agressor intercepta a conexão para descobrir, e potencialmente modificar as partes iniciais da conexão. MITM é um exemplo de hijacking. Modos para mitigar a ameaça é criptografia end-to-end e MFA.
    - Replay- Attacks: Ao contrário do sequestro, o ataque-replay intercepta uma transmissão válida e repete (ou reenvia) os dados posteriormente, para obter dados ilegalmente. Uma forma de previnir esse ataque é o token de validação única;
    - Dos (Denial of Service) - Tem por objetivo sobrecarregar uma rede/servidor, para deixá-la fora de serviço. Os tipos de DoS são:
        - Flood attacks: Quando agressores inundam os dispositivos alvos com solicitações, fazendo com que sobrecarreguem seus sistemas. Os tipos de flood attacks são:
	        - Smurf attack: o agressor "imita" o IP da vítima para enviar um ICMP (Internet Control Message Protocol) para uma rede, onde todos os dispositivos da rede respondem a requisição, travando o dispositivo da vítima;
    	    - Fraggle attack: parecido com o Smurf, o agressor "imitando" a vítima envia um pacote UDP para os endereços de broadcast do router, fazendo com que os dispositivos da rede retornem o tráfego para o dispositivo da vítima, o deixando indisponível;
            - SYN flood: é parte de um protocolo que ataca especificamente servers, proxies ou firewalls. O agressor cria um aperto de mão de 3 vias incompleto, inundando os recursos do dispositivo, que aguarda por uma conexão que está meio aberta;
            - Ataque árvore de Natal: é o envio de vários pacotes com as flags FIN, URG e PSH, onde o sistema de análise de pacote do router demora a analisar todos (grande quantidade), fazendo com que o router sobrecarregue e, em alguns casos, reinicie.
        - Ping of death: Um ping grande, de 65,345 bytes, é enviado, porém de forma fragmentada. Quando o alvo monta o pacote mal-feito, pode ocorrer uma sobrecarga de buffer ou crashar o sistema;
        - Teardrop: é o envio de pacotes com cargas modificadas (duplicadas ou aumentadas). Quando o alvo tenta remontar os fragmentos, os pacotes  se sobrepõe, crashando o dispositivo de rede;
        - DoS permanente: PDoS, é a exploração de vulnerabilidades de um dispositivo, que é usado para substituir o software por um firmware corrompido, levando a inutilização do dispositivo;
        - Fork Bomb: é a replicação de processos infinitamente, reduzindo a velocidade dos recursos ou crashando o sistema;
#### Previnindo ataques DoS
- Método de prevenção
    - Detecção de anomalia de pacote: Previne seguintes ataques:
        - Ping of death;
        - XMAS attack;
        - Teardrop attacks
    - Limitação de processos únicos: Previne:
        - Fork attacks;
    - Evitar encaminhamento de pacotes:
        - Smurf attacks;
        - Fraggle attacks;
        - Sensores DoS ou analise de comportamento de rede: utilizam sensores e IA para analisar comportamentos e previnir flood attacks em geral.
#### Melhores práticas
- Fechar portas desnecessárias, para evitar acessos indesejados;
- Corrigir vulnerabilidades conhecidas;
-  Segmentação de rede;
- Implatação dos princípios Zero-Trust

## Aula 11 - OT (Operational Technology) Security
- Operational Technology (Tecnologia Operacional) se refere ao hardware e software que controla dispositivos físicos, processos e infraestrutura.
- A OT Security protege um sistema operacional das ameaças digitais, para garantir a segurança, a confiabilidade e a continuidade dos processos físicos da operação.

#### Comparativo: Tecnologia da Informação (TI) vs. Tecnologia Operacional (TO)
| Tecnologia da Informação (TI / IT) | Tecnologia Operacional (TO / OT) |
| :--- | :--- |
| **Objetivo Principal**<br>Projetada para gerenciar o processamento de informações, armazenamento e transmissão de dados. | **Objetivo Principal**<br>Controlar processos físicos, operar máquinas e gerenciar a infraestrutura. |
| **Prioridades de Segurança**<br>Prioriza a confidencialidade e a integridade dos dados. | **Prioridades de Segurança**<br>Prioriza a confiabilidade, disponibilidade, estabilidade e segurança física (*safety*). |
| **Escopo de Atuação**<br>Suporta sistemas de negócios e comunicações corporativas. | **Requisitos de Tráfego**<br>Exige tráfego em tempo real (nenhum atraso é aceito). |

#### Componentes comuns em OT
- ICS (Industrial control system): usado para monitorar e controlar processos industriais. Os sistemas automatizam operações e provêm controle preciso em equipamentos e processos de produção. Eles incluem os seguintes sistemas:
    - DCS - sitema usado para controlar processos industriais complexos, como refinamento de petróleo ou produção de produtos químicos, onde muitos loops de controle trabalham simultaneamente;
    - PLC - são computadores industriais estratificados, que controlam e automam maquinário e processos no chão de fábrica. Eles executam lógicas pré-programadas, baseados em sensores de tempo real;
    - SCADA - supervisora o controle e aquisição de dados (Supervisory Control And Data) é um sistema que provê controle e monitoramento centralizado de processos industriais espalhados por grandes áreas geográficas, como sistemas de água, linhas de energia e óleodutos.
#### Ameaças comuns a OT
- Malware - usado no ambiente industrial para interferir no controle de processos, comprometer a integridade do sistema ou garantir acessos futuros;
- Ransomware - utilizado para obter vantagens financeiras, em ambientes de OT podem causar paralização da produção, interromper serviços críticos e impactar a continuidade operacional;
- Nation-State Actors & Advanced Persistent Threats (APTs) - grupos financiados por Estados que tem como alvo infraestruturas críticas, como energia, água ou setores de defesa, para conduzir espionagem, disrupção ou sabotagem;
- Insider Threat - risco de ator maliciosos ou negligência causados por empregados, parceiros ou fornecedores com acesso aos sistemas de OT. Esse tipo de ameaça são particurlarmente sérias, pois o acesso pode passar pelo perímetro de controle;
- Ataques a cadeias de suprimentos - comprometem um terceiro confiável, como um fornecedor ou um provedor de software, para se infiltrar no ambiente de OT. Por conta da necessidade de ferramentas externas específicas,esse vetor de ataque apresenta um risco crescente;
- Unauthorized Remote Access - com a maior interconectividade entre os ambientes de IT e OT, acessos remotos inseguros podem se transformar em um caminho para os agressores acessarem os sistemas de controle industrial.
#### Dificuldades na segurança da OT
- Legacy systems - muitos sistemas de OT são de décadas atrás, e não suportam ferramentas modernas de segurança;
- Zero downtime requirement - patches de segurança são difíceis de serem aplicados sem interromper a produção;
- Visibilidade limitada - muitos ambientes de OT não possuem ferramentas para monitorar tráfego de rede para detectar anomalias;
- Protocolos não-criptografados - protocolos industriais como o Modbus e DNP3 não foram criados com a segurança em mente;
- Arquitetura de rede plana - a falta de segmentação das redes na OT tradicional faz com que o movimento lateral seja fácil;
#### Benefícios da garantia de uma segurança de OT forte
- Continuidade operacional - garante a continuidade operacional industrial, pois qualquer parada não planejada por causa de um cyberattack pode ter consequencias graves para serviços, cadeia de produção e comunidades;
- Monitoramento continuo e visibilidade - detecta e alerta sobre ameaças, identificando dispositivos, testando o tráfego e mapeando a superficie de ataque para gerenciar sistemas e protocolos eficientemente;
- Sistemas de controle - controles como MFA, segmentação de rede, e sandboxing restringe os acessos não autorizados e contem a ameaça antes que se espalhe;
- Compliance regulatório - OTs com segurança forte , tem um sistema regulatório a seguir, ajudando as organizações a evitar penalidades, paradas ou dano na reputação;
- Segurança de equipamento e pessoaiscos de incidentes que podem por em perigo empregados, comunidades e infraestruturas críticas, previnindo mau funcionamento e operação em condições não seguras.

- Estrutura de segurança da OT
    - Governança e gerenciamento de risco - definir papeis, políticas e estratégia específica e implementar um framework de estrutura de risco;
    - Rede e controle de acesso:
        - Segmentar a OT a partir da IT usando firewalls;
        - Aplicação de menos privilégio dos acessos;
        - Assegurar e monitorar conexões remotas;
        - Gerenciar ativos e patchs de atualização com responsabilidade.
    - Monitoramento e detecção - manter visibilidade continua nas redes da OT;
    - Resposta e recuperação de incidentes:
        - facilita a capacidade de restauraçã;
        - Desenvolvimento e teste dos planos de resposta específicos das OTs.
    - Preparação da força de trabalho - para reduzir o risco relacionado ao ser-humano, é necessário treinamentos de consciência de segurança.
