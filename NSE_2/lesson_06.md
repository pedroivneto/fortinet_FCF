# Sistema de prevenção a intrusão e controle de aplicação no FortiGate

### O que é um IPS
Intrusion Prevention System (IPS) é uma ferramenta de segurança que monitora o tráfego de rede em tempo real e automaticamente bloqueia atividades suspeitas/maliciosas.
O sistema inspeciona os pacotes de dados para padrões de ataque ou comportamentos suspeitos conhecidos, e então toma a ação de 'drop' no pacote ou alerta os administradores, para que possam previnir um potencial dano a rede.

---

### Por que o IPS é importante
Os IPSs são importantes para a segurança da rede por que:
* Previne em tempo real contra ameaças a redes: através da verificação de vulnerabilidades expostas e assinaturas de ataque conhecidas;
* Ativa o `deep packet inspection`, analisando a nível de apliação os pacotes que passam por ele;
* O IPS foca a análise em pacotes que já foram liberados pelo firewall, complementando a segurança, com uma camada a mais de inspeção;

---

### Técnicas de detecção
* **Decodificadores de protocolo**: Um attacker pode enviar um pacote malformado intencionalmente --> O decodificador de protocolo identifica o tráfego que não está de acordo com os padrões --> FortiGate pode identificar a maioria dos protocolos, apesar do número da porta usada no pacote --> Apenas as assinaturas relacionadas ao protocolo detectada são usadas enquanto está sendo realizada uma varredura por ataques;
* **Assinaturas**: O IPS compara o tráfego de rede a um banco de dados conhecido de ameaças --> Se houver correspondência, o IPS toma ação de acordo com a configuração para aquela assinatura --> FortiGate possui uma base de dados vasta e recebe diariamente novas atualizações do FortiGuard.

---

### O que é uma aplicação de controle
> Aplicações de controle ajudam a melhorar a segurança e ficar em conformidade com padrões de fluxo de tráfego da aplicação da rede

### Por que aplicações de controle são importantes?
Uma aplicação de controle pode identificar um tráfego de rede gerado por uma aplicação específica e tomar ações apropriadas, como:
* Monitoria;
* Bloqueio;
* Modelagem de tráfego.

---