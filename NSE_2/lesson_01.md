# NGFW - Next Generation FireWall
> É um dispositivo que processa o tráfego de dados, aplicando regras de filtragem e bloqueando tráfegos potencialmente perigosos de entrar em uma rede.

Um NGFW combina as ferramentas de um firewall tradicional com capacidades extras, como analisar, descriptografar e filtrar o tráfego da rede.
Um NGFW pode filtrar um tráfego por aplicação e realizar uma inspeção de pacote, que é mais que um firewall tradicional faz.

### Como um firewall tradicional trabalha
Os firewall tradicionais trabalham na camada de rede e transporte, e inspecionam:
* Fonte e destino de endereços da rede;
* Port numbers;
* Protocolos,
E com base nesses dados, decide encaminhar ou não o pacote.
Como muitas aplicações utilizam as mesmas portas e protocolos, um conteúdo malicioso pode ser enviado escondido, sendo necessário uma camada a mais de segurança.

### Como um NGFW trabalha
Os NGFWs também trabalham nas camadas de rede e transporte, porém foi adicionado uma nova proteção, passando a trabalhar também na camada de aplicação.
Trabalhar na camada de aplicação permite incluir novas funcionalidades, como o DPI (deep packet inspection)
O DPI examina o conteúdo do pacote (tanto o corpo quando o cabeçalho) quando passam pelo checkpoint da rede. Caso algum gatilho seja acionado, o pacote é enviado para uma sandbox para análise futura e evita uma possível infecção.

### Como NGFWs mitigam ameaças
Os NGFWs possuem conscientização de aplicações (reconhecimento de aplicações), o que significa que eles controlam o tráfego com base em aplicações específicas, em vez de portas.
Pode implementar um controle de acesso a uma organização.

### Funcionalidades
* **Segmentação de rede**: Usa várias formas de isolar usuários, dispositivos e aplicações baseadas nas necessidades de negócios. Com a segmentação, ao invés de manter uma rede plana, NGFWs removem um único ponto de entrada, dificultando o acesso de cybercriminosos e evitando a propagação de ameaças através da rede;
* **Controle de acesso**: integra IAM (manutenção de acesso e identidade) para restringir acesso de aplicações baseadas em usuários ou políticas de dispositivos. O IAM permite a organização de reforçar a política de zero trust através da rede, garantindo acesso correto aos usuários. O controle de acesso ajuda a previnir roudo de informações e ataques maliciosos;
* **SSL decryption**: descriptografa e inspeciona tráfego criptografado, buscando conteúdo malicioso, então recriptografa o dado antes de encaminhar para seu destino;
* **Sandboxing:** Envia arquivos ou aplicações suspeitas para um ambiente sandbox, para uma análise futura;
* **Capacidade de IA**: pode adotar um sistema de proteção contra ameaças impulsionado por IA permite uma detecção em tempo real e atualizado sobre as últimas ameaças de cybersecurity. Isso é necessário para proteção contra ataques zero-day, o que firewalls tradicionais não conseguem lidar.
