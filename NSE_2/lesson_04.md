# Como os NGFWs bloqueiam malwares

Enquanto firewalls tradicionais verificam apenas informações das camadas de tráfego e rede (como números de IP e direção do tráfego), malware podem ser enviados de forma disfarçada em um pacote com informações de envio legítimas, permitindo a passagem e infectando o dispositivo de destino.
Os firewall de nova geração, além de realizar as inspeções padrão, existe uma cada extra de proteção, como:
* Deep packet inspection: o firewall inspeciona de forma profunda o pacote recebido (suas aplicações, e até mesmo o código da aplicação);
* Application awareness: com a evolução das ameaças, os firewalls também evoluíram, a ponto de ter mais conciência sobre a importância das aplicações para a segurança da rede, dispositivos, etc...;
* Threat intelligence: possuir uma boa base de informações sobre as ameaças facilitam a identificação das mesmas.

---

### Detecão baseada em assinatura
Funciona com a comparação de assinaturas. Em um banco de dados, existem assinaturas de malwares já conhecidos préviamente. Se caso a assinatura for compatível, o firewall pode identificar e bloquear de forma rápida e eficiente.
Uma brecha importante nesse sistema é que, se caso a assinatura não tenha correspondência no banco de dados (um novo malware ou ataques de dia-zero), o tráfego pode passar por essa barreira.

### Detecção baseada em comportamento
Ao invés de apenas visar nos malwares já conhecidos, esse tipo de detecção monitora constantemente o comportamento dos processos da rede.
Caso um arquivo esteja tentando se comunicar com a rede externa de forma constante, ele é considerado um malware, ou caso um script está tentando acessar dados sensíveis, também é considerado malware.
Logo, a detecção por comportamento não se baseia pelo o que é, e se pela forma que se comporta (o que faz), e isso complementa a detecção baseada em assinatura.

---

### Threat Intelligence
Os firewalls de nova geração possuem conexão com a inteligência de ameaças, um banco de dados mundial sobre todas as ameaças conhecidas no mundo real.
Dessa forma, o firewall se mantém atualizado, sobre novos IPs em listas de bloqueio, ou servidores conhecidos por distribuirem malwares.
Alguns exemplos de organizações e pesquisadores que contribuem com a inteligência de ameaças:
* Fortiguards Labs;
* Cisco Talos;
* Google Mandiant;
* CrowndStrike, Microsoft Security Intelligence, IBM X-Force, etc...

---

### Como NGFWs bloqueiam malware
Ações comuns:
* Block/deny: bloqueia/nega conexão com pacotes de malware, previnindo o estabelecimento de conexões potencialmente perigosas;
* Drop: caso um malware seja detectado, o firewall deixa cair (devolve) o pacote, previnindo que o malware chegue ao usuário;
* Terminate: se existe um processo em andamento (como uma conexão com um servidor C&C), o firewall finaliza a conexão, interrompendo imediatamente a comunicação;
* Alert/Log: o firewall pode enviar um alerta aos analistas de segurança, gerando um log da ação, criando uma visibilidade do ataque, para que seja realizado futuramente uma investigação e resposta;
* Reject: rejeita explicitamente a conexão, enviando um reset de TCP (RST) ou uma mensagem de erro ICMP;
* Redirect: Envia o tráfego a outro destino, como um portal captive (para login - identificação do usuário) ou inspeção de dispositivo;
* Quarentine: Isola o dispositivo ou o fluxo do tráfego do resto da rede (para que seja analisado - investigação e resposta).

---

### Proteção avançada
* Análise de sandbox: se um fluxo for verificado como suspeito, é enviado para uma sandbox (ambiente controlado) - para analisar o comportamento, e caso seja identificado um comportamento perigoso, o arquivo é deletado;
* Checagem de reputação: O firewall busca no banco de dados gloal de reputação, informações sobre o arquivo. Caso encontre alguma correspondência, marca o arquivo com uma red flag e deixa registrado para análise futura;
