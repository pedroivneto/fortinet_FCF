# Segurança de dados e aplicações
## Aula 1 - Proteção de dados
Na proteção de dados, devemos ter salvaguardas de segurança e privacidade para:
- Dados em descanso;
- Dados em uso;
- Dados em trânsito.
Para pode garantir:
- Confidencialidade;
- Disponibilidade;
- Integridade;
- Não-repudiação.
Logo, proteção de dados é a união de segurança com privacidade.
### Proteção de dados
Segurança dos dados incluem:
- Manter a integridade, digital ou física dos ativos;
- Garantir a integridade dos dados através de todo seu ciclo de vida;
- Autorização adequada de acessos e usos;
- Soberania dos dados;
- Privacidade dos dados.
### Tipos de dados
Os tipos de dados mais comuns:
- CUI (Controlled unclassified Information)
    - Criado ou possuído pelo gonverno;
- PII (Personally Identifiable Information)
    - Inclui endereços ou dados biométricos
- PHI (Protected Health Information)
    - Relacionados a informações médicas confidenciais
- PCI (Payment Card Information)
    - Os administradores de cartão são responsáveis pelos pagamentos eletrônicos
- Sensitive Institutional Data
    - Dados legais, regulatórios, administrativos e requerimentos contratuais
- IT Security Information
    - Dados sensíveis relacionados a proteção da rede
- Exporte Control Records
    - Dados relacionados ao comércio de exportação
- Student Education Records
    - Mantido por uma instituição ou agência educacional
### Riscos aos dados
- Exposição acidentã dos dados
    - APIs permitem aplicações a interagirem sem nenhuma ação do usuário;
    - Eles podem prover acesso não autorizado a dados sensíveis
- Compartilhamento de dados sem intenção
    - Quando uma mensagem de phishing é enviada para enganar o destinatário
- Infecção por malware - criados para comprometer a confidencialidade, integridade e disponibilidade dos dados:
    - Malware: software criado para parar um dispositivo para obter acesso não atorizado a informações privadas;
    - Ransomware: bloqueia o sistema e ameaça a vítima com a exposição de dados ou o bloqueio permanente, a menos que um resgate seja pago;
    - Doxware: é um tipo de ransomware que ameaça a divulgação de dados sensíveis, constrangedores ou incriminadores, a não ser que um resgate seja pago;
    - Leakware: um programa que coleta dados sem que seja notado, e envia ao criminoso virtual. Quando o mesmo coleta informações suficientes, demanda o pagamento de um valor para a não divulgação dos dados.
### Ciclo de vida dos dados
O ciclo de vida dos dados consistem em 5 estágios:
- Criação
- Armazenamento
- Uso
- Arquivamento
- Destruição
Durante o ciclo de vida dos dados, eles estão em constante movimento, nos seguintes passos:
- Descanso > Trânsito > Em uso;
### Táticas e técnicas da proteção dos dados
- Trainamento: ajuda o entendimento de todos da importância da proteção de dados. Ajuda no entendimento claro e na aplicação das políticas de uso de dados da empresa;
- Ofuscação de dados: ou mascaramento de dados, minimiza o valor dos dados sensíveis a ação de intrusos não autorizados. Diferencia a disponibilidade da informação de acordo com os níveis de autorização;
- Criptografia: Aumenta a integridade de confidencialidade dos dados;
- Resiliência dos dados: importante para a continuidade e disponibilidade dos dados na empresa. Backups regulares permitem que os dados sempre estejam disponíveis e acessíveis;
- Destruição: deve ser feito com o procedimento correto, como erasure (apagamento, destriução), que sobrescreve os dados com informações sem importância ou padrões pseudo-aleatórios para destriur completamente o arquivo;
- Prevenção de perda de dados: Permite a detecção e prevenção de aberturas para ataque, roubo ou destruição indesejada de dados.
### Boas práticas
- DLP (Data Loss Prevention)
    - Identifica informações sensíveis;
    - Previne compatilhamento acidental de dados;
    - Audita e monitora movimentação de dados;
    - Educa os usuários sobre conformidades.

## Aula 2 - Privacidade dos dados
### Privacidade dos dados
Se refere à devida utilização de dados pessoais e outros dados sensíveis, onde:
* O público:
  * Tem a expectativa da privacidade dos seus dados;
  * O direito de ter o controle sobre os seus próprios dados;
  * As empresas tem a obrigação de manter a privacidade dos dados;
