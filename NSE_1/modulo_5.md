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
    - Block: encripta a informação do texto em blocos. O tamanho do block depende do tamanho da chave. Se a chave tem tamanho de 256 bits, o bloco também terá tamanho de 256 bits. Exemplos dessa cifra são DES (Data Encryption Standart), 3DES1, AES (Advanced Encryption Standard) e Blowfish