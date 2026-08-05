# Malware
- Malware: Malicious software, criado para romper, danificar ou ganhar acesso não autorizado a um computador.
- Os malwares são desenvolvidos para várias tarefas, como:
    - Modificar o comportamento de um programa;
    - Espionar usuários;
    - Roubo de dados;
    - Criptografia de arquivos importantes;
    - Negar acesso do usuário ao sistema.

## Sintomas de um computador infectado por malware
- Performance degradada: o dispositivo começa a travar;
- Pop-up windows: janelas pop-up abrem de forma constante e de forma indesejada;
- Abrir e fechar: aplicações abrem e fecham sozinhas e de forma inesperada;
- Problema com aplicações: sempre falham a tentativas de iniciazação;

- Vários outros problemas, como mensagens não usuais são mostradas ou caracteres são digitados de forma aleatória;

- Conta bloqueada: conta quebra ou realiza logout inesperadamente;
- Erro geral do computador: dispositivo desliga sozinho;
- E-mails em massa: envio de e-mails em massa disparados dasua conta sem vocẽ ter enviado;
- Mudança da homepage ou das configurações do navegador: Mudanças são realizadas de forma inexplicadas

## Tipos de malware
- Virus: segundo a Norton, "Um vírus de computador é um tipo de código ou programa malicioso escrito para alterar a forma como um computador opera e que é projetado para se espalhar de um computador para outro."
- O vírus se anexa a um programa ou um documento que suporta a execução de macros, para que o código do vírus seja rodado. Os traços de um vírus são:
    - Deve ser acionado por um usuário;
    - Ele se anexam a aplicações;
    - São criados para se espalhar para outros dispositivos na rede.
- Tipos de vírus:
    - Resident (Residente): o vírus infecta as aplicações quando são abertos;
    - Non-residents (Não-residentes): o vírus infecta os arquivos executáveis quando não estão rodando;
    - Multipartite (Multiparte): o vírus infecta muitos computadores, ficando na memória do dispositivo;
    - Direct action (Ação-direta): acessa a memória principal do computador e infecta todas as aplicações e arquivos;
    - (Browser hijacker) sequestrador de navegador: altera as configurações e funcionalidades de um navegador. Pode também conter adware, que causa abertura de janelas pop-ups e propagandas;
    - Overwrite (Sobrescrita): o vírus deleta e substitui dados em arquivos com seu próprio conteúdo ou código;
    - Web scripting: o vírus ataca a segurança de um navegador, permitindo injetar código malicioso no navegador;
    - File infector (Infestador de arquivo): o vírus sobrescreve arquivos quando eles são abertos;
    - Network (Rede): o vírus paralisa a rede e se espalha para os dispositivos conectados a rede;
    - Boot sector (Setor de boot): o alvo do vírus é o setor pricipal de boot (Master Boot Record - MBR) e se anexa na partição do HD, e se instala na memória principal quando o computador reinicia;

- Worm malware (Malware de verme): não precisam de um sistema hospedeiro e pode se espalhar pelos dispositivos e redes sem a necessidade de uma ação do usuário
- Rootkits:
    - rootkit: é uma coleção de softwares de computador tipicamente malicioso, criado para permitir o acesso a um computador ou uma área do software qe normalmente não é permitido. Mascara sua existência ou de outro software, operando perto ou no kernel do sistema;
    - DDL injection: permite a execução de códigos maliciosos para realizar a substituição de arquivos DDL legítimos por outros DLL maliciosos. O ataque é difícil de identificar e previnir por envolver o uso de processos e arquivos legítimos;
    -   Driver manipulation: altera ou substitui os drivers de software;
    - Keylogger: programa que grava cada tecla digitada pelo usuário para conseguir informações confidenciais;
    - PUP (Potentially unwanted program / programa potencialmente não-desejado): um programa que pode ser não desejado, mesmo que o usuário tenha consentido em baixar o programa, normalmente são baixados com os programas que o usuário queria, e incluem:
        - Spyware: acompanha a atividade do computador, e transmite informações de forma secreta do HD, buscando informações pessoais e agrupa os dados sem o consentimento do usuário;;
        - Adware: monitoram o comportamento online do usuário e pode marcá-los com ads específicos;
        - Discadores (dialers): se instala no computador e usa recursos de discagem, acarretando o aumento da conta de telefone;
    - Adversarial IA (): são inputs maliciosos criados para confundir a rede neural das IA's;
    - Ransomware: vírus que criptografa os dados e informações de um computador, que é reestabelecido após o pagamento de um resgate;
    - Trojan horse virus (Cavalo de Tróia): vírus disfarçado de algo que o usuário pretende baixar, mas não é. O RAT (Remote Access Trojan) controla remotamente o computador infectado;
    - Dropper: tipo de cavalo de Tróia que é criado para instalar malware no computador (pode instalar o malware ou baixar o malware);
    - Rogueware/Scareware: engana o usuário com informação falsa (como um pop-up informando que o computador está infectado), e oferece a solução, um ativírus (pago ou grátis), ao qual o usuário, por medo, baixa o arquivo, que na verdade é um malware;
    - Botnet malware: controla o hospedeiro através de um servidor C&C (command and control). O nome de um dispositivo infectado é bot ou robot, e uma coleção de dispositivos infectados é chamado de botnet;
    - Cryptojacking: uso ilegal de recursos para minerar moedas crypto. O hacker usa um malware ou script para sequestrar um computador e usa seus recursos para minerar cryptocurency