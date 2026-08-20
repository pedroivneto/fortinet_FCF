# Segurança na nuvem e virtualização
## Aula 1 - Visão geral sobre virtualização
Virtualização é o processo de reproduzir algo virtualmente, como sistemas operacionais (OS), servidores ou dispositivos de rede.
A virtualização é um software que emula uma máquina física. De um servidor host com grande capacidade de hardware consegue se virtualizar 3, 4 ou 5 máquinas.
### Benfícios da virtualização
- Eficiência e escala econômica;
- Ambientes virtualizados economizam energia e reduzem os custos;
- Criação de ambientes de teste e produção;
- Melhoria de mecanismos de recuperação de desastres;
- Gerenciamento rápido e fácil, como o isolamento dos ambientes de teste e produção.
### Hypervisor
É um software que permite o lançamento e gerenciamento de máquinas virtuais. Responsável por dividir as capacidades de hardware e recursos do sistema do host e gerenciar a alocação desses recursos nas VMs.
### Tipos de Hypervisor
A principal diferença entre os tipos de hypervisors (tipo 1 e tipo 2) é a forma como cada um lida com a alocação de recursos de hardware.
- Tipo 1:
    - Rodam direto no hardware do computador, interagindo diretamente com a CPU, memória e armazenamento físico;
    - Desenvolvem tarefas que involvem a virtualização, como o gerenciamento e a divisão dos recursos;
    - Permite a implementação de várias VMs para rodar no servidor;
    - Usado em data centers e em servidores com hardware de alta performance, designados a rodar várias VMs;
    - Rodam em um hardware dedicado e precisam de um console de gerenciamento;
    - Fornecedores e produtos incluem: Oracle VM Server, ESXi, Hyper-V, Kernel-based VM (KVM) e outros.
- Tipo 2:
    - Conhecido como hypervisor hospedado;
    - Atua como um gerenciador da VM;
    - Instalado como um software de aplicação;
    - Roda em OS convencionais como Windows, Linux ou macOS;
    - Tem suporte para VMs convidadas, coordenando chamadas para recursos dos hosts;
    - Não é instalado no hardware, mas no OS, e coordena a utilização desses recursos;
    - Fornecedores e produtos incluem: VMWare Fusion, Oracle Virtual Box, Oracle VM for x86, Solaris Zones, Parallels Desktop, VMWare Workstation Pro e outros.

## Aula 2 - Visão geral sobre nuvem
A nuvem se refere a software e serviços oferecidos por empresas que se especializam disponibilizar os recursos dos seus data centers para serem acessados através da internet.
### Modelos de serviço
Existem 3 modelos de serviços baseados na nuvem:
- On premises - A empresa gerencia todo o seu sistema de TI; 
- IaaS (Infrastructure as a Service) - A empresa gerencia seus dados e softwares. A manutenção do equipamento é realizada pelo fornecedor;
- PaaS (Plataform as a Service) - A empresa gerencia apenas a aplicação e os dados, o restante fica a cargo do fornecedor;
- SaaS (Software as a Service) - A empresa gerencia apenas seus dados, o restante (rede, armazenamento, servidores, virtualização, OSs, bancos de dados e aplicações) ficam a carogo do fornecedor.
### Quem é responsável pela segurança?
A segurança é uma responsabilidade compartilhada entre o fornecedor e o cliente.
- Fornecedores - são responsáveis por:
    - Armazenamento;
    - Redes;
    - Infraestrutura;
    - Computação.
- Clientes - são responsáveis pelo restante:
    - Dados;
    - Aplicações;
    - Firewalls;
    - Criptografia.
Segundo estimativas da Gartner, 99% das falhas de segurança da nuvem são de responsabilidade do cliente, ocasionados por erro humano e má configuração de segurança.

## Aula 3 - Segurança da nuvem
### Segurança para IaaS
O fornecedor é responsável pela segurança da infraestrutura do serviço, porém o cliente, que irá utilizar essa infraestrutura, é responsável pelos acessos, tráfego de rede e aplicações de dados.

## Aula 4 - Riscos de VMs
Uma virtualização segura é feita por processos, procedimentos e políticas.
Um dos pontos a serem considerados é a segurança do hardware e dos hypervisors. Um servidor virtual pode conter milhares de VMs, então é vital manter a segurança física e um controle de ambiente apropriado.
Como o hypervisor tem acesso e controle as milhares de VMs, um ataque bem sucedido causará grande impacto na infraestrutura virtual, logo é de extrema importância controlar acessos e aplicar medidas de segurança.
A disponibilidade, escalabilidade e elasticidade permitem que empresas reduzam seus custos com infraestrutura, porém criam desafios relacionados a segurança, como:
- tempo de atividade do dispositivo;
- armazenamento dos dados;
- segurança da máquina
### Assegurando um ambiente virtual
Se começa com a prática similar ao de assegurar os dispositivos tradicionais, como:
- Reparo (patch) as OS e as aplicações regurlamente.
- Usar gerenciamento de acessos e políticas de senhas fortes;
- Instalar firewalls virtualmente no ambiente em linha com a proteção da VM;
- Implementar a segmentação de rede para reduzir a superfície de ataque.
Como práticas adicionais, temos:
- Limitar a conectividade entre a VM e o hospedeiro (host);
- Remover peças virtuais de hardware desnecessárias;
- Evitar que o aumento da virtualização, implementando um gerenciamento de VM são, planejado e supervisionado;
- Restringir acesso físico e administrativo ao hypervisor.
### Ameaças da virtualização
- VM Escape - quando um redhat roda um código em uma VM, que dá acesso ao hypervisor, que consequentemente, libera o acesso as outras VMs nesse host. Os métodos de prevenção são:
    - Assegurar o hypervisor e as VMs com atualizações e pacthes de segurança;
    - Uso de forte controle de acesso e senhas;
    - Permitir apenas a instalação de aplicações confiáveis e verificadas.
