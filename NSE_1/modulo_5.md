# Criptografia e infraestrutura de chaves pública

- Criptografia (do grego kryptós, "escondido", e gráphein, "escrita") é a ciência e a prática de transformar informações legíveis em um código indecifrável para proteger os dados contra acessos não autorizados. O objetivo principal é garantir que apenas quem possui a chave correta consiga ler ou modificar a mensagem original.
- Infraestrutura de chaves públicas é a implementação da criptologia em uma rede de computadores, e é baseada em 3 pilares:
    - Hardware;
    - Software; 
    - Políticas e procedimentos.

## Encriptação, assinatura digital e termos relevantes
- Encriptação: Processo de conversão de um texto em um texto criptografado, transformando algo que antes era legível em ilegível;
- Assinatura digital: É uma forma de criptografia que produz um valor único, que fica associado a uma pessoa.
 - A utilização de criptografia e assinatura digital satisfazem vários objetivos:
    - Privacidade e confidencialidade;
    - Integridade;
    - Autenticidade;
    - Não-repudiação: a pessoa que assinou não pode negar que assinou o contrato.

## Cifras
- Cifra é uma forma de disfarçar ou manter em segredo um código. Um algoritmo, uma sequencia finita de instruções, juntamente com uma chave, transforma um texto normal em um texto criptografado, podendo também realizar o movimento contrário, chamado descriptografia. Exemplo de criptografia simples:
    - Tomando o alfabeto de 26 letras, a mensagem "Hail Caesar", movendo cada letras em 3 posições, a mensagem se torna "Kdlo Fdhvdu". Para decriptografar a mensagem, deve-se saber o número de letras que será movido, e realizar o movimento contrário;
    - O número de mudanças de letras é o segredo compartilhado ou chave, o método é o algoritimo
- One-Time Pad Cipher: é um tipo conhecido por compartilhar a chave apenas uma vez, e por conta que os pedaços de papéis eram precisos para descriptografar a mensagem:
    - 26 combinações possíveis de cada letra da mensagem;
    - Quase 12 milhões de combinações possíveis para uma mensagem de 5 letras;
    - Sem um computador, é impossível quebrar usando força bruta (é o método de tentativa e erro).
- Existem 2 tipos de cifras usadas por computadores:
    - Stream: encripta uma sequência de texto bit ou byte por vez. Exemplos de cifras Stream são FISH e RC4 (Rivest Cipher);
    - Block: encripta a informação do texto em blocos. O tamanho do block depende do tamanho da chave. Se a chave tem tamanho de 256 bits, o bloco também terá tamanho de 256 bits. Exemplos dessa cifra são DES (Data Encryption Standart), 3DES1, AES (Advanced Encryption Standard) e Blowfish.

## Aula 2 - Chaves e algoritmos de criptografia
- Uma chave digital é um valor, que pode ser expressado alfanuméricamente, que é usado para operações criptograficas. Podem ser usadas como:
    - Assinatura digital;
    - Código de autenticação de mensagem (MAC);
    - Encriptação:
        - Fluxo de informação entre 2 dispositivos;
        - Grande volume de dados estáticos;
        - Pequeno volume de dados, como uma chave digital.
- As chaves podem ser de 2 tipos:
    - Pública:
    - Privada.

### Tamanhos e Força das Chaves (*Key Lengths and Strengths*)

| Característica | Chave Grande (Assimétrica)<br>`1024 bits ou mais` | Chave Pequena (Simétrica)<br>`128 a 256 bits` |
| :--- | :--- | :--- |
| **Criptografia** | Criptografa pequenas quantidades de dados | Criptografa grandes volumes de dados (*bulk data*) |
| **Uso / Aplicação** | Transferência de chaves e assinaturas digitais | Fluxos contínuos de dados ou grandes volumes onde a performance é crítica |
| **Força / Segurança** | **Tamanho (Comprimento)** + **Complexidade** | **Tamanho (Comprimento)** + **Complexidade** |

---

#### Fórmula da Força da Chave

**Força da Chave** = **Tamanho (Comprimento)** + **Complexidade**

* **Apenas dígitos:** `10.000.000.000` combinações possíveis.
* **Dígitos + Letras maiúsculas e minúsculas:** `218.000.000.000.000` combinações possíveis.