* As empresas:
  * Informar o processo de coleta, compartilhamento, arquivamento e exclusão de dados sensíveis;
  * Manter níveis aceitáveis de risco;
  * Cumprimento com as regulações e leis de proteção dos dados.
### A importância da privacidade dos dados
É importante para as empresas manterem a privacidade dos dados pois:
* Os dados são ativos de extrema importância;
* Controle individual sobre os dados;
* As empresas devem ser transparentes sobre a forma em que eles gerenciam seus dados;
* Governos reconhecem direitos individuais dos dados;
* Atualmente, a coleta de dados se torna fácil com os avanços tecnológicos;
* O não cumprimento de regras podem gerar muitas consequencias, como processos jurídicos e perca de confiança no mercado.
### Funções das empresas na privacidade dos dados
Pesquisas proprietárias, recursos de RH e informações financeiras devem ser protegidas de exposição:
* Identificando os dados sensíveis;
* Identificando as funções autorizadas, usuários e políticas;
* Coletando e reportando sobre dados comprometidos;
* Desenvolvendo procedimentos de resposta para invasões;
* Implementando medidas de criptografia para a obfuscação dos dados.
As informações devem ter níveis de classificação:
* Restrito: um tipo altamente sensível de dado, e deve ser limitado e seu uso deve ser limitado a consulta que são estremamente necessários ao desempenho de suas funções;
* Confidencial: é um dado a nível de equipe, e seu uso deve ser estritamente dentro do negócio;
* Interno: é um dado a nível de empresa e deve ser protegido com controle limitado;
* Público: é um dado que pode ser amplamente compartilhado com qualquer pessoa.
As políticas pertencentes a classificação e uso dos dados devem ser seguidas.
### Leis e regulações
As leis e regulações de privacidade de dados garantem que indivíduos tenham controle sobre seus dados.
Algumas leis e regulações vigentes:
* GPDR (General Data protection Regulation);
* ISO 27701 - padrão internacional para gerenciamento e privacidade de dados;
* NIST (SP 800-53) - provê um catálogo de segurança e privacidade para proteção e controle contra riscos de privacidade;
* SOC 2 (System of Organizations Control) - requerimentos para empresas que fornecem SaaS (serviços de nuvem);
* PIPEDA (Personal Information and Eletronic Documents Act) - lei canadense de privacidade para o setor privado;
* CCPA
* HIPAA
* PCI DSS

## Aula 3 - Segurança de e-mail gateway
Spam: Mensagens não solicitadas e irrelevantes que são enviadas para vários destinatários;
Phishing: Ataque de engenharia social que usa o e-mail como caminho e tem como alvo um público amplo e indiscrimidado de pessoas.
Alguns dados sobre o phishing:
- em 2004, 176 ataques de phising foram identificados;
- em 2012, o número de ataques subiu para 28.000;
- Em 2022, para 500 milhões de ataques;
- A média do custo por invasão é de 4.35 milhões de dólares;
### O que é Secure Email Gateway (SEG)
É uma solução tecnológica criada para proteger empresas de e-mails que podem ser ameaças e garante a segurança e privacidade das comunicações por e-mail.
Possui algumas características:
- Filtro de conteúdo: Controla e gerencia os tipo de conteúdo que pode ser acessados e compartilhados na rede, e inclui:
  - Correspondência de palavre chave;
  - Expressões regulares;
  - Checagem de pacotes profunda (deep package inspections);
  - Analise de contexto.
- DLP (Data Loss Prevention): Previne o vazamento não autorizado ou acidental de informações sensíveis ou confidenciais de uma empresa
- Filtros spam: Gerencia o recebimento de e-mails e elimina os que contem os potencialmente perigosos, reduzindo a quantidade de spam na caixa de entrada. Os spams possuem:
    - Características:
      - Endereços de remetentes suspeitos;
      - Uso excessivo de palavras-chave;
      - Padrões de spam conhecidos;
      - Endereços de IP com reputação ruim.
    - Tecnologias de filtros de spam:
      - Bayesian filters: um filtro estatístico, baseado na teoria Bayesiana, lidando com probabilidades e incertezas;
      - Lista de negados: blocklist, uma lista de itens ou entidades que são proibidas ou negando acesso a determinados sistemas específicos;
      - Lista de permitidos: o contrário da deny list;
      - Machine learning algorithms: algorítimos de IA criados para reconhecerem padrões, realizar inferências para aprender e realizar a filtragem.
