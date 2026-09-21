# Controle de acesso web usando filtros

### Por que é preciso utilizar filtros na web?

* Melhorar a produtividade dos colaboradores, evitando distrações com redes sociais, por exemplo;
* Previnir congestionamento de rede, bloqueando por exemplo, sites de streaming, que costumam utilizar muita banda da conexão;
Diminuir a exposição a ameaças baseadas em web, limitando o acesso a sites inseguros;
* Limitar a responsabilidade legal, ao limitar o download de material indevido ou ofensivo;
* Previnir o consumo de material inapropriado.

---

### Categorias de filtro do FortiGuard
* **Security Risk**;
* **General interest**;
* **Bandwidth consuming**;
* **Adult/Mature Content**;
* **Local Categories**.

Todas as categorias podem ter subcategorias, que estão listadas no site da [FortiGuard](www.fortiguard.com/webfilter).
As categorias são classificadas de acordo com seu tópico dominante.

### Aplicando ações de categorias
As ações são tomadas não por URLs, mas sim pelo comportamento de utilização e risco de uma determinada categoria.
As ações são:
* **Permitir**: permite acesso aos sites da categoria;
* **Bloqueio**: o bloqueio previne o acesso aos sites da categoria. Os usuários que tentam acessar um site bloqueado veem uma mensagem indicando que o site foi bloqueado. Quando um site é bloqueado, um log de segurança é gerando no FortiGate;
* **Monitor**: Permite o acesso aos sites da categoria e grava os dados de acesso, assim como URLs, destino e IP, nos logs do FortiGate;
* **Aviso**: Informa aos usuários que a requisição ao site não pode ser acessada devido as políticas de internet, contudo, os usuários tem a escolha de continuar ou retornar. O intervalo de tempo que o aviso aparece pode ser configurado, uma vez acessado, após esse período, o aviso aparece novamente;
* **Autenticar**: Permite o acesso a categoria se o usuário autenticar-se com um usuário e senha válidos, podendo:
    * Configurar a autenticação baseada em um grupo ou usuário individual;
    * Customizar o intervalo de tempo de permissão;
    * Usuários podem acessar outros sites da mesma categoria sem a necessidade de realizar nova autenticação, a menos que o tempo expire.

---

### Processo recomendado para configurar web filters
* **Tarefa \#1:**: Validar a licensa de uso do FortiGuard;
* **Tarefa \#2**: Identificar como o FortiGuard categoriza os sites que serão permitidos ou bloqueados;
* **Tarefa \#3**: Configurar um perfil de segurança de filtro web;
* **Tarefa \#4**: Aplicar o perfil de filtro web na política de firewall para começar a inspecionar o tráfego web - caso queira registrar logs, ativar o logging nas políticas de firewall;
* **Tarefa \#5**: Testar as políticas de filtro de web configuradas para o perfil selecionado.

---