- Alongamento de chave: é um processo que aumenta o tamanho da chave, onde pegamos uma senha e jogamos em um tipo de algoritmo hashing para produzir uma senha mais forte.
- Exemplo de algoritmo: Password-Based Key Derivation Function Two (PBKDF2) e BCRYPT, que é o algoritmo padrão de várias distribuições Linux.
- O BCRYPT funciona adicionando valores aleatórios - salt - para aumentar a entropia da senha final.

## Algoritimo simétricos e assimétricos

#### Algorítimo simétrico
- É uma cifra usada para encriptar e descripitar dados usando a mesma chave. Exemplos de algoritmos simétricos são, sendo todos do tipo stream, menos o RC4. O restante são cifras de bloco:
    - DES (Encriptação padrão de dados);
    - 3DES;
    - IDEA (Algoritmo de encriptação de dados internacional);
    - AES (Padrão de encriptação avançado);
    - Rivest Cipher (RC4, RC5 e RC6);
    - Blowfish / Twofish
- Vantagens:
    - Encriptação e descriptação mais rápidos que a assimétrica;
    - Mais eficiente para encriptar e descriptar grandes quantidades de dados.
- Desvantagens:
    - A chave permanece em segredo;
    - Como proteger a chave?.

#### Algorítimo assimétrico
- É uma cifra que usa um par de chaves matematicamente relacionadas para criptografar operações. Pode fazer todas ou algumas das operações:
    - Encriptação
    - Troca de chaves;
    - Assinatura digitaç;
- Algoritimos assimétricos e criptografia são conhecidos tambmém como algoritimo de chave pública. Alguns exemplos de algoritimos assimétricos:
    - Diffle-Hellman;
    - Rivest, Shamir e Adleman (RSA);
    - Elliptic Curve Cryptography (ECC);
    - Pretty Good Privacy (PGP) e (GPG);
    Digital Signing Algorithm (DSA).
- Vantagens:
    - Aumenta a segurança da informação;
    - Usuários não compartilham suas chaves privadas;
    - A chave pública encripta e a chave privada decripta;
- Desvantagem:
    - As operações de encriptar e decriptar são mais lentos comparados com a criptografia simétrica.

## Aula 4
#### Hashing
- Processo de conversão de uma entrada de qualquer tamanho que gera uma saída de valor único fixo.
- Existem 3 características de segurança no hashing:
    - A saída é de tamanho fixo determinado pelo algoritmo, o que nega a obtenção de informações sobre o arquivo;
    - Cada saída é única, evitando a duplicação (mesmo resultado) para mais de um arquivo (é raro, mas pode acontecer);
    - O hash não é reversível, logo se você pegar uma saída e tentar realizar o caminho inverso, você não conseguirá, logo não é possível determinar o valor da entrada pelo arquivo de saída

- O uso de hashing e criptografia assimétrica gera o que conhecemos como assinatura digital, que garante a integridade dos dados, autenticação do assinante e a não-repudiação (não existe a possibilidade do assinante negar que não assinou). O processo segue da seguinte maneira:
    1. O documento a ser assinado passa pelo processo de hashing, gerando um valor de saída, e esse valor de saída é criptografado com a chave privada do assinante;
    2. A assinatura digital, criado no passo anterior, é gerada e anexada ao documento original de entrada, antes do processo de hashing, gerando assim um documento/dado assinado digitalmente.
- O processo de verificação de assinatura digital segue da seguinte forma:
    1. O documento assinado digitalmente passa por um hash, o que irá gerar uma saída;
    2. A assinatura digital é decriptografada com a chave pública do assinante, gerando o hash original no passo anterior;
    3. As 2 saídas são comparadas, se elas forem iguais, significa que o documento não foi alterado.

- Tipos de hashing:
    - Message digest five (MD5 ou MD6);
    - Secure hashing algorithm one (SHA-1, 2, 3)
        - SHA-2 inclue SHA-224, SHA-256, SHA-384 e SHA-512;
        - SHA-3 inclui vários tamanhos de saída.
    - Microsoft LANMAN
    - NT LAN Manager Algorithm (NTLM);
    - HAVAL;
    - RIPEMD.