- Authentication and identity verification: autentica e verifica a identidade para previnir a cópia do e-mail ou a imitação do mesmo;
- Malware: escaneia os anexos dos e-mails e links para previnit conteúdos potencialmente mal intencionados de chegar a caixa de inbox;
- Criptografia: criptografa as mensagens, ou até mesmo assina digitalmente, para assegurar a confidencialidade e não-repudiação da mensagem.
### Sender Policy Framework
- SPF verifica o endereço de IP do rementente, para previnir o roubo do endereço de e-mail.
- Domain Keys Identified Mail (DKIM) - Uma tecnologia de autenticação e anti-phishing que verifica a autenticidade de mensagens e legitimidade dos remetentes.
- Domain-based Message Authentication, Reporting and Conformance (DMARC) - Um protocolo de autenticação e framework usado para aumentar a segurança na comunicação por e-mail, permitindo os e-mails dos remetentes especificarem suas políticas e instruções de como os destinatários lidarem no caso de falha na autenticação.

## Aula 4 - WAF - Web Application Firewall
WAF é uma aplicação ou software que monitora os tráfegos HTTP(S) e pode bloquear tráfegos maliciosos de de e/ou para uma aplicação web.
Aplicações WAF podem parar ataques que se originam da web, que podem ser:
* SQL Injection;
* File inclusion;
* Cross-site scripting;
* Desconfiguração de segurança.
## Aula 5 - Filtros de conteúdo
Um processo para triar ou restringir o acesso a e-mails, páginas da web, executáveis e outros itens suspeitos ou indesejados.
É um processo incluso em firewalls, projetados para bloquear conteúdos:
- Perigosos;
- Ilegais;
- Inapropriados.
### Tipos de filtros de conteúdo
- Filtros de pesquisa web: Classifica o conteúdo de imagem ou texto em: Estrito, moderado ou desligado. Após a configuração de restrição, uma IA irá analisar o conteúdo da pesquisa e trará o retorno de acordo com a configuração do filtro, podendo classificar os resultados como:
    - Seguro
    - Moderado;
    - Inapropriado;
    - Rejeitado.
- Filtros de e-mails: Lê o cabeçalho do e-mail e compara com o RBLs (lista de nomes de domínios, servidores de emails ou endereços de IP), para averiguar se o e-mail é seguro. Além dessa verificação, o corpo do email é verificado, como também os anexos, procurando por padrões que possam indicar um potencial ataque.
- Filtro baseado em DNS: Verifica se o site que o usuário está tentando se conectar está em um blocklist. Caso esteja nesse blocklist, o servidor DNS retorna uma mensagem de "website blocked"
- Filtros web: Funciona da mesma forma como filtro baseado e DNS, porém com uma função adicional, que é a categorização. Como exemplo, uma escola pode manter uma lista de URLs que serão bloqueadas para o acesso indevido de crianças.
### Benefícios dos filtros de conteúdo
- Bloqueia acesso a sites conhecidos por conter malwares e protege os dados e usuarios de atividades maléficas.
- Identifica phishing ou exploit kit (código projetado para explorar vulnerabilidades de sites e navegadores, através de extensões e plugins), bloqueando o acesso antes do acionamento do download do malware.
- Aumenta a banda de internet e melhora as conexões para todos os empregados.
- Pode aumentar a produtividade do empregado.

## Aula 6 - Aplicando técnicas de endurecimento (hardening)
Hardening:
- Definido por vários padrões e regulamentações de cybersecurity.
- Minimalização de vulnerabilidades e redução da superfície de ataque.
- Proteção da integridade da aplicação e salvaguarda dos dados sensíveis.
### Técnicas para aplicação de hardening
- Uso específico de ferramentas aprovadas pela empresa
- Treinamento dos empregados sobre comportamentos seguros no ambiente de trabalho;.
- Tipos de cuidados:
    - Web browser: A empresa deve recomendar um navegador estável e os empregados são responsáveis pela instalação do navegador aprovado;
    - Cookies: Os usuários devem:
        - Limpar os cookies;
        - Permitir apenas os cookies requisitados do trabalho;
        - Configurar opções de segurança avançados de cookies.
    - Add-ons: Devem apenas instalar add-ons oficiais e que forem aprovados pela empresa;
    - Pop-up blocker: Pop-ups podem conter malware, logo os empregados devem:
        - Ativar o bloqueador de pop-ups;
        - Criar uma lista de permissão, com os sites que são permitidos abrir pop-ups.
    - Active content: Os empregados devem tratar os active contents com precaução:
        - Active contents são pequenos programas que aplicações usam para performar funções específicas, com mostrar um calendário ou tocar um vídeo.


