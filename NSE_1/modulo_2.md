# O panorama das ameaças
Conhecendo o panorama de ameaças digitais nos dá uma perspectiva sobre os principais pontos de defesa, identificando alvos, objetivos e, principalmente, os realizadores dos ataques.

## Agentes das ameaças
Pessoas (hackers) que, através de um computador, tenta te impedir de usar um computador ou acessar informações que você está autorizado e que está armazenado ou em trânsito entre dispositivos.
- Tipos de agentes - Não são um grupo homogênio.:
    - Explorador - o curioso: Esse tipo de agente não tem maldade, mas uma busca por notoriedade, mostrar que consegue furar bloqueios de segurança. Tem curiosidade em buscar falhas de seguranças nas aplicações, e o principal método hack é o Phishing que tem 3 variantes:
        - Spear phishing (pesca com lança): utiliza e-mails com links mal intencionados
        - Smishing - utiliza a mesma forma de ataque, por mensagens de texto ou SMS
        - Vishing: por ligação, utilizando VoIP e alterando o ID da ligação, para parecer uma empresa legítima;
    
    - Hacktivista - acredita em uma causa externa: motivado por uma ideologia e cria sua persona movido por uma força emotiva. A ideologia os fazem se mover em grupo e focar em uma determinada empresa, que para eles, fazem coisas ruins (causa externa). O hacktivsmo exige anonimato. Uma estratégia comum é o ataque DDoS (Distributed Denial of Service), que tem os seguintes passos:
        1. Criação de um botnet secreto e um servidor C&C (servidor de comando e controle) - que irá comandar todos os nós de botnets;
        2. Criação de um malware que será instalado nos computadores de uso regular (ao redor do globo);
        3. O servidor C&C irá enviar instruções para milhares de nós de botnets para que, cada computador com o malware envie mensagens para o servidor alvo, sobrecarregando o servidor e fazendo com que o mesmo pare de responder;

    - Cyber-terrorista - mais parecido com o hacktivista (movido por ideologia): Ao contrário dos hacktivistas, que focam seus ataques a empresas "malvadas", os cyber-terorristas voltam sua ideologia para a sociedade, buscando destruir ou desestabilizar computadores ou redes de comunicação. Alvos comuns são usinas nucleares, linhas de gasodutos e estações de energia, ou operações tecnológicas. São mais organizados, como um exército online e, pela falta de recursos, precisam "pegar emprestado" os recursos necessários para os ataques DDoS, porém o principal ataque é o spear phishing, que após identificar uma pessoa com grandes privilégios de rede, cuidadosamente planejam um ataque de engenharia social;

    - Cyber-criminoso - mais auto-centrado, com motivação financeira: Busca atingir seus resultados através de uma combinação de phishing, roubo de identidade ou clonagem de cartão de crédito, que eles usam ou vendem no mercado branco, ou por:
        - Ransomware: malware que bloqueia o acesso as informações ou sistemas de um computador, até que o ransom (resgate) seja pago;

    - Cyber-guerreiro - o que tem menor auto-interesse: O mais perigoso devido aos recursos de uma nação-estado ao seu dispor. Motivados pelos interesses de sua terra natal, e podem ser bons, neutros ou ruins, dependendo de onde trabalhe. Com um vasto arsenal de métodos, e algumas vezes, métodos secretos. Buscam vantagens em vunerabilidades em sistemas operacionais comuns que ainda não foram atualizados, conhecido como "exploração zero-dia", pois quando a vunerabilidade é lançada, existe o prazo de 0 dia para que seja resolvido. Basicamente, trabalham nessas aplicações buscando fraquezas, bugs e outros comportamentos que podem ser usados para atacar o sistema de computadores inimigos, e a fraqueza se mantém em segredo até o momento do uso, para que o suporte da aplicação não lance um patch de segurança.

## Categorias de hackers
São categorias distinguidas por cores:
- White hat: hacker com acesso que busca criar soluções para as vulnerabilidades;
- Black hat: hacker que ataca redes para obter lucro e causar danno;
- Grey hat: hacker que ataca redes, infringindo leis, mas não tem a mesma inteção do black hat. Se alinha com a categoria explorador
- Blue hat: variante do white hat, hacker que presta serviços de consultoria para terceiros, para testar futuros lançamentos e previnir possíveis falhas de segurança.

-----------------------------------
**lessons que não subiram**
------------------------------------
## Frameworks de ataque

- Cyber kill chain: Desenvolvido pela Lockheed Martin em 2011, com 7 estágios de um ataque cibernético:
    1. Reconhecimento: reune informações sobre o alvo, utilizando ferramentas como redes sociais e mecanismos de busca;
    2. Armamento: Criação da carga explosiva (códigos maliciosos ou softwares) que irão infectar o alvo, que podem, por exemplo, ser transportado através de um arquivo .doc, enviado por um e-mail de phishing;
    3. Entrega: Como o nome sugere, é o ato de enviar a carga para seu destinatário, que pode ser usado o método de engenharia social ou uma vulnerabilidade em um site;
    4. Exploração: É a utilização da carga para ganhar acesso ao sistema e obter vantagens das vulnerabilidades dos sistemas ou da rede;
    5. Instalação: É o processo de instalação de um software que é usado para ganhar e manter o controle do sistema, mesmo que a carga seja detectada e deletada ;
    6. Controle e comando: É o estabelecimento da comunicação com o sistema que foi comprometido, e pode envolver um servidor C&C ou outros meior de comunicação;
    7. Exfiltração (coleta e envio de dados): A extração de dados sensíveis do alvo, copiando para um servidor remoto, ou usar o sistema comprometido para lançar ataques a outros alvos.
    As limitações do framework vem da presunção de que os ataques são de origem externas e que reforça a utilização de métodos de defesas tradicionais.
- MITRE ATT&CK: Criado em 2013, a empresa MITRE publicou as táticas, técnicas e conhecimento comum de adversários (Adversarial Tatics, Techniques & Common Knowledge), parecido com o Cyber Kill Chain, ajuda a entender a metodologia dos ataques, porém, está em constante desenvolvimento. Possui uma matriz que descreve táticas específicas e métodos usados para comprometer sistemas e roubar e manipular informações. As técnicas são agrupadas por categorias baseadas no tipo de ataque ou atividade que estão sendo utilizadas. Um dos benefícios da matriz é a a linguagem comum e a disponibilização do framwork para analisar e discutir sobre as ameaças.