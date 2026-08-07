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
