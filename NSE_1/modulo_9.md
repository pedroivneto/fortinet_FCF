# Segurança de dados e aplicações
## Aula 1 - Proteção de dados
Na proteção de dados, devemos ter salvaguardas de segurança e privacidade para:
- Dados em descanso;
- Dados em uso;
- Dados em trânsito.
Para pode garantir:
- Confidencialidade;
- Disponibilidade;
- Integridade;
- Não-repudiação.
Logo, proteção de dados é a união de segurança com privacidade.
### Proteção de dados
Segurança dos dados incluem:
- Manter a integridade, digital ou física dos ativos;
- Garantir a integridade dos dados através de todo seu ciclo de vida;
- Autorização adequada de acessos e usos;
- Soberania dos dados;
- Privacidade dos dados.
### Tipos de dados
Os tipos de dados mais comuns:
- CUI (Controlled unclassified Information)
    - Criado ou possuído pelo gonverno;
- PII (Personally Identifiable Information)
    - Inclui endereços ou dados biométricos
- PHI (Protected Health Information)
    - Relacionados a informações médicas confidenciais
- PCI (Payment Card Information)
    - Os administradores de cartão são responsáveis pelos pagamentos eletrônicos
- Sensitive Institutional Data
    - Dados legais, regulatórios, administrativos e requerimentos contratuais
- IT Security Information
    - Dados sensíveis relacionados a proteção da rede
- Exporte Control Records
    - Dados relacionados ao comércio de exportação
- Student Education Records
    - Mantido por uma instituição ou agência educacional
### Riscos aos dados
- Exposição acidentã dos dados
    - APIs permitem aplicações a interagirem sem nenhuma ação do usuário;
    - Eles podem prover acesso não autorizado a dados sensíveis
- Compartilhamento de dados sem intenção
    - Quando uma mensagem de phishing é enviada para enganar o destinatário
- Infecção por malware - criados para comprometer a confidencialidade, integridade e disponibilidade dos dados:
    - Malware: software criado para parar um dispositivo para obter acesso não atorizado a informações privadas;
    - Ransomware: bloqueia o sistema e ameaça a vítima com a exposição de dados ou o bloqueio permanente, a menos que um resgate seja pago;
    - Doxware: é um tipo de ransomware que ameaça a divulgação de dados sensíveis, constrangedores ou incriminadores, a não ser que um resgate seja pago;
    - Leakware: um programa que coleta dados sem que seja notado, e envia ao criminoso virtual. Quando o mesmo coleta informações suficientes, demanda o pagamento de um valor para a não divulgação dos dados.
### Ciclo de vida dos dados
O ciclo de vida dos dados consistem em 5 estágios:
- Criação
- Armazenamento
- Uso
- Arquivamento
- Destruição
Durante o ciclo de vida dos dados, eles estão em constante movimento, nos seguintes passos:
- Descanso > Trânsito > Em uso;
### Táticas e técnicas da proteção dos dados
- Trainamento: ajuda o entendimento de todos da importância da proteção de dados. Ajuda no entendimento claro e na aplicação das políticas de uso de dados da empresa;
- Ofuscação de dados: ou mascaramento de dados, minimiza o valor dos dados sensíveis a ação de intrusos não autorizados. Diferencia a disponibilidade da informação de acordo com os níveis de autorização;
- Criptografia: Aumenta a integridade de confidencialidade dos dados;
- Resiliência dos dados: importante para a continuidade e disponibilidade dos dados na empresa. Backups regulares permitem que os dados sempre estejam disponíveis e acessíveis;
- Destruição: deve ser feito com o procedimento correto, como erasure (apagamento, destriução), que sobrescreve os dados com informações sem importância ou padrões pseudo-aleatórios para destriur completamente o arquivo;
- Prevenção de perda de dados: Permite a detecção e prevenção de aberturas para ataque, roubo ou destruição indesejada de dados.
### Boas práticas
- DLP (Data Loss Prevention)
    - Identifica informações sensíveis;
    - Previne compatilhamento acidental de dados;
    - Audita e monitora movimentação de dados;
    - Educa os usuários sobre conformidades.
