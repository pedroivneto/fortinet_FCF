# Conectando vários locais com segurança

### O que é uma VPN
É uma rede virtual privada (Virtual Private Network). A VPN cria uma conexão criptografada atraves de redes públicas (como a internet). Essa conexão segura permite que usuários, escritórios e dispositivos se comuniquem como se estivessem conectadas a uma mesma rede privada.
* A VPN é uma das melhores ferramentas para garantira privacidade;
* Também pode garantir o anonimato do usuário conectado a qualquer serviço público de internet.

---

### Tipos de VPN
*VPN de acesso remoto: Conecta os dispositivos dos usuários a uma rede de uma organização;
* VPN site-to-site: Conecta redes inteiras.

---

### Benefícios da VPN
1. Protege os dados através de criptografia;
2. Permite usuários a acessarem de forma segura os recursos organizacionais;
3. Permite que organizações se conectem a múltiplos locais de forma segura.

---

### Como a VPN funciona
A VPN cria um túnel criptografado seguro entre o dispositivo e seu destino final:
1. A VPN autentica e estabelece chaves de criptografia para proteger a comunicação;
2. Antes de enviar o pacote, a VPN criptografa os dados, para que ninguém possa visualizar ou modificar o pacote;
3. Quando o pacote chega, a VPN descriptografa o pacote e o entrega ao usuário final.

---

### O que é um IPsec
IPsec (Internet Protocols Security) é uma coleção de protocolos usados para assegurar as comunicações de rede.
IPsec provém:
01. **Autenticação**: verifica a identidade de ambos os endpoints antes de qualquer troca de dados (Quem é você);
02. **Integridade**: garante que o dado não foi adulterado ou alterado durante o trânsito;
03. **Criptografia** : protege os dados durante a viagem pela rede de acessos não autorizados.

---

### Como IPsec é utilizado
* **Conexão e autenticação**: Primeiro, o usuário confirma sua identidade com o servidor VPN. Após a confirmação de identidade, os dispositivos trocam chaves de criptografia para assegurar a conexão;
* **Criptografia de dados**: Para que os pacotes viagem com segurança, a VPN criptografa os dados em um pacote e envia para o destino, através da conexão segura;
* **Descriptografia e entrega**: Quando o pacote cheaga ao destino, o endpoint que recebeu o pacote descriptografa o pacote e entrega ao seu destino final.

---