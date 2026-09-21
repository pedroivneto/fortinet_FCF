# SD-WAN

### Estrutura SD-WAN
> SD-WAN (Software defined - Wide Area Network) utiliza o gerenciamento centralizado para gerenciar os links da organização.

---

### Funcionamento das SD-WANs
Monitora a performance das conexões de WAN e regula os tipos de tráfego para garantir a consistência de alta velocidade e otimizar a conectividade como um todo.
Permite um roteamento de tráfego baseado em aplicação, permitindo um ajuste fino para aumentar velocidade de comunicação de aplicações críticas do negócio.
Diferente de roteadores WANs convencionais, o modelo suporta aplicações localizados em data centers, nuvens públicas ou privadas, e SaaS como AWS, Dropbox e outros

---

### Vantagens da utilização de SD-WAN
* **Orquestração centralizada**: centralizam o gerenciamento de deployments, configurações e operações, permitindo que os adminitradores da rede gerem e modifiquem regras de segurança em tempo real, de acordo com a evolução das demandas da rede. Essa característica ajuda a reduzir a complexidade e o requerimento de recursos que a organização precisa para gerenciar sua rede;
* **Acesso direto a nuvem**: Elimina a necessidade de backhauling (enviar o tráfego para ser inspecionado pelo firewall da matriz), permitindo acesso direto a serviços de nuvem críticos para todos os usuários, independente da sua localização, eliminando a necessidade de rotear o tráfego de uma filial através do data center, independente do destino atual;
* **Melhor performance para aplicações**: SD-WANs podem ser configuradas para priorizar tráfegos críticos para o negócio e serviços de tempo real, como VoIP, podem ser direcionados para a rota mais eficiente. Ter várias opções de movimentação de tráfego ajuda a reduzir a perca de pacotes por conta de circuitos sobrecarregados e a latência devido ao tráfego pesado, melhorado a performance e a experiência do usuário;
* **Agilidade de negócio melhorada**: Utilizando a SD-WAN, os administradores de redepodem realizar deploys de updates para toda a rede simultaneamente, permitindo a organização de responder as mudanças de negócios suavimente;
* **Economia**: Permite que o tráfego seja roteado eficientemente atraǘes de multiplos canais, incluindo MPLS (*Multiple Protocols Label Switching*) e a internet pública por LTE e banda larga. Isso reduz a necessidade de aumentar a largura de banda com links caros, como os MPLS;
* **Segurança melhorada**: Com as características de segurança integradas e a habilidade de restringir acesso a rede, organizações podem se proteger de ameaças internas e externas de forma mais eficiente. É recomendado usar soluções de SD-WAN que contam com um amplo leque de recursos de segurança, como NGFW, IPS, criptografia, antivírus e sandboxes, que ajudam a previnir perca de dados, downtime, violações de regulação e responsabilidades legais.

---

### Evolução da tecnologia SD-WAN
* **Fase 1 - necessidade de maior largura de banda**: As técnicas básicas de balanceamneto de carga permitiram que as redes fizessem aplicações inteligentes para decisões em links híbridos de WAN, incluindo provedores de serviços, banda larga ou rede móvel (LTE);
* **Fase 2 - Necessidade de maior performance**: Durante essa fase, alguns recursos foram adicionados, como failover / Failback em ambiente virtualizado (comutação por falha / reversão após falha), e roteamento por aplicação, e com os recursos, foi reduzido os atrasos associados a instalação de MLPS e a unificação de um painel de controle simplificado para os processos de operação;
* **Fase 3 - Necessidade de unificar a infraestrutura de segurança**: A evolução da SD-WAN permitiu a unificação da infraestrutura de segurança, tendo reduzido o custo operacional e facilitando o gerenciamento da rede.

---

### SD-WAN segura
> Secure SD-WAN é a combinação das funções de um firewall e SD-WAN em um único dispositivo, provendo um aumento da segurança da rede e simplificando as tarefas do administrador.

---