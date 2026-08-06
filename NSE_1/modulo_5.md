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
