# Endpoint Security
## Aula 1 - IoT
É um dispositivo físico conectado a internet usando softwares, sensores e outras tecnologias.
Categorias de IoT:
- Dispositivos pessoais:
    - Smartwatches, celulares e câmeras;
    - Monitores cardíacos ou carros.
- Localização residencial:
    - Casas inteligentes;
    - Cidades inteligentes;
- Dispositivos industriais:
    - Manufatura;
    - Produção de energia;
    - Agricultura
### Desafios da segurança endpoint
O número de dispositivos endpoint aumentou e o alcance da conectividade também, sem um aumento correspondente do alcance da segurança:
- Maior superfície de ataque: com o aumento da superfície de ataque, uma brecha em um dispositivo IoT pode levar ao comprometimento de outros dispositivos que compartilham a mesma rede. E muitos dispositivos IoT:
    - Tem uma segurança de criptografia pobre ou nenhuma;
    - Tem senha muito fraca ou mantém senha padrão.
- Criação de botnets: Os dispositivos de IoT são alvos para criação de botnets para:
    - Futuramente comprometer dispositivos locais e outras redes;
    - Consequencias:
        - Perda de dados;
        - Infraestrutura de ataque;
        - Violação de privacidade.
### Segurança de dispositivos IoT
O maior desafio é manter uma conexão segura com a internet/redes, já que são dispositivos não conhecidos, que são construidos para gerenciar uma infraestrutura já existente.
É importante conectar os dispositivos em uma rede isolada, até que se possa resgistrar com segurança como dispositivos válidos.
- Identificar o dispositivo;
- Registrar suas informações;
- Conectar todos os dispositivos desconhecidos em uma rede isolada e identificá-los usando suas informações;
- A maioria dos IoT não suporta instações de softwares de segurança tradicionais.
### Estratégias corporativas
- Aprender e categorizar todos os dispositivos, incluindo os IoT;
- Dividir os dispositivos em grupos por necessidades de segurança e conexão;
- Empresas devem colocar apenas os dispositivos que precisem conversar com outro na mesma estrutura de rede.
## Aula 2 - Técnicas de segurança de endpoints
- Controles administrativos;
    - Senhas;
    - Restrições de usuário;
    - PoLP (Pricípios de menos privilégios).
- Proteção local do endpoint:
    - OS e startup hardening;
    - Gerenciamento de boot;
    - Criptografia de segurança de disco;
    - Prevenção de perca de dados (DLP - Data Loss Prevention).
- Manutenção do endpoint:
    - Auto-atualização e patching;
    - Checagem de políticas;
    - Backups.
- Monitoramento do endpoint:
    - EPP - Plataforma de proteção do endpoint;
    - IDS - Sistema de detecção de intrusão;
    - EDR - Detecção e resposta do endpoint.

