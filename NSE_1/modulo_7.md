# Autenticação e controle de acesso

## Aula 1 - Métodos de autenticação
### Tipos de autenticação
- Inerência - utiliza um traço físico único em que a pessoa que está tentando se autenticar tem. Existem vários traços únicos, os mais comuns são:
    - digital, retinas iris, padrões faciais e medidas das mãos
- Posse - baseado em algo que você tem, e mais ninguém. Pela lógica, se você tem algo só você tem, isso confirma quem você diz que é:
    - Assinatura digital é um exemplo, já que sua chave privada, só você tem acesso;
    - Hardware ou Software token (dispositivo que gera um OTP usando um algoritmo com chave secreta);
    - Mensagem SMS - OTP (One-time password)
- Comportamento - autenticação baseada em comportamento utiliza dados biométricos ativos. Tipos de identificação:
    - Por voz;
    - Dinâmica de digitação;
    - Características de utilização do mouse.
- Conhecimento - baseado em conhecimento (segredo):
    - Um exemplo de autenticação baseada em conhecimento é perguntas e respostas;
    - Senhas;
    - PIN (personal number identification).
### Melhoria na segurança da autenticação - MFA
- Single-Factor Authentication - pede uma forma simples de autenticação, como nome de usuário e senha. Porém, existe uma crescente movimento em que se demanda duas ou mais formas de autenticação, conhecido como MFA (Muti-Factor Authentication).
- Um exemplo de MFA são ações realizadas em caixas eletrônicos, pois você precisa do cartão (o que você tem), sua senha (o que você sabe) e da sua digital (algo inerente a vocẽ).

