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

## Aula 3 - Monitoramento de endpoints
Endurecendo a segurança do endpoint:
- Controles administrativos:
    - Senhas;
    - Restrições de usuários;
    - PoLP (Princípio de menor privilágio).
- Mantenção de endpoints:
    - Patching e atualizações automáticas;
    - Checagem de políticas;
    - Backups.
- Proteção local de endlpoints:
    - Endurecimento do sistema operacional e inicialização;
    - Criptografia de disco rígido (HD);
    - Prevenção de perda de dados (DLP).
- Monitoramento de endpoints:
    - EPP (Plataforma de Proteção Endpoint);
    - IDS (Sistema de detecção de intrusão);
    - EDR (Detecão e resposta de endpoints).
### EPP
Plataformas de proteção contínua a dispositivos finais de rede. Podem fazer:
- Verificações de versões de sofware e firmware;
- Escanear sistemas locais por vírus e malware;
- Fortalecer a prevenção de perca de dados e outras políticas definidas pela empresa.
Os EEPs são uma medida de defesa contra ataques maliciosos, ajudam os administradores a manter os softwares uniformemente atualizados por toda a empresa e permite um monitoramento e visibilidade básica do sistema.
### EDR
Está constantemente verificando o sistema para detecção de IOC (indocador de comprometimento) - se o sistema detecta alguma conexão inapropriada, arquivo suspeito ou comportamento estranho, o sistema bloqueia a ação e emite um aviso. Isso ajuda a detectar e parar ataques como ransomware e ataques zero-day.
- Utiliza IA e uma grande base de dados para prever e reconhecer arquivos e programas suspeitos;
- Envia alertas para outros endpoints conectados para que eles possam bloquear atividades suspeitas, antes que eles possam ser executados, gerando uma resposta imediata a ataques de zero-day e outros ataques não definidos.
- Possui ferramentas que ajudam a reunir dados de novas ameaças. Sistemas suspeitos são colocados em quarentena, para evitar infecções.
### Assegurando dispositivos desconhecidos e BYODs
Um dos maiores desafios é conectar um dispositivo desconhecido em uma rede estabelecida.
Além de sistemas de monitoramento instalados préviamente, é importante conectá-los em uma rede isolada, para que eles possam ser avaliados e identificados.
Após conectado em uma rede isolada, o dispositivo para por duas etapas:
- Registro de informações:
    - Hostname (nome do dispositivo);
    - Serial number;
    - MAC/ static IP.
- Instalação de um software de segurança.
Desabilitando o acesso de dispositivos desconhecidos:
- Usuários desconhecidos são forçados a se registrar;
- Previne agressores de tentar inserir seus próprios dispositivos na rede.


