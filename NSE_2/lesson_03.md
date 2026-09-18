# Autenticação de usuário com NGFW

### Por quê autenticação de usuário importa
Firewalls tradicionais utilizam endereços de IP como identificação, porém esses endereços identificam apenas as máquinas, e não quem as está usando, expondo 2 problemas:
1. Causa uma falta de confiabilidade e;
2. Limita a responsabilidade do usuário (se eu apenas sei qual máquina foi utilizada e não quem a utilizou)

---

### O que é autenticação de usuário?
> É o processo de verificação de identidade de um usuário.

Os passos da autenticação são:
1. Autenticação (quem é você): O usuário e a máquina (que se autentica de outra forma) se identificam;
2. Autorização (o que você pode fazer): De acordo com as regras aplicadas ao usuário, são liberadas as ferramentas aos quais esse indivíduo pode utilizar.

Fatores de autenticação:
* Algo que você sabe: nome de usuário, senha ou pergunta secreta;
* Algo que você tem: dispositivos físicos ou softwares de autenticação (geradores de token),ou o sistema gera um OTP (one-time password) e envia para um telefone cadastrado ou e-mail;
* Algo que você é: fatores biométricos, ou fatores herdados, como biometria digital, retina, iris ou até mesmo biometria facial;
* Algo que você faz: segurança baseada nos padrões únicos que o usuário produz, como o tom da voz e sotaque ou a forma como digita.

---

### Como NGFW aplica a identidade de usuário
Ao implementar a autenticação de usuário, os NGFWs podem mapear as máquinas utilizadas pelos usuários, podendo também integrar um serviço de diretórios, permitindo com que seja mapeado a utilização de um usuário ou um grupo de usuários, integrando as identidades diretamente as regras de firewall, permitindo que as políticas sejam baseadas nos usuários e não apenas de onde o tráfego se originou.
Em firewall tradicionais, as regras se baseiam em endereços de IP, podendo permitir acessos de mútiplos usuários a um único IP. Quando as regras são atraladas ao usuário, aumenta-se a segurança, responsabilidade e política de controle.

---

### Métodos comuns de autenticação
1. Uma das autenticações mais utilizadas por NGFWs é a utilização de autenticação baseada em diretório, onde as credencias são armazenadas em:
    * Lightweight Directory Access Protocol (LDAP);
    * Active Directory (AD)
O firewall pode identificar e associar sua rede de atividades pela sua identidade, permitindo que o firewall fortaleça as políticas baseadas em usuários ou grupos.
2. Single sign-on (SSO) é uma forma de autenticação onde o usuário loga apenas uma vez, o firewall reconhece a identidade, evitando múltiplos log-ins. O fluxo de autenticação se dá da seguinte forma:
    1. O usuário realiza o log-in no sistema, que é enviado a um servidor de controle (Domain controller - DC);
    2. O DC envia as informações ao servidor de acessos (AD ou LDAP), que geram um token de identificação;
    3. Com o token de identificação, o DC, conhecido também como agente coletor, rastreia os passos do usuário na rede, de acordo com as regras de firewall (quais acessos são permitidos para cada usuário).
3. MFA (Multi-Factor Authentication) é o requerimento de dois ou mais fatores de autenticação, como algo que você sabe (senha) com algo que você tem (OTP). Com a implementação do MFA:
    * Uma segunda camada de segurança é adicionada (OTP, app, token);
    * Segurança mais forte para acessos sensíveis (como acesso a área do seu banco).
4. Autenticação baseada em certificados é quando dispositivos e usuários se autenticam através do envio dos seus certificados digitais ao firewall, que verifica com o AD a validade do mesmo, e é utilizado em ambientes corporativos. Os dispositivos que utilizam certificados digiais para autenticação incluem:
    * Dispositivos de usuários: laptops, smartphones e tablets;
    * Servidores: servidores web, de aplicação e de e-mail;
    * Dispositivos de rede: firewalls, routers e switches;
    * Dispositivos IoT: sensores inteligentes, câmeras ou sistemas de controle industrial.
    
 ---