- Data remanence - São os vestígios de dados que ficam nas VMs, que podem ser roubadospelos redhats. As formas de prevenir são:
    - Implementar um processo seguro e apropriado para a destruição desses dados:
        - Overwriting (sobrescrita): reescrever sobre um dado , já que os data centers são planejados com prevenção de perca de dados, e a sobrescrita não irá apagar o dado;
        - Degaussing: modifica o campo magnético do HD para destruir ou embaralhar os dados, que ficam irrecuperáveis e destrói o HD;
        - Cripto-erasing: em um armazenamento criptografado, esse método remove a chave existente, pondo outra no lugar, e todos os dados criptografados que usavam a chave antiga é renderizado como irrecuperável,mas o dispositivo ainda pode ser usado;
        - Sheredding: uma máquina industrial que destrói fisicamente o drive, não deixando possibilidade de remontagem dos dados.
## Aula 5 - Ameaças comuns a nuvem
Ameaças da nuvem:
- Autenticação e autorização: Garantir métodos de autenticação modernos para proteger dados sensíveis e máquinas virtuais;
- VM creep: Uso frequente de auditoria em Vms e dados baseados em nuvem, para diminuir os rastros de uso e assim reduzir a superfície de ataque;
- Armazenamento desconfigurado: Armazenamentos em nuvem tem regras, autenticações e lista de controle de acesso, que deve ter uma segurança robusta e os conteiners, discos, buckets e blobs devem ser configurados com o intuito de previnir a perca de dados e o excess de uso de recursos;
- DLP: Leva em consideração como as empresas de gerenciamento de cloud lidam com o armazenamento de dados, direitos e propriedade;
- Conectividade: Sempre utilizar protocolos seguros de conectividade, como HTTPS ou SSH, criptografar e assegurar os dados que estão sendo transferidos entre a nuvem e as aplicações e armazenamentos, utilizando esses protocolos seguros;
- Improper logging and monitoring: Manter um log de segurança, sendo capaz de centralizar essa coleção de dados em um SIEM (Security Information and Event Management) ou outro ponto de log, ajuda a manter a segurança e ajuda a resposta rápida a ameaças que afetem o ambiente de nuvem;
- Direitos e propriedades a dados: É um assunto complicado, pois as propriedades sobre os dados dependem de fatores como:
    - País onde o serviço de nuvem é usado;
    - País onde a empresa provedora está alocada;
    - Assinatura do SLA (Service Level Agreement).
### Autenticação e autorização
Opções de autenticação e autorização como OAuth e SAML dão suporte a interoperabilidade entre várias companhias e serviços e segurança dos dispositivos, podendo simplificar a administração que suporta a autenticação de banco de dados para ambas as opções, local e nuvem.
### Armazenamento de dados e segurança
É um dos recursos mais expostos a riscos na nuvem. Para reforçar a segurança, existe um conjunto único de regras e políticas reforçadas por:
- políticas de serviço local do provedor;
- sistema de IAM (Identity and Access Managemant);
- lista de controle de acesso ao armazenamento (ACLs);
- serviço de autenticação centralizado;
- princípio de menor privilégio.
A auditoria e remoção de qualquer VM, armazenamento e outros serviços na nuvem que aumentam com o tempo e não são removidos ou deletados após o uso ajuda a:
- Reduzir o número de recursos em uso da nuvem;
- Previne que sistemas não deletados e velhos se tornem ameaças a segurança em potencial;
- Previnir um ponto de ataque inicial de hacker maliciosos.
Os dispositvos de segurança da nuvem, como CNP (Cloud Native Protection) e CNAP (Cloud Native Application Protection) possuem mecanismos como DLP, Auditing e Risk Assessment.

## Aula 6 - CNP-CNAP (Ferramenta de segurança na nuvem)
### SECaaS
Permite que um único fornecedor forneça multiplos dispositivos e ferramentas de segurança, todas integradas em uma plataforma CNP.
Disaster recovery, virus scanning, intrusion protection e authentication são algumas das ferramentas disponíveis.
### SASE (Secure Access Service Edge)
Tem o objetivo de se extender além das simples conexões entre os escritórios e as aplicações em nuvem.
O SASE combina conectividade segura de SD-WAN (software defined WAN) com uma borda de serviço de segurança (security service edge) contendo produtos SECaaS (Security as a Service) para validar e proteger conexões com aplicações hospedadas.

## Aula 7 - Securing the Cloud
### Protegendo servidores na nuvem
Para a proteção dos servidores em nuvem, podem ser usados WAF (Web Application Firewall) ou CNF (Cloud Native Firewall) para separar sua rede virtual da rede da nuvem, e assim aplicar suas políticas, regras, realizar inspeção de tráfego e regras e gerenciamento de autenticações, DLP (Data Loss Prevention) e sistema de detecção de intrusão (IDS).
Dentro dessa rede de proteção, pode-se ter scanners DLP, motores de antivírus e sandboxes, realizando pré-checagens antes das solicitações chegarem aos servidores.
A replicação dos métodos de segurança para outros serviços de nuvem se torna fácil, ou adicionar outra camada de segurança com o mínimo de esforço de lançamento e custos administrativos.
