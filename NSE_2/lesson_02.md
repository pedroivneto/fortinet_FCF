# Como as políticas de firewall funcionam

### O que um faz um firewall?
> Firewall é um dispositivo de segurança físico ou uma aplicação de software que monitora e controla o tráfego entrante e sainte (incoming e outgoing - I/O)

> Os firewalls tomam ações, como permitir ou bloquear um tráfego específico, baseado em regras pré-definidas.

---

### Segmentação interna
Segmentar a rede diminui a chance de infecção lateral, caso ocorra uma brecha na segurança, melhorando também a classificação de acesso que cada agente possui (cada usuário acessa os dados do seu setor), protegendo ativos de alto valor, como servidores e bancos de dados.

A segmentação é realizada por um firewall de perímetro, onde dentro desse perímetro podem ter:
* Firewall interno de segmentação (ISFW);
* Firewall interno
Essa técnica é chamada de microsegmentação, que envolve a estratégia de segurança de dividir a rede em pequenas zonas segura.
Todas as ferramentas se baseiam na lógica principal:
* Fonte;
* Destino;
* Porta;
* Protocolo;
* Ação (libera ou bloqueia)

---

### Regras de firewall
> É uma instrução específica que diz ao sistema: ´qual tráfego examinar´, ´quais condições devem ser satisfeitas´ e ´qual ação tomar´.
Basicamente, as regras são um grande repositório de condicionais de SE/ENTÃO (IF/THEN).

* **Ex 1**: *SE* um tráfego de um usuário é enviado para a internet *E* está usando a porta 443, *ENTÃO* permita
* **Ex. 2**: *SE* o tráfego se origina da rede de estudantes *E* tenta acessar o servidor de pagamentos, *ENTÃO* negue.

---

### Componentes de uma regra de firewall
* **Source (Remetente - de onde saiu o pacote)**: Uma fonte pode ser expressa como:
    * Um endereço de IP simples;
    * Um intervalo de endereços de IP;
    * Uma sub-rede;
    * Uma zona da rede;
    * A identidade de um usuário.
* **Destination (Destinatário - Destino final)**: Destinos podem ser expressos por:
    * Um servidor;
    * Uma sub-rede;
    * Um dispositivo específico;
    * Uma zona;
    Uma aplicação.
* **Port (Porta)**: Regras de firewall para  portas TCP/UDP normalmente referencia:
    * HTTP - 80;
    * HTTPS - 443;
    * Secure Shell (SSH) - 22;
    * Telnet - 23 (porta insegura);
    * Simple Mail Transfer Protocol (SMTP) - 25.
* **Protocol (Protocolo)**: Regras de firewall para protocolos IP normalmente referenciam:
    * TCP (transmission control protocol);
    * UDP (User Datagram Protocol);
    * ICMP (Internet Control Message Protocol).
* **Action (Ação)**: Regras de firewall de ação normalmente são:
    * Allow - Permitir;
    * Deny/Drop - Negar/Largar(Deixar);
    * Authenticate - autenticar;
    * Reject - rejeitar;
    * Log.
* **Regras adicionais**:
    * Identificação dos tipos de aplicações;
    * Examinar cabeçalhos de HTTP e URLs;
    * Avaliar tipos de arquivos;
    * Associar o tráfego a identidade do usuário;
    * Analisa tráfego criptografado quando configurado para criptografia TLS (Transport Layer Security).

---

### Como os firewall validam os tráfegos
Firewalls processam as regras sempre top-to-bottom (de cima para baixo), e segue o comportamento de primeira correspondência. A partir do momento que a primeira correspondência é encontrada, o firewall para de processar o conjunto de regras.
Por conta desse comportamento, as regras devem ser estruturadas de menor granularidade para maior granularidade, evitando assim erros nos processamentos das informações.

> **Implicit deny rule (regra implicita de negação)**: bloqueia automaticamente o tráfego que não tem correspondencia com as regras de firewall.

> **Shadow rule**: É uma regra que nunca vai ser usada, pois a regra acima sempre terá correspondencia primeiro, criando um gap de segurança.

Ex.:
**Regra 1**: Permitir todos tráfego proveniente da rede *Estudante*.
**Regra 2**: Negar acesso ao servidor de pagamentos

As regras de firewall devem seguir os princípior de menor privilégio, o que significa a liberação do mínimo de acesso necessário para que os usuários ou sistemas possam cumprir suas tarefas.

---

### Componentes necessários para uma regra de firewall
Um firewall deve conter:
* Um critério de correspondência;
* Uma ação:
    * permitir;
    * negar;
    * rejeitar;
    * logar.

> A regra implicita de `deny` se aplica quando as regras não estão definidas (fonte, destino e serviço são, por padrão, definidos por `any`, fazendo com que o firewall nege imediatamente a requisição)