## Aula 5
#### Infraestrutura de chaves públicas
- Um ecosistema composto de **políticas**, **procedimentos**, **hardware** e **software**, que cria, armazena, usa, distribui e revoga certificados digitais. 4 entidades compõem uma infraestrutura de chaves públicas:
    - Autoridade certificadora (CA - Certification Authority);
    - Autoridade registradora (RA - Registration Authorty);
    - Servidor de diretórios (Directory server);
    - Usuário final (End entity).

## Aula 6 - Segurança Quântica
- O que é computação quaântica: Um novo método de cálculo, utilizando os princípios fundamentais da física para resolver problemas extremamente complexos. É usado uma unidade especial chamada qubits para explorar a maior quantidade de possibilidades ao mesmo tempo, permitindo resolver problemas complexos mais rápidos que os computadores atuais.
- Bits vs Qubits: Bits são unidades básicas de informação, que só podem ser 0 ou 1. Qubits é a unidade básica de informação na computação quântica, onde os estados de 0 e 1 existem em superposição de estados, sendo ambos simultaneamente até ser medido.
- Superposição: Princípio fundamental da mecânica quântica, que declara que em um sistema quântico pode existir vários estados simultaneamente, até que seja medido. Ex. uma moeda, quando está em sobre uma mesa, ela será cara (0) ou coroa (1). Quando jogamos a moeda, rodando, para cima, ela existe em um estado misto de cara ou coroa (0 ou 1) ao mesmo tempo, até que a coloquemos em cima da mesa (momento da medição).
- Vantagem quântica: Os qubits em superposição permitem que o computador quântico possa averiguar muitos caminhos de uma vez.

#### QC (Quantum-Criptography) vs PQC (Post-Quantum Criptography)
- QC - Quantum Criptography:
    - Fundação: Baseado nos princípios da mecânica quântica para manter a segurança da comunicação;
    - Limitação: Sua aplicação prática necessita de hardware especializado em mecânica quântica.
- PQC - Post-Quantum Criptography:
    -  Fundação: Baseado em novos algoritmos matemáticos criados para resistir a ambos os ataques, tanto da computação classica quando a quântica;
    - Vangatem: Não requer hardware quântico. Opera nas redes e dispositivos existentes, na escala atual.

#### 4 abordagens para PQC
- Lattice-based Cryptography: A segurança é baseada na geometria de uma grade de alta dimensão:
    - Problemas complexos da grade: É praticamente impossível computacionalmente achar o menor vetor em uma grade de alta dimensão;
    - Complexidade multidimensional: Mais dimensões expandem a busca exponencialmente, tornando a segurança mais forte.
- Hash-based cryptography: Se baseia na segurança das funções hash, que tem 3 características:
    - Funções hash de um sentido: Fácil de criar, impossível de reverter;
    - Mesma entrada = mesma saída: A mesma entrada sempre vai produzir exatamente a mesma saída, todas as vezes;
    - Efeito avalanche: Se for mudado apenas uma letra sequer, o resultado da saída do hash será totalmente diferente.
- Code-based cryptography: Baseia-se na dificuldade de decodificar um código linear aleatório corretor de erros:
    - Problema de difícil decodificação: Decodificar um código linear aleatório sem a chave é intratável;
    - Padrão escondido: Um usuário autorizado usa uma chave padrão. O agressor vê apenas peças aleatórias;
    - Eficiente e a prova de futuro: Desde 1978 o modelo de criptografia ainda não foi quebrado, ganhando o recorde de segurança criptográfica de maior tempo.
- Multivariate Cryptography: Baseado na dificuldade em resolver um sistema de muitas variáveis de equações polinomiais sobre uma quantidade finita de campos:
    - Equações polinomiais multivariadas: Resolver muitas equações polinomiais sobre corpos finitos é computacionalmente inviável, mesmo para computadores quânticos;
    - Public Key: Um conjunto de equações polinomiais multivariadas. Qualquer pessoa pode vê-las, mas resolvê-las é o problema difícil;
    - Private Key: Informação secreta de alçapão (trapdoor) que torna as equações trivialmente solváveis apenas para o usuário legítimo.

- Padronização do PQC: 4 padronizações foram criadas, após anos de estudos e análises:
    - Criação de chaves: Crystal-Kyber (ML-KEM);
    - Assinatura digital:
        - Crystals-Dilithium (ML-DSA);
        - SHINCS+ (SLH-DSA);
        - FALCON (FN-DSA